# Using AI tools
## Tools for creation
- Whole code
- Code completion
- Strengths:
	- Creating unit tests+
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
#### Potential
- Read my emails and notify me for everything important
	- Only local model
- Read RSS feeds and apis and collect interesting material for me
	- News sites
	- Youtube
	- Reddit
- Job opportunities
- Social media
- Research history
- Develop my business
- Develop itself (read ai developments)
	- Make it teach me how to control it
	- Dashboard view of the whole system
- Plan my days and update them. Roadmaps
- Have a light interface open while I work that listens me and I can easily ask it for something.
- It should have access to my notes (obsidian)
	- It could have write access and it could communicate by the notes
- It constantly asks questions for me to clarify what I want
	- Gamify it
- Anki usage
- It has access to my calendar
- Mac Mini M1
	- Could I use this as the 24/7 machine?
- Main PC that can run more powerful local ais
	- Before this, use online services
- Handle stream notes
	- Audio to transcript
		- ask clarifying questions of it
	- Read the note changes
	- Update the notes on the website
		- show "verified" ones differently
- Character
	- For personal life
	- Neutral
	- It
	- Personality
		- Mental age: 20
		- Energetic and enthusiastic
		- Motivating
		- Aiming for the same goal - World Peace
	- Name?
	- Physical representation?
		- Animal (some social animal on land)
		- Humanoid
- It won't be a mirror of me and will develop it's own personality and history in the future. The knowledge of me will be on it's own place.

- Use tools like creating docx files
- Create dashboards
- Using private online servers?

#### On PC
- Having a constant conversation on
- 24/7 work on a local machine
#### On phone
- Chat through Telegram/Slack


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







