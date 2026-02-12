# Setup
- Windows settings:
	- Enable developer
	- Enable sudo
- WSL2
- Terminal
- Git, Github
- SSH
- Zsh, Oh My Zsh
- pnpm
- Node.js
- VS code
	- Life Server
	- Prettier
	- ESLint
	- GitLens
	- Docker
	- Bracket Pair Colorizer 2
	- Path Intellisense
	- vscode-icons
	- Remote -SSH
	- (open vscode from ubuntu)
- Packet managers for windows:
	- Chocolatey
- Docker Desktop
- Browser Extensions
	- React Developer Tools
	- Redux DevTools
	- Postman Interceptor
	- JSON Viewer
	- ColorZilla
	- WhatFont
	- Wappalyzer
- Productivity tools
	- PowerToys
	- DevToys
- AI
	- Gemini
- VNC viewer


[The Ultimate Guide to Setting Up a Windows 11 Web Development Environment 🚀 ~ Sep, 24 - DEV Community](https://dev.to/a99divx/the-ultimate-guide-to-setting-up-a-windows-11-web-development-environment-pj4)
- WSL2
- Windows Terminal
- Github
- SSH
- Enhance Shell with Zsh and Oh My Zsh
- Node.js
- pnpm
- VS code
	- Life Server
	- Prettier
	- ESLint
	- GitLens
	- Docker
	- Bracket Pair Colorizer 2
	- Path Intellisense
	- vscode-icons
	- Remote -SSH
- WebStorm
- Packet managers for windows:
	- Chocolatey
	- Scoop
	- Winget
- Docker Desktop
- Browser Extensions
	- React Developer Tools
	- Redux DevTools
	- (Vue.js devtools)
	- (Angular DevTools)
	- Postman Interceptor
	- JSON Viewer
	- ColorZilla
	- WhatFont
	- Wappalyzer
- Productivity tools
	- PowerToys
	- WSLtty
	- DevToys
- AI
	- Copilot
	- Tabnine
	- Codeium

- What about the browsers?
- Online testing places:
	- BrowserStack
	- Sauce Labs
- VNC viewer


Website possible features:
- Flashcards with some nice animation
- Complex navigation. I will experiment my own unique solutions.
- Integrated whiteboard with pan, zoom, edit features
- Mobile version with all the same features, but slightly different
- 3D racing game using webgl or webgpu
- webxr experience


SSR costs?
React, svelte, vue, other?
Kubernetes


# Setup notes:
- Backing up everything?
## Docker Desktop
"Allow Windows Containers to be used with this installation"?
- From gemini:
	- Doesn't hurt
	- Allow running windows images

Docker Compose
## VS Code Extensions:
### Docker

## Docker in a project:
- (docker init)
- Dockerfile
	- FROM node:22 (node base image)
	- WORKDIR /app
	- COPY package*.json
	- RUN npm install
	- COPY . .
	- ENV PORT=9000
	- EXPOSE 9000
	- CMD ["npm", "start"]
- Dockerignore
	- node_modules
	- .env
- Building:
	- docker build -t <name of image> . 
		- (-t=tag)
		- (fireship suggest using dockerhub name first (kipnuni/<docker_image_name>:<version>))
		- (. means current directory)
- Run
	- docker run -p 9000:9000 <docker_image>
		- (-p = port forwarding)
- Debugging
	- On Docker Desktop
	- docker scout quickview
		- (on terminal, looks for vulnerabilities
- Multi Container Application
	- Separate backend, database, frontend
	- Docker Compose
		- compose.yaml file
			- services
				- backend
				- db
		- Terminal commands:
		- docker compose up
		- docker compose down
	- Docker volume


- Learn UML

