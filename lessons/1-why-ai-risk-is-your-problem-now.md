## Lesson 1 — Why AI Risk Is Your Problem Now

*Module 1 · Day 1 (Foundation + Frameworks)*

> **Source note:** This lesson is built from the public syllabus of *Owning AI Risk: Hands-On Playbooks* (Antisyphon Training) and from Kip Boyle's public material: the book *Gears Don't Guess* and the  Cyber Risk Management Podcast episodes 181, 210, 212 and 219. 

### Learning Objectives

By the end of this lesson you should be able to:

- Explain why AI behaves differently from the "deterministic" technology most governance habits were built for.
- Describe the three forces that bring AI risk into an organization: **people**, **vendors**, and **agents**.
- Explain why most organizations face AI risk as **buyers** of AI, not builders, and what that means for their attack surface.
- Recognize **third-party** and **fourth-party** AI risk and give real examples.
- Build a one-page AI risk map for your organization and rank the three forces by exposure.
- Add AI to an existing risk register without inventing a parallel process.

### Who This Lesson Is For

The course is aimed at security, risk, audit, privacy, and IT professionals who have just been made responsible for AI risk, often without asking for it. You do not need an AI or coding background. You do need to be able to talk about your organization's security or risk program at a working level. If you have ever kept a risk register, sat in a vendor review, or written a policy, you already have most of the skills you need. This lesson's job is to help you point those skills at AI.

### Key Terms

- **Artificial intelligence (AI):** Broadly, software that performs tasks that normally need human judgment. In this course it mostly means **generative AI**: systems that produce text, images, audio, or code in response to a prompt.
- **Large language model (LLM):** The kind of model behind tools such as ChatGPT, Claude, Gemini, and Microsoft Copilot. It predicts likely next pieces of text based on patterns learned from large amounts of training data.
- **Prompt:** The instruction or input a person, or another system, gives to an AI tool.
- **AI agent:** An AI system that can do more than chat. It can take actions, such as reading files, calling APIs, sending email, browsing the web, or running code, often across several steps with little human involvement.
- **Shadow AI:** AI tools or features used inside an organization without its knowledge or approval. It is the AI version of "shadow IT."
- **Risk:** The chance something bad happens multiplied by how bad it would be. This is the classic *probability × impact* framing.
- **Risk register:** A living list of identified risks, each with an owner, a rating, a treatment decision, and a review date.
- **Third party / fourth party:** A third party is your vendor. A fourth party is your vendor's vendor, a company you may never have heard of that still touches your data.

### Gears vs. Guessers: Why Old Instincts Misfire

Kip Boyle's book *Gears Don't Guess*, which his podcast episode 219 discussed, opens with a simple contrast that is worth absorbing before anything else.

**Traditional systems are "gears."** Give a calculator, a firewall rule, or a payroll process the same input and you get the same output every time. Because that behavior is predictable, managers have learned a reliable habit: set it up, test it, trust it, and check it periodically. Most control frameworks, audit approaches, and approval workflows quietly assume this kind of determinism.

**AI is probabilistic.** An LLM generates its answer by predicting what is statistically likely. The same prompt can give different answers minutes apart, even from the same model. It can produce confident, fluent text that is simply wrong. This is usually called a **hallucination**. Episode 181 stresses that this makes human review of outputs essential in high-stakes work, such as a court filing, while lower-stakes uses, such as drafting a podcast script, can tolerate more error.

**Why this matters to you:** A control that says "we tested it once, so it works" does not hold for a system that guesses. You need controls that assume variable behavior: review steps, monitoring, limits on what the system can touch, and a way to catch and log mistakes.

The book's central reassuring point is that leaders **do not need to learn AI from scratch**. They need to adapt the risk management they already practice to a system that guesses. Risk is still probability times impact, and it is still managed on a gradient, not as a yes/no switch.

### The Ban-vs-Embrace Trap

When AI arrives, leaders often swing to one of two extremes:

1. **Ban it.** This feels safe. In practice, people who find AI useful keep using it on personal accounts, personal phones, and personal credit cards. Usage goes underground and becomes shadow AI, so you lose visibility and gain no control. Episode 181 makes the same point: banning AI is largely ineffective. The real choice is whether you govern AI use or not.
2. **Embrace it wholesale.** This feels competitive. It also exposes the organization to risks nobody has examined: data leakage, contract and privacy violations, and unreviewed vendor access.

