# AI University
## 1
- Task: Clearly clarify the end goal
	- "Generate a three..."
	- "Summarize the key..."
	- Always begin with action verbs
- Context: Tailor the response
	- Background info
	- Success (what it looks like)
	- Setting (extra info)
- Examples: Mimic style, structure, and tone
	- Copy-paste a sample text you want the ai to mimic
- Persona: Embody a specific expertise
- Format: Tell AI how to structure the output
	- "Give me bullet points"
	- "End with a clear next-steps section with owners and deadlines"
- Tone: Add emotional context

- Task: Write a follow-up email summarizing a sales call and proposing next steps.
- Context: I’m a B2B SaaS account executive selling to mid-market operations teams. The buyer is concerned about implementation time and internal buy-in. Here is the meeting transcript: [paste meeting transcript].
- Examples: Match the tone and structure of this previous follow-up email: [paste example].
- Persona: Act as a senior sales manager who is concise and persuasive.
- Format: Create 3 short paragraphs followed by bullet-point next steps.
- Tone: Write this in a professional, confident, and helpful tone.

## 2
- Project Files: give AI your context
## 3
- Step 1: Gather your materials
	- Notes or bullet points
	- Existing documents
	- Data or metrics
	- Examples of presentations you like

## 4
My AI stack I dedicate every Sunday to testing and building with AI, so this is constantly getting refined, but here’s what’s sticking right now:
- ChatGPT: Real-time thinking partner for business and life decisions. I also keep Voice mode on while reading to clarify concepts, and use Vision to diagnose broken tech around the house
- Custom GPTs: Chatbots trained on Loom videos, SOPs, and internal docs to onboard new hires. Our motto: "Don't ask questions you haven't asked GPT first"
- Claude: Editor-in-chief for all my long-form writing. Go-to prompt: "make it better"
- Claude Code: Runs live Meta Ads analytics through an MCP server with a memory system that recalls past tests for faster ad iteration
- Lindy AI: Manages my calendar, books meetings via email, and drafts replies for FAQs and common customer questions 
- Notion AI: My project management tool that organizes thoughts into actionable plans and generates pages for our AI tool database
- n8n: Advanced automations like filtering spam emails from genuine customer feedback and pinging appropriate team members in Slack
- Wispr Flow: Turns voice notes into polished writing based on my trained style
- HeyGen + ElevenLabs: Clones my face and voice for my AI avatar — helped me grow to 100k+ Instagram followers without filming myself
- Gemini: Auto-generates timestamps and finds clippable highlights from interviews
- NotebookLM: An AI tool by Google Labs that turns long research papers into engaging podcasts (I’m a nerd and like to listen to this stuff on long walks)
- Cursor/Replit Agent: AI development tools that help me spin up/build simple app prototypes in seconds
- Perplexity Comet: Lets me "chat" with YouTube videos and go into rabbit holes to fully grasp concepts
- Granola: Records, transcribes, and summarizes meetings into action items
- Nano Banana: Quick photo touch-ups that would normally require Photoshop
- Gamma: Instantly converts prompts and outlines into beautiful, structured presentations

# Using AI tools
## Tools for creation
- Whole code
- Code completion
- Strengths:
	- Creating unit tests
	- Documentation
- Make ai do a detailed description plan.md
- Snyk Open Source (DeepCode AI Agent)
	- Scans the generated code for vulnerabilities and compliance issues

Replit AI

Krater.ai
- Contains all ais

SC Training
- Create courses/training

### Claude Code
- On terminal using npm
- Todo lists. Shows what it will do and cross them when it does
- Bash commands without leaving to another tab in terminal. Handy.
- Documentation
- Either manual ask/accept or auto when moving from phase to phase
- Screenshots as input (for example error messages)
- Claude.md: programming and project rules it follows
- Message queue
- Plan mode before proper work
- Different "think 'how hard'" options for how long it will think
- Web search feature
- Change tracking, log
- Integration with Github Actions
- Parallel instances running at the same time
	- For bugs for example
	- Use git worktrees 
- Custom commands file for repeating commands
- Subagents: specialized agents for small tasks that Claude controls (like testing)
- MCP (Model Context Protocol): access database, or enable claude to "see" browser window, etc

### AI agents
- GitHub Copilot
	- !!! Use /create-prompt to generate a reusable prompt file with the agent

- Tabnine
	- Most private
	- "Air-gapped"

- Cursor
	- Cursor > Copilot by metrics
		- BYOK (Bring your own key)

- Amazon Q Developer


## Tools for productivity
### Learning
- Notebooklm
	- What is it?
	- What problem does it fix?
	- How could it be better?
- General chatbots for learning
	- Prompt templates

- How do I connect my notes with AI?
	- On pc (using obsidian)
	- Notion?

Studypdf
- Upload the material and study with ai


Search engines
+ Exa
	+ Can receive url and give similar topic and feeling websites
+ Perplexity AI
+ Andi
+ DuckDuckGo
+ Google AI mode

#### Extensions
- Mapify
	- Creates mind map from the website content for easier learning
- Scholarcy
	- Creates easy to understand cards from complex website text
- Monica
	- Inline chat, summarization, translation

#### Note taking
- Notion AI
- Obsidian + plugins

#### Language learning
Grammarly
- Fixes typos and suggests edits
	- Browser extension, app, on mobile

LanguageTool
- For grammar checks

#### Text-to-audio
- Speechify
- ElevenLabs Reader

#### Legal purposes
- Jurismetic AI
- LegesGPT
- Streamline AI
- Sonix

#### Math and physics
- Wolfram Alpha

#### Listener in a meeting/conversation
- Otter.ai
	- Otter pilot can join a meeting in your behalf
- Zoom AI Companion
- Taskade
### PC workflow
- Asking about anything in a separate window
	- conversations are saved
	- no difficulties navigating, always goes back to ready to write
		- browser is bad
		- cli best
			- copilot cli?
	- needs to be open at all times
- Ask quick questions where I don't care about the history
	- use separately from separate window
	- also a separate window

- Different windows (+color coded) for different agents

- Excalidraw and Miro AI integration
	- Create diagrams from text notes

#### Automated tools
- Automated engines
	- n8n
	- Zapier
	- Make (formerly Integromat)
	- Pipedream
- Apis
	- What are there?
	- Top 10:
		1. http
		2. OpenAI
		3. PostgreSQL/MySQL
		4. Ollama
		5. Google Sheets
		6. Slack/Telegram
		7. WhatsApp Business
		8. Pinecone/Milvus/Supabase (Vector Database)
		9. 
#### Gemini cli
- npm install -g @google/gemini-cli
- GEMINI.md file

##### AIChat using gemini
- edited ~/.config/aichat/config.yaml
	- stream: true; highlight: true; wrap: auto
- alias ask='aichat -f context.md'

### AI assistant
#### On PC
- Having a constant conversation on
#### On phone



# Building AI
- MCP researching

- RAG: Retrieval-Augmented Generation
	- Searches the data from a source
	- Adds the data into the prompt
	- The prompt uses llm with the added data

- Vector Database:
	- Instead of using structured/stiff data like tables, the data is turned into a data that can be queried "smartly"
	- The process of turning a piece of data (like a sentence) into a vector is called **Embedding**.

# New AI







