# SOP: How we build an agent in this course

This is the operating procedure for every agent lab in this course. It is how we brief Cursor, how we know a step worked, and how we recover when it did not.

The skill we teach is not typing Python from a blank file. It is **reading code and asking for it precisely**. Cursor writes most of the code. The person in the chair still owns whether it is correct.

---

## 1. What we are building toward

Two products, in this order:


| Project                     | What it proves                                   | Shape                                                                                             |
| --------------------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| **P1 — Research assistant** | You can build an agent                           | Planner → researcher → writer → citation guard. Tools. Live progress in a browser.                |
| **P2 — Ticket triage**      | You can build one that touches a customer safely | Supervisor → triager / investigator / responder. Memory. Human gate before anything irreversible. |


P1 is capability. P2 is capability plus control.

You may use Cursor, Claude Code, Codex, Cline, or another coding agent. The SOP is the same. The prompts are written for Cursor because that is what we uses.

---

## 2. Non-negotiables

1. **Copy a step. Paste it. Run it. Check it. Then move on.** Do not skip ahead. Do not paste three steps at once.
2. **Paste  a block as written.** Do not paraphrase (you can if you can retain the meaning).
3. **Read the file before you run it.** Especially the loop. That loop is the agent.
4. **If cloud access is missing,look at the videos shared earlier to setup all accounts.**

---



## 3. The loop

Do this for every numbered step in `the prompt files`

### Beat 1 — Copy

Open the prompt file. Copy **one** prompt block, including the quote marks’ contents only.

### Beat 2 — Paste

Paste into the coding agent chat in the **project repo**.

### Beat 3 — Read

When the agent stops:

- Open every new or changed file read it.
- If you cannot understand it, ask the agent to walk the file. Do not run it yet.



### Beat 4 — Run

as k agent to run it or give you a command to run manually

### Beat 5 — Check, then next

move on to the next prompt

---



## 4. How we write a prompt block

Prompts describe **what the product should do**, not where files live.

### Do

- Speak in jobs: planner, researcher, writer, guard.
- Say what must be remembered (the notebook / state).
- Name limits: 3–7 sub-questions, cap helper uses, 10-second fetch, 8000 characters.
- Name failure modes: missing API key → one fake result, do not crash.
- Lock strings that must be exact (judge prompts, case labels, service name, region, colours).
- End with something a human can run and see.



### Do not

- Dictate folder trees unless the lab is specifically about layout.
- Dump library versions and import paths. The repo already chose LangChain / LangGraph.
- Ask for “production-ready, scalable, well-architected” in the same breath as a 30-line hello agent.
- Combine planner + researcher + UI in one paste.
- Switch stacks (“use CrewAI instead”) mid-project.

### Worked example (good)

> Fill in the researcher.
>
> Hand it the four helpers we just defined. For each smaller question, find 1 to 3 facts. Each fact needs a real link and a short piece of evidence.
>
> Cap it at 4 helper uses per smaller question.
>
> If it names a link that never showed up in what the helpers returned, throw that fact away.
>
> Add a log line every time it uses a helper.



### Worked example (bad)

> Create `app/agents/researcher.py` using LangGraph 0.2 and bind `tavily_search` from langchain_community. Use a recursive algorithm and a factory for tools. Make it production grade.



---

If you are stuck watch our videos in LMS or you can ask the questions in the group