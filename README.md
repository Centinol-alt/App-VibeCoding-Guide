# App-Vibe-Coding-Guide

## Getting Started
To begin vibe coding, you only need two tools:  
- **Grok 3 Thinking**  
- **Cursor with Claude Sonnet 3.7 Thinking**  

Setting up everything correctly is key. If you’re serious about creating a fully functional and visually appealing game, take the time to establish a solid foundation.  

**Key Principle:** *Planning is everything.* Do NOT let the AI plan autonomously, or your codebase will become an unmanageable mess.

---

## Setting Up Everything

### 1. App Design Document
- Take your app idea and ask **Grok 3 Thinking** to create a simple **App Design Document** in Markdown format (`.md`).  
- Review and refine the document to ensure it aligns with your vision. It’s fine if it’s basic—the goal is to give your AI context about the app’s structure and intent.  

### 2. Tech Stack and `.cursor/rules`
- Ask **Grok 3 Thinking** to recommend the best tech stack for your app (e.g., React, Svelte etc).  
  - Challenge it to propose the *simplest yet most robust stack possible*.  
- Prompt Grok to write a set of 6-10 rules for Cursor as if it’s a senior app developer specializing in your chosen stack.  
  - Ensure one rule emphasizes **modularity** (multiple files) and avoids a **monolith** (one giant file).  
  - Example: Rules might include best practices for networking
  - *This is mandatory if you want a app that is as optimized as possible, and code as clean as possible.*


### 3. Implementation Plan
- Provide **Grok 3 Thinking** with:  
  - The App Design Document  
  - The tech stack recommendations
  - The Cursor rules  
- Ask it to create a detailed **Implementation Plan** in Markdown (`.md`) which is a step-by-step instructions for your AI developers.  
  - Steps should be small and specific.  
  - Each step must include a test to validate correct implementation.  
  - No code—just clear, concrete instructions.  
  - Focus on the *base app*, not the full feature set (details come later).  

### 4. Memory Bank
- Create a new folder, open it in Cursor, create another folder, name it`memory-bank`.  
- Add the following files:  
  - `game-design-document.md`  
  - `tech-stack.md`  
  - `implementation-plan.md`  
  - `progress.md` (for tracking completed steps)  
  - `architecture.md` (for documenting file purposes)  

### 5. Setup `.cursor/rules`
- In Cursor, press `Cmd + Shift + P`, type "rules", and hit Enter.  
- Input the rules generated by Grok 3 from Step 2.  

---

## Vibe Coding the Base App
Now the fun begins!

### Making sure everything is clear
- Select **Claude Sonnet 3.7 Thinking** in Cursor. 
- Prompt: Read all the documents in `/memory-bank`, is implementation-plan.md` clear? What are your questions to make it 100% clear for you?
- He usually asks 9-10 questions, answer them and prompt him to edit the `implementation-plan.md` accordingly, so it's even better.

### Your first implementation prompt
- Select **Claude Sonnet 3.7 Thinking** in Cursor.  
- Prompt: 
``` bash
Read all the documents in `/memory-bank`, and proceed with Step 1 of the implementation plan. I will run the tests. Do not start Step 2 until I validate the tests. Once I validate them, open `progress.md` and document what you did for future developers. Then add any architectural insights to `architecture.md` to explain what each file does.
```

**Alternative prompt:**
``` bash
Read all the documents in /memory-bank, and proceed with Phase 1 of the implementation plan. Once Phase 1 is complete open progress.md and document what you did for future developers. Then add any architectural insights to architecture.md to explain what each file does but don't include any code.
```

- **Extreme vibe:** Install [Superwhisper](https://superwhisper.com) to speak casually with Claude instead of typing.  

### Workflow
- After completing Step 1:  
- Commit your changes to Git (if unfamiliar, ask Grok 3 for help).  
- Start a new composer (`Cmd + N`, `Cmd + I`).  
- Prompt: Now go through all files in the memory-bank, read progress.md to understand prior work, and proceed with Step 2. Do not start Step 3 until I validate the test.
- Repeat this process until the entire `implementation-plan.md` is complete.  

---

## Adding Details
Congratulations, you’ve built the base app! It might be rough and lack features, but now you can experiment and refine it.  
- For each major feature, create a new `feature-implementation.md` file with short steps and tests.  
- Implement and test incrementally.  

---

## Fixing Bugs and Stuckness
- If a prompt fails or breaks the app:  
- Click “restore” in Cursor and refine your prompt until it works.  
- For errors:  
- **If JavaScript:** Open the console (`F12`), copy the error, and paste it into Cursor—or provide a screenshot for visual glitches.  
- **Lazy Option:** Install [BrowserTools](https://browsertools.agentdesk.ai/installation) to skip manual copying/screenshotting.  
- If stuck:  
- Revert to your last Git commit (`git reset`) and retry with new prompts.  
- If *really* stuck:  
- Use [RepoPrompt](https://repoprompt.com/) and ask **Grok 3 Thinking** for assistance.  

---

## Other Tips
- **Small Edits:** Use Claude Sonnet 3.5.  
- **Great Copywriting:** Use GPT-4.5.  
- **Better prompt outputs:** Add “think as long as needed to get this right, I am not in a hurry. What matters is that you follow precisely what I ask you and execute it perfectly. Ask me questions if I am not precise enough."
