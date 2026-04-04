# Research Log — Vibe Coding Blind Spots

## Scoping

**User prompt**: Non-technical person building small tools with AI. Wants to learn
engineering primitives that are essential but invisible to vibe coders — things
that, if you don't know them, you can't even tell when AI-generated code is
dangerously wrong.

**Key insight for scoping**: The user isn't asking "teach me to code." They're
asking: "What concepts do I need so that my collaboration with AI is safer and
more effective?" This means the primitives need to be:
- Learnable without learning to code from scratch
- High-leverage: ignorance creates real risk, not just suboptimal code
- Things the AI won't spontaneously teach you (because you don't know to ask)

**The angle I'm pursuing**: The most dangerous blind spot for vibe coders is
**state and side effects** — the distinction between code that computes something
and code that changes something in the world. This is where the real risk lives:
you can't tell by reading AI output whether code is safe to run twice, whether it
handles partial failure, or whether it's making irreversible changes.

But I want the survey phase to challenge this thesis. Maybe there's a more
fundamental or more practical primitive cluster. Possible alternatives:
- The execution environment (paths, dependencies, OS state)
- Security boundaries (what runs where, who can see what)
- The concept of a "contract" or interface (what code promises vs what it does)

### Questions for investigation

1. **What do experienced developers report as the most common failure modes in
   vibe-coded / AI-generated software?** — Not theoretical risks, but actual
   patterns of breakage people have observed.

2. **What engineering concepts have the highest "danger-to-invisibility ratio" for
   non-technical AI users?** — i.e., concepts where (a) ignorance causes real
   harm and (b) the concept is genuinely non-obvious / wouldn't be discovered
   through normal vibe-coding practice.

3. **How do state, side effects, and idempotency manifest in the "small personal
   tools" context?** — The user builds small tools, not distributed systems. What
   does "state management" actually look like at that scale? File corruption?
   Double-sending? Lost data?

4. **What mental models separate "dangerous vibe coding" from "safe vibe coding"?**
   — Not "learn to program" but "learn to think about programs." What's the
   minimum conceptual toolkit?
