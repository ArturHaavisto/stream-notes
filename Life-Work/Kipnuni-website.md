# tmp
- Question about auth. If used build-in, can there be a login that uses only email and code sent to it?
- edit at least 5. Local Development Experience to not include "we changed". Just have the new spec
- For prerequisites, remove links
- What about running tests section?
- vscode extensions: where did TypeScript Nightly go?

As a software architect reviewing the [spec-new.md](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/0870c2a0c7/resources/app/out/vs/code/electron-browser/workbench/workbench.html) plan, I think you have an excellent foundation. The push towards a serverless, cloud-native architecture on Azure using Static Web Apps (SWA) and Azure Functions is highly scalable and cost-effective. Your choices of React 19, Tailwind CSS 4, and Playwright demonstrate a forward-looking, modern stack.

However, carefully reviewing the specifics, there are a few architectural gaps and potential pitfalls—particularly around serverless behavior, user identity, and the Azure Functions v4 programming model.

Here is my critical feedback and suggested adjustments to bulletproof this project before implementation begins:

### 1. The Azure Functions Node.js v4 Model (Major Catch)

**Observation:** In the "Project Structure", the `api` folder uses `function.json` files inside endpoint directories (`api/HealthCheck/function.json`).  
**Feedback:** You specified **Azure Functions v4**, but the folder structure reflects the old **v3 model**. The v4 Node.js programming model completely dropped `function.json` files. Instead, it uses a code-centric approach where you define routes directly in TypeScript (similar to Express) using `app.http()`.  
**Recommendation:** Update the folder structure to remove `function.json`. A simpler structure would be `api/src/functions/health.ts` and `api/src/functions/users.ts`. This makes the backend much cleaner and more familiar to Node.js developers.

### 2. User Authentication vs. MongoDB Persistence

**Observation:** You are using SWA built-in auth (`/.auth/login/{provider}`) but also have "User Management (CRUD via Azure Functions)" and a MongoDB `User` model.  
**Feedback:** SWA handles the identity (passing `$x-ms-client-principal`), but how does that tie into your MongoDB `User` collection? When a user logs in via SWA for the first time, they don't automatically get a row in your generic DB.  
**Recommendation:** Define a synchronization strategy. You will likely need to configure Azure SWA's **Custom Authentication API hook** or build a frontend routine that calls an `/api/users/sync` endpoint immediately after login. This endpoint will read the `x-ms-client-principal` header and upsert the user record into MongoDB so they exist in your local database for relations and custom properties.

### 3. Serverless Database Connection Limits (MongoDB Atlas)

**Observation:** You correctly identified the need for a **Mongoose Singleton** pattern.  
**Feedback:** Even with a Singleton, serverless applications can experience connection bursts (e.g., a traffic spike causes 50 concurrent functions to cold-start at once, creating 50 distinct connections). Since MongoDB Atlas uses TCP connections, this can rapidly exhaust cluster connection pools.  
**Recommendation:** In your Mongoose connection logic, strictly constrain connection limits using options like `maxPoolSize: 1` or `2`, `serverSelectionTimeoutMS: 5000`, and `socketTimeoutMS`. Alternatively, if the app receives highly bursty traffic, consider querying Atlas via the **MongoDB Atlas Data API** (which is REST/HTTPS based and stateless) instead of a stateful Mongoose TCP connection.

### 4. Frontend State & Data Fetching Layer

**Observation:** The frontend stack has React, Vite, and Tailwind, but omits a tool for managing server state.  
**Feedback:** With a heavily abstracted serverless API backend, standard `useFetch` or `useEffect` chains will become a bottleneck for caching, deduplicating requests, and handling loading/error states.  
**Recommendation:** Add **TanStack Query (React Query)** to your frontend Tech Stack. It inherently pairs perfectly with serverless REST APIs, giving you out-of-the-box caching, retry logic, and seamless suspense-handling without writing custom hooks.

### 5. Monorepo & Tooling Complexity

**Observation:** The frontend is at the repository root (`/package.json`), while the backend is nested in `/api/package.json`.  
**Feedback:** This creates an implicit monorepo where ESLint, Prettier, Husky, and Jest configs are sitting at the root alongside frontend code, but need to be respected by the backend code in `/api/`. This often causes TS/ESLint library collision issues.  
**Recommendation:** Use **NPM Workspaces**. Add a simplified `package.json` at the absolute root managing only Husky/workspaces, and move the frontend code exclusively into a [frontend](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/0870c2a0c7/resources/app/out/vs/code/electron-browser/workbench/workbench.html) or `/app/` folder, and the functions into `/api/`. Your `staticwebapp.config.json` and GitHub actions can easily target `app_location="frontend"` and `api_location="api"`.

### 6. Local Emulation Environment Nuances

**Observation:** Developers use `swa start` which wraps the Vite dev server and the Azure Functions.  
**Feedback:** Running Azure SWA emulator, Vite emulator, and Azure Functions emulator simultaneously often leads to hidden debugger attachment issues.  
**Recommendation:** Add a `launch.json` configuration block to the spec so the team knows how to attach a VS Code step-through debugger to the locally emulated API while the `swa` CLI is running. Serverless functions are notoriously tricky to trace console logs on without step-through debugging.

**Summary:**  
Overall, the infrastructure topology is great. Before executing, I highly recommend modifying the document to account for the **Azure Functions v4 model**, defining how **stateful Auth meets DB storage**, and updating the **package architecture** to leverage NPM workspaces to keep dependencies from bleeding across tiers.

# Plan
- I want to host a functional version of the website with separate frontend, backend, and database
	- At least have the same data that's there now and everything else can be "work in progress"
- I want to create a workflow where I can quickly and easily add/remove/modify content on the website (create new stream notes (url, discussed topics, image,...))
	- A page that shows all the stream notes and links to them


## Admin
- From the start, add security measures to code logic.

## Cookies
- can be implemented later

# Production plan
- Frontend: Azure static web app
- Backend: Azure functions
- Database: MongoDB Atlas
	- Backups: manually. Create a script that I can run for example weekly on my pc and store in google drive
	- Push new info on the website: local script to connect the backend api



# Ideas
- Multiple languages
- Multiple themes (at least dark/light themes)
- info popups from an icon
- extra info on the sides (long document)
- mini game that makes fun of me
	- throw tomatoes at my figure
- webxr small game/app
- a portal for my videos/content
	- youtube
	- tiktok
	- instagram/facebook
	- bluesky
	- Who am I - 
- Daily cards/updates of what I have done on and off the stream

create a page where there is a vertical timeline that represent my journey the timeline is in the middle and there are info cards on the sides, total in 4 columns when on desktop and tablet, and in 2 columns when in mobile. make the vertical line a bit flowy/snaky. on top of the line, put a current time and on right and left side of it, create a button that are links to other pages on the website. On the timeline, create clear sections with year numbers.

create a component that is an icon that I can easily add almost anywhere in the website that opens a small (size can change) text, info card popup with an x to close it or when the user clicks outside of it, it closes too.

- front page
	- who i am and my goals
- contact page
- portfolio
- video page
	- explain categories (brand)


Links
https://www.linkedin.com/in/arturhaavisto/

https://www.instagram.com/kipnuni/

https://www.facebook.com/kipnuni

https://t.me/kipnuni

mailto:contact.kipnuni@gmail.com


