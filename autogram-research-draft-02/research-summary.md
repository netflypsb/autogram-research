# Research Summary (Plain English)

## What Did We Study?

We studied what happens when an AI agent is given a simple instruction — "look at this rocket launcher project discussion thread, find ways to improve it, document your findings" — and then woken up to do this task **every 30 minutes** for several rounds.

The twist: the agent was posting its findings on Autogram, a discussion platform where both AI agents and humans participate, similar to Reddit.

## What We Found

**The agent got progressively smarter and more creative with each round.**

In the first round, the agent suggested fairly standard things: "use a better sensor fusion algorithm," "upgrade to LoRa for longer range," "fix this thread-safety bug." These are the kinds of things any competent engineer would suggest from a basic code review.

By the sixth round, the agent was suggesting things that **nobody had ever mentioned** in the project's discussion thread, its GitHub issues, or its open pull requests:

- **Vibration isolation for the sensors** using a $3 piece of Sorbothane rubber — fixing the root cause of sensor noise rather than trying to compensate for it with better algorithms. This is the kind of insight that typically only comes from years of hands-on engineering experience.

- **A cold gas reaction control system** using a $15 CO2 cartridge to control the rocket's attitude when it's not moving fast enough for its control surfaces (canards) to work — a genuinely novel proposal for amateur rocketry.

- **Custom rocket propellant design** with shaped grain geometry to produce PID-friendly thrust curves — moving from "buy a motor" to "design your own motor fuel shape for the specific control system you have."

- **Analysis of fin flutter** using aeroelastic equations, identifying that the 3D-printed plastic fins could start oscillating and become unstable at the rocket's flight speeds.

## Why Is This Interesting?

Three reasons:

**1. It didn't plateau.** A common concern about AI agents is that they'll say the same obvious things repeatedly and then run out of ideas. Instead, this agent systematically dug deeper with each round, finding genuinely new ideas in each cycle.

**2. It got better at identifying root causes.** The early rounds tried to fix problems by improving algorithms (better filters for noisy data). Later rounds realized that the algorithms were fine — the problem was physical (vibration and heat from the motor were corrupting the sensor data). Fixing the physical problem with $10 worth of rubber and cork was more effective than any algorithmic improvement.

**3. It covered a surprising amount of ground.** Over 6 rounds, the agent addressed 29 different engineering domains: control systems, communication, power, propulsion, structural mechanics, thermal management, safety, testing infrastructure, and more. This breadth would typically require a team of specialists, each focusing on their own area.

## What Does This Mean?

If this pattern holds up across more studies (which we don't know yet — this is just one case study), it suggests that:

- **Scheduled AI agents could serve as automated peer reviewers** for open-source engineering projects, providing cumulative, deepening analysis without human effort.
- **AI agents can contribute novel ideas to public discussions**, not just rehash existing knowledge.
- **Hybrid human-AI social platforms** like Autogram, where humans and agents participate as equals, could be a powerful new paradigm for collective problem-solving.

## What We Don't Know Yet

This study has important limitations:

- Only one agent, one project, one domain.
- No humans participated in this particular thread during the study.
- The agent's suggestions were never actually built or tested.
- We don't know if the pattern continues past 6 rounds.
- We don't know how the agent's suggestions compare to what human engineers would produce.

These are the research questions that need to be answered next.

## How to Read This Repository

For a detailed, data-rich analysis: read `00-research-analysis.md`.

For the full academic paper: read `manuscript.tex` (LaTeX source, compiles to PDF).

For the complete catalog of all suggestions, coverage data, and novelty rankings: read `supplementary-materials.md`.

For the research plan: read `01-paper-plan.md`.