The book describes a CFO who banned AI after a competitor's public misfire, then came under pressure from her CEO when a rival used AI to speed up a core business cycle. Her options looked like "fall behind" or "accept exposure." The lesson is that a **middle path** exists: govern AI at the level of specific use cases, scale controls to the risk of each use, and make the approved path fast enough that people prefer it.

> **Mental model:** Governance should **accelerate** adoption, not block it. That is the first of the book's six parts. If your governance is so slow that people route around it, it is producing shadow AI, not preventing it.

### The Three Forces: People, Vendors, Agents

The syllabus organizes AI exposure into three forces. Each is a different channel through which AI, and its risk, enters your organization.

#### Force 1 — People

Employees and contractors using AI tools directly, approved or not.

Typical exposures:

- Pasting confidential data, such as customer records, source code, contracts, or strategy documents, into a public AI tool whose terms let the vendor keep or train on inputs. Episode 181 notes that free tools often retain what users submit.
- Relying on hallucinated output in decisions or documents without review.
- Signing up for AI tools with a company card and expensing them. This is the subject of Lesson 2.
- Granting a small AI app access to corporate email, calendar, or files through a single "Sign in with Google/Microsoft" click, known as an OAuth grant.

What makes this force hard: it is spread across every department, and it is driven by people trying to do their jobs better, not by bad actors.

#### Force 2 — Vendors

AI that arrives through software you buy, whether or not you asked for the AI part.

Typical exposures:

- **AI features switched on inside existing SaaS.** Episode 219 highlights a general counsel's pain point: AI often arrives as an unannounced feature in software you already use, so it never goes through contract or governance review.
- Enterprise AI products, such as Microsoft Copilot, ChatGPT Enterprise, Claude Enterprise, and Gemini for Workspace, that are configured with risky defaults.
- **Supply-chain and fourth-party risk:** the libraries, hosting providers, and sub-processors underneath your vendors.

What makes this force hard: you inherit risk you cannot see, under contracts you did not fully negotiate.

#### Force 3 — Agents

AI systems that **act**, not just answer: they read and write files, call APIs, send messages, and chain steps together.

Typical exposures:

- Agents running with a human's credentials or broad shared credentials, so their actions cannot be told apart from the human's.
- Agents that combine private data, untrusted input such as email or web pages, and the ability to take action. Lesson 5 covers this as the "lethal trifecta."
- Long-running agents producing hundreds of actions that nobody reviews.

What makes this force hard: agents move at machine speed and break the old identity assumption that one human stands behind every action. This force is newer than the other two, but it is growing fastest.

### Why You Are a Buyer, Not a Builder

Most AI governance advice is written for organizations that **build** models. Episode 212 argues that most organizations instead **buy** AI: Copilot, ChatGPT Enterprise, Claude Enterprise, or AI bundled into SaaS they already use. That changes where the risk lives.

- **Buying AI means inheriting everything beneath it:** every library, default setting, and sub-vendor. Your attack surface gets bigger, not smaller.
- **The model is a small part of the system.** Episode 212 cites an analysis of Claude Code suggesting the model was only about 20% of the system. The remaining roughly 80% was "plumbing": session management, permissions, crash recovery, budgeting, and observability. Failures usually happen in that plumbing, not in the model.
- **Configuration is where risk lives.** Episode 212 points to Microsoft research from May 2026 finding that the main risks in AI apps come from setup: default settings, disabled authentication, and unsecured public interfaces.

The podcast's framing, which is the title of episode 212, is worth remembering: *the AI worked; the process didn't.*

### Real Incidents That Illustrate the Three Forces

Episode 212 walks through three 2026 incidents. As summarized from the episode:

| Incident | What happened (summary) | Force it illustrates | Lesson for buyers |
|---|---|---|---|
| Anthropic Claude Code source exposure (March 2026) | A build/packaging configuration mistake published product source code to a public registry, despite strong AI-layer safeguards | Vendor (process failure at a supplier) | Strong AI controls don't stop a plain release-pipeline error. Ask vendors about release discipline. |
| Mercor via LiteLLM (late March 2026) | Attackers used stolen credentials to publish malicious versions of LiteLLM, a popular open-source library. Automated builds that pulled the latest version were compromised | Vendor / supply chain | Your AI stack depends on open-source components you don't control. Pinning versions and scanning dependencies still matter. |
| Vercel via Context.ai (April 2026) | One employee granted a small AI productivity tool OAuth access to their work Google account. Malware at that tool stole the token, and attackers pivoted into Vercel | People and fourth-party | One unreviewed OAuth click can open the door. Your vendor's vendor's security becomes yours. |

