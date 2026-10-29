## What it does

You type `wait-what` when you did not understand a message. The [agent](https://www.aihero.dev/ai-coding-dictionary/agent) then re-pitches what it just said. It adds the context you were missing, writes clearly in Simplified Chinese by default, and uses the vocabulary from your project's `GLOSSARY.md`. Code, commands, logs, error messages, protocol fields, interface names, package names, and paths stay in their original form.

The skill is three lines long. That is the design, not an unfinished draft. Skills against verbosity usually fail because they grow too long. A four-hundred-line concision skill still leaves the [model](https://www.aihero.dev/ai-coding-dictionary/model) verbose, because the model copies the length of the skill, not its request. This one has a single precise leading word and nothing else.

## When to reach for it

You invoke it by typing `/wait-what`. The agent will not reach for it on its own, and it shouldn't. Only you know when you stopped following.

Use it as soon as you notice you're skimming. For example, the agent has started to use jargon it invented, put five acronyms in one sentence, or explained a decision whose premise you never saw. It fixes the conversation you're already in. To stop the jargon arriving at all, use [grill-with-docs](https://aihero.dev/skills-grill-with-docs), which builds the shared language upfront.

## The name is the mechanism

The leading word is **wait**. "Be concise" is an instruction about the agent's output, and the model obeys it by clipping words and losing you further. **Wait** is about *your* state. It says you stopped understanding here. An agent that hears "be brief" writes clipped fragments. An agent that hears "wait, you lost me" backs up and explains.

That difference is the whole skill. Every popular fix for verbosity names the *output*: `/tldr`, `/no-fluff`, `/talk-normal`. The model over-corrects into clipped fragments that are shorter and no clearer. Naming the *listener* asks for both halves at once: fewer words **and** the context you were missing.

The skill says re-pitch **that**, not "that last message". What lost you is usually bigger than one paragraph, so the agent decides how far back to go.

## It plugs into the language you already have

The body asks for a clear explanation in Simplified Chinese and reuses the vocabulary in your project's `GLOSSARY.md`. The ubiquitous language supplies the nouns, while technical identifiers and other original material stay unchanged.

If you have no `GLOSSARY.md` (and no `GLOSSARY-MAP.md` pointing to one for the context at hand), the skill still works. You lose only the domain-vocabulary half.

## It's working if

- The re-pitch is **shorter and clearer**, not shorter and blunter.
- It adds the premise you were missing, instead of only deleting words.
- The explanation defaults to Simplified Chinese, while technical identifiers and original material remain unchanged.
- Project nouns replace invented ones. The terms in your `GLOSSARY.md` come back.
- You can use it twice in a row, and it does not degrade into terseness.

## Where it fits

You can use `wait-what` at any point, in any conversation, inside any other skill. It repairs one message after the fact. The real fix is a shared language agreed upfront, and that is [grill-with-docs](https://aihero.dev/skills-grill-with-docs): a [grilling](https://www.aihero.dev/ai-coding-dictionary/grilling) session that runs [domain-modeling](https://aihero.dev/skills-domain-modeling) as it goes, so it records the words you both use in your `GLOSSARY.md`. If you're unsure which skill fits the moment, [ask-matt](https://aihero.dev/skills-ask-matt) routes you.