**Fourth-party risk and transitive trust.** The Vercel case shows risk you never consented to. You trust your vendor, your vendor trusts its vendor, and so on. Episode 212 compares this to telling a secret to a friend, who tells their cousin. You never chose the cousin, but your secret now depends on them.

### The Top AI Risk Categories (Buyer's View)

Episode 181 names three top cyber risks of AI. They make a useful starting checklist for your risk map:

1. **Data leakage and exposure.** Once data enters a generative AI system, you may not know how it is stored or used. At risk are trade secrets, source code, customer data, and proprietary processes. Vendor terms help, but a probabilistic model cannot be guaranteed to follow rules every time, and **prompt injection**, meaning manipulating a model with crafted input, can coax data out.
2. **Compliance and regulatory violations.** Existing privacy laws such as GDPR, HIPAA, and CCPA still apply when AI processes personal data. AI-specific rules such as the EU AI Act and some U.S. state laws add a second layer.
3. **Unauthorized access and authentication weaknesses.** Most AI tools are browser-based SaaS. Weak authentication and leaked **API keys** are a real concern: anyone holding a key can use it and run up charges.

Add two more from the wider material:

4. **Output integrity.** Hallucinations and errors flow into decisions, code, or customer communications.
5. **Excessive agency.** Agents with more permissions than their task requires. This term comes from the OWASP Top 10 for LLM Applications.

### Building the One-Page AI Risk Map

The syllabus outcome for Module 1 is a **one-page AI risk map** for your organization that identifies which of the three forces is biggest. Below is a practical way to build one.

> **Reconstruction:** The layout, fields, and 1–5 scales below are my own design to deliver the syllabus outcome. The instructor's in-class worksheet may differ.

#### Step 1 — Set the frame (5 minutes)

Write the organization or business unit, the date, your name as preparer, and the decision this map supports. A typical decision is: "Where should I spend my first 90 days?"

#### Step 2 — Brainstorm exposures under each force (15 minutes)

For each force, list concrete ways AI is or could be present. Ask the question episode 210 proposes as the key governance question: **where are we using AI today?** Include unapproved use.

Prompts to get you going:

- **People:** Which teams are most likely using AI on their own, such as marketing, sales, HR, engineering, legal, and finance? What sensitive data do those teams handle?
- **Vendors:** Which of your top 20 SaaS vendors have added AI features in the last year? Which enterprise AI products are licensed? Who approved their configuration?
- **Agents:** Is anyone running coding assistants, automation platforms, or browser agents with access to production systems or real data?

#### Step 3 — Rate each exposure (10 minutes)

Use simple 1–5 scales:

- **Likelihood:** 1 = rare, 3 = plausible this year, 5 = probably happening now.
- **Impact:** 1 = minor inconvenience, 3 = reportable incident or meaningful cost, 5 = regulatory action, major customer harm, or material financial loss.
- **Score** = Likelihood × Impact, from 1 to 25.

Also note your **confidence** in each rating (Low/Med/High). Low-confidence, high-score items are where you need discovery work first.

#### Step 4 — Roll up and rank the three forces

Compute two numbers per force: the **sum** of exposure scores and the **highest single score**. The sum shows breadth, and the max shows the worst single scenario. Rank the forces and write one sentence explaining the ranking.

#### Step 5 — Name the top three actions

For the top-ranked force, write the next three actions, each with an owner and a date. Keep the actions small and concrete, for example "pull 12 months of card transactions and scan for AI vendors."

#### Example one-page map (fictional mid-size company)

| Force | Exposure | L | I | Score | Confidence |
|---|---|---|---|---|---|
| People | Staff pasting customer data into free chatbots | 4 | 4 | 16 | Low |
| People | AI note-takers recording customer calls without consent | 3 | 4 | 12 | Low |
| Vendors | CRM vendor enabled AI summarization by default | 4 | 3 | 12 | Med |
| Vendors | Copilot rolled out with default permissions over messy SharePoint | 3 | 5 | 15 | Med |
| Agents | Developer coding agent with production database credentials | 2 | 5 | 10 | Low |

Roll-up: People = 28 (max 16); Vendors = 27 (max 15); Agents = 10 (max 10).
**Ranking:** People ≈ Vendors > Agents. Because confidence in the People ratings is low, the first move is discovery: finance records (Lesson 2) and OAuth grants.

### Adding AI to the Risk Register You Already Have

*Gears Don't Guess*, as discussed in episode 219, gives risk managers a deliberately modest first step: **add an AI row to the existing risk register**, using the same taxonomy, the same rating method, and the same review cadence. Don't build a separate "AI risk program" with its own spreadsheet that nobody reviews.

Why this works:

- It signals that AI risk is ordinary business risk, which is the core message of Boyle's work.
- Executives already know how to read the register.
- It pulls AI into existing review meetings without new overhead.

A good register entry includes: a risk statement ("If staff paste confidential data into unapproved AI tools, then that data may be retained by third parties, leading to contractual breach and loss of trade secrets"), an owner, a likelihood/impact rating, current controls, a treatment decision (accept, mitigate, transfer, avoid), and a review date.

Over time, split the single AI row into the specific exposures from your risk map.

### Connecting to Established Frameworks

You do not need to adopt a framework before you start, but it helps to know where your work fits:

- **NIST AI Risk Management Framework (AI RMF 1.0):** Organized into four functions: **Govern** (culture, roles, policies), **Map** (understand context and identify risks), **Measure** (analyze and track risks), and **Manage** (prioritize and act). The risk map in this lesson is a lightweight **Map** activity. Boyle's podcast covered the AI RMF in episodes 153–154 and favors its principles-based flexibility.
- **ISO/IEC 42001:** A certifiable standard for an AI management system, similar in spirit to ISO 27001 for information security.
- **EU AI Act:** A risk-tiered regulation that classifies AI systems as unacceptable, high, limited, or minimal risk, with obligations that grow with the tier.
- **OWASP Top 10 for LLM Applications:** A list of common technical weaknesses, such as prompt injection, sensitive information disclosure, and excessive agency. It is useful vocabulary even for buyers.

### Common Gotchas

- **Mapping only approved tools.** The point of the map is to surface what you *don't* know. Mark low-confidence areas honestly.
- **Treating "AI" as one risk.** A meeting-notes tool and a coding agent with production access are completely different risks. Map by use, not by "AI in general."
- **Ignoring vendor-embedded AI.** Many organizations' largest exposure is AI that quietly arrived inside existing software.
- **Over-engineering the scoring.** A 1–5 scale and a conversation beat a 40-factor model nobody understands. The map is for prioritizing, not for precision.
- **Starting with a ban.** Bans drive usage underground and destroy the visibility you need.
- **Forgetting speed.** Boyle uses the phrase "speed is the new firewall" in his podcast. AI-assisted attacks move quickly, so detection and response speed is part of your risk posture.

### Key Takeaways

- AI is a **probabilistic** system that guesses. Controls built for deterministic "gears" need to be adapted, not discarded.
- **Banning AI creates shadow AI.** Embracing it wholesale creates unexamined exposure. Govern by use case instead.
- AI risk arrives through three forces: **people**, **vendors**, and **agents**. Rank them for your organization rather than assuming.
- Most organizations are **buyers** of AI. Their risk lives in configuration, vendor processes, and supply chain, the "plumbing," more than in the model.
- **Fourth-party risk** is real: one OAuth grant to a small AI tool led to a major breach in the Vercel case.
- Build a **one-page risk map**, rate likelihood × impact, note confidence, and turn the top force into three concrete actions.
- Start by **adding AI to your existing risk register**, not by building a parallel program.

### Sources

- [Owning AI Risk: Hands-On Playbooks — Antisyphon Training (syllabus)](https://www.antisyphontraining.com/product/owning-ai-risk-hands-on-playbooks/)
- [Cyber Risk Management Podcast EP 219: Why Gears Don't Guess](https://cr-map.com/podcast/219/)
- [Cyber Risk Management Podcast EP 212: The AI Worked. The Process Didn't.](https://cr-map.com/podcast/212/)
- [Cyber Risk Management Podcast EP 210: How Boards of Directors Are Thinking About Generative AI](https://cr-map.com/podcast/210/)
- [Cyber Risk Management Podcast EP 181: Deploying AI Securely and Privately](https://cr-map.com/podcast/181/)
- [NIST AI RMF — AI Resource Center](https://airc.nist.gov/airmf-resources/airmf/)
- [Gears Don't Guess companion site](https://gearsdontguess.com)

