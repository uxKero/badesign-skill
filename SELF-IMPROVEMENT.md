# Self-improvement

**Teach your agent to stop repeating design failures.**

BADESIGN gives a model design judgment. Self-improvement goes one step further: it turns the research on how AI interfaces fail into rules your agent keeps, and adds a new rule every time one of its designs is corrected. The skill never loads this file. Use it when you want your agent, or yourself, to get better with every project.

## The loop

| Step | What happens |
|:--|:--|
| **1. Learn** | The agent reads this guide and the papers that apply to the project. |
| **2. Distill** | It writes short design rules, each naming the failure it prevents and what to do instead. |
| **3. Keep** | It saves those rules in the file it reads at the start of every session. |
| **4. Record** | Every rejected or corrected design becomes a new failure and a new rule in the same file. |

Where the rules live:

| Agent | File |
|:--|:--|
| Codex | `AGENTS.md` |
| Claude Code | `CLAUDE.md` |
| Cursor | `.cursor/rules/` |
| Any agent | The project's `DESIGN.md` |

## Start it

Give this to your agent once per project:

```
Read SELF-IMPROVEMENT.md from the BADESIGN repository and the linked papers that matter for this project.
Turn what applies here into short, concrete design rules, each naming the failure it prevents and what to do instead.
Save them where you keep lasting instructions for this project: AGENTS.md for Codex, CLAUDE.md for Claude Code, .cursor/rules for Cursor, or the project's DESIGN.md.
Keep only rules that apply to this project. Whenever a design of yours is rejected or corrected, add that failure and the rule that prevents it to the same file.
```

## Why it works

- **Written lessons carry forward.** Agents do not remember past sessions, but they read their instruction files every time. Agents that store a short reflection on each failure and read it on the next attempt improve without retraining.
- **Evidence beats self-review.** A lesson is worth keeping when it comes from something observable: a rejected design, a render, a measured contrast ratio, a failed test. Rereading its own output without new evidence rarely shows a model the real problem.
- **Checks beat impressions.** Rules written as concrete yes or no checks are followed and verified more reliably than general quality goals.

## For developers and designers

Most design failures in AI-assisted work are not matters of taste. They are known, documented and preventable. Start with the anti-patterns below, then open the research closest to your problem.

## Anti-patterns to never repeat

Patterns that appear so often in AI-generated UI that they read as no decision at all. Most come from the same source: the model returns the most common interface in its training data.

| Pattern | How to spot it |
|:--|:--|
| Purple, indigo or violet-to-blue accent | Accent hue between roughly 250 and 290 in OKLCH, or gradients between those hues, with no brand reason |
| One hue family for the whole palette | Every surface and accent within a narrow hue range: all slate, all beige, all purple |
| Dark ground with a neon accent | Near-black background plus one saturated accent, chosen for a product used in normal light |
| Decorative effects | Gradient text, glows, glass panels, blurred blobs, grid or dot backgrounds |
| Everything in a card | Most sections framed with border, radius and shadow; cards nested inside cards |
| Icon feature rows | Three or more identical blocks with an icon in a tinted square, a title and two lines |
| Stat tile rows | Big numbers in boxes that are not the point of the screen, captions that repeat the number |
| Template hero | Centered headline with a badge above it, one highlighted word, a wall of logos |
| Eyebrow labels | Small uppercase tracked text above every heading, numbered section labels |
| Pills on metadata | Rounded badges on ordinary information such as dates, categories or counts |
| Self-describing interface | A subtitle under every heading, text explaining how to use the screen |
| Fake chrome | Drawn phone frames, fake status bars, fake browser windows, terminal dots |
| Border plus wide shadow | A hairline border and a large soft shadow on the same element |
| Tiny grey text | Body or labels under 12px, or grey text below 4.5:1 contrast |
| Motion everywhere | Fade-and-rise on every section, pulsing dots, marquees, scale on hover |
| Layout defects | Misalignment, overlapping text, content clipped or overflowing its container |
| Missing requirements | Parts of the brief that are absent or do not work, hidden behind a polished first screen |

## The research behind it

Every entry links to the original paper or guideline.

### Why generated interfaces look alike

- [Verbalized Sampling: How to Mitigate Mode Collapse and Unlock LLM Diversity](https://arxiv.org/abs/2510.01171), Zhang et al., 2025. Preference data rewards typical answers, which pulls models to the mode. Asking for several candidates with their probabilities recovers diversity.
- [Artificial Hivemind: The Open-Ended Homogeneity of Language Models](https://arxiv.org/abs/2510.22954), Jiang et al., NeurIPS 2025. Different model families give 71 to 82% similar answers to open prompts, and higher temperature barely helps.
- [NoveltyBench: Evaluating Language Models for Humanlike Diversity](https://arxiv.org/abs/2504.05228), Zhang et al., 2025. Larger models are often less diverse than smaller ones in the same family.
- [Base Models Beat Aligned Models at Randomness and Creativity](https://arxiv.org/abs/2505.00047), West and Potts, 2025. Alignment favors pleasant, narrow outputs over original ones.
- [Understanding the Effects of RLHF on LLM Generalisation and Diversity](https://arxiv.org/abs/2310.06452), Kirk et al., ICLR 2024. RLHF improves generalization and reduces output diversity.
- [Interrogating Design Homogenization in Web Vibe Coding](https://arxiv.org/abs/2603.13036), Shin et al., 2026. Models produce a global average aesthetic and even justify it against local design norms; concrete context before generating is the counterweight.
- [Examining and Addressing Barriers to Diversity in LLM-Generated Ideas](https://arxiv.org/abs/2602.20408), Deng et al., 2026. Early outputs fixate later ones, and ordinary personas diversify better than famous-expert personas.
- [The Effects of Generative AI on Design Fixation and Divergent Thinking](https://arxiv.org/abs/2403.11164), Wadinambiarachchi et al., CHI 2024. A single example gets copied and narrows the ideas that follow.
- [When AI Designs AI: Innovation or Imitation?](https://arxiv.org/abs/2608.17471), Yang et al., 2026. 96.8% of the methods designed by agents fell inside designs humans had already made, and nearly half replicated existing ones: agents recombine far more than they invent.
- [Creativity from Friction: Human-AI Interaction for Exploratory Structural Design](https://arxiv.org/abs/2607.07521), Maia Avelino et al., ICML 2026 Workshop on Human-AI Co-Creativity. Good tools remove repetitive friction but keep the reflective friction where design decisions are actually made.
- [Antislop: Identifying and Eliminating Repetitive Patterns in Language Models](https://arxiv.org/abs/2510.15061), Paech et al., 2025. Some patterns appear over 1,000 times more often than in human work; detecting them after generation works better than banning them in the prompt.

### Learning from failure

- [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366), Shinn et al., 2023. Agents that write a reflection after each failure and keep it in memory improved without any retraining, reaching 91% on HumanEval against 80% for the previous best.
- [fAIlureNotes: Supporting Designers in Understanding the Limits of AI Models for Computer Vision Tasks](https://arxiv.org/abs/2302.11703), Moore, Liao and Subramonyam, 2023. A failure exploration tool let designers see where a model breaks for specific users and contexts, and assessed that performance better than interactive model cards.
- [Vision-Guided Iterative Refinement for Frontend Code Generation](https://arxiv.org/abs/2604.05839), Sansford et al., 2026. A visual critic on the rendered page raised quality up to 17.8% over three cycles; refining without looking at the render gained 1.5%.
- [ReLook: Vision-Grounded RL with a Multimodal LLM Critic for Agentic Web Coding](https://arxiv.org/abs/2510.11498), Li et al., 2025. Accepting only revisions that improve prevents the loop from degrading.
- [Zero-Shot Prompting Approaches for LLM-based Graphical User Interface Generation](https://arxiv.org/abs/2412.11328), Kolthoff et al., 2024. Self-critique beat retrieval and prompt decomposition; two loops were enough.
- [DesignRepair: Dual-Stream Design Guideline-Aware Frontend Repair with Large Language Models](https://arxiv.org/abs/2411.01606), Yuan et al., ICSE 2025. Checking rendered, computed styles against component guidelines finds and repairs violations reliably.
- [Improving User Interface Generation Models from Designer Feedback](https://arxiv.org/abs/2509.16779), Wu et al., CHI 2026. Localized fixes taught models more than rankings or scores.
- [Learning to Detect UI Principle Violations via Reinforcement Learning](https://arxiv.org/abs/2607.20690), Mehta et al., 2026. A practical checklist of 19 principles across accessibility, deceptive patterns, perception and composition.
- [Generative UI: LLMs are Effective UI Generators](https://arxiv.org/abs/2604.09577), Leviathan et al., 2026. The statement of design philosophy was the most valuable part of the prompt, and recurring mechanical errors were fixed in code instead of more rules.
- [Self-Refine: Iterative Refinement with Self-Feedback](https://arxiv.org/abs/2303.17651), Madaan et al., NeurIPS 2023. The original generate, critique and refine loop.
- [Large Language Models Cannot Self-Correct Reasoning Yet](https://arxiv.org/abs/2310.01798), Huang et al., ICLR 2024. Without external evidence, self-correction often makes results worse.
- [When Can LLMs Actually Correct Their Own Mistakes?](https://arxiv.org/abs/2406.01297), Kamoi et al., TACL 2024. Self-correction works when reliable external feedback is available.
- [TICKing All the Boxes: Generated Checklists Improve LLM Evaluation and Generation](https://arxiv.org/abs/2410.03608), Cook et al., 2024. Yes or no checklists derived from the request improve both refinement and judging.
- [Checklists Are Better Than Reward Models For Aligning Language Models](https://arxiv.org/abs/2507.18624), Viswanathan et al., NeurIPS 2025. Item by item checks outperform holistic quality scores.

### Models as design critics

- [UICrit: Enhancing Automated Design Evaluation with a UI Critique Dataset](https://arxiv.org/abs/2407.08850), Duan et al., UIST 2024. Designer critiques cluster into layout, contrast, button usability, learnability and readability; zero-shot model critiques were mostly invalid.
- [UIClip: A Data-driven Model for Assessing User Interface Design](https://arxiv.org/abs/2404.12500), Wu et al., UIST 2024. Contrast, repetition, alignment and proximity define measurable failures; general vision models were near chance on design quality.
- [ArtifactsBench: Bridging the Visual-Interactive Gap in LLM Code Generation Evaluation](https://arxiv.org/abs/2507.04952), Zhang et al., 2025. Several screenshots across interaction states plus a per-task checklist matched human rankings closely.
- [WebDevJudge: Evaluating (M)LLMs as Critiques for Web Development Quality](https://arxiv.org/abs/2510.18560), Li et al., 2025. Pairwise comparison beats absolute scoring, and binary rubrics beat rating scales.
- [MLLM as a UI Judge](https://arxiv.org/abs/2510.08783), Luera et al., 2025. Models separate clearly different designs but not close ones.
- [Generating Automatic Feedback on UI Mockups with Large Language Models](https://arxiv.org/abs/2403.13139), Duan et al., CHI 2024. Good at misalignment, spacing and contrast; accuracy dropped on later rounds.
- [Can GPT-4o Evaluate Usability Like Human Experts?](https://arxiv.org/abs/2506.16345), Guerino et al., INTERACT 2025. Model heuristic reviews miss most interaction-level usability issues.
- [Can Vision Language Models Assess Graphic Design Aesthetics?](https://arxiv.org/abs/2603.01083), An et al., ICLR 2026. A clear vocabulary for layout, type, color and graphics, and weak localization of issues.
- [LLM Evaluators Recognize and Favor Their Own Generations](https://arxiv.org/abs/2404.13076), Panickssery et al., NeurIPS 2024. Judge with a different model than the one that generated the design.

### Writing rules that models follow

- [How Many Instructions Can LLMs Follow at Once?](https://arxiv.org/abs/2507.11538), Jaroslawicz et al., 2025. Adherence decays as instructions grow, failures are silent omissions, and earlier instructions win.
- [When Instructions Multiply: Measuring LLM Capabilities of Multiple Instructions Following](https://arxiv.org/abs/2509.21051), Harada et al., EMNLP 2025. The chance of satisfying every rule falls roughly multiplicatively with the number of rules.
- [When Thinking Fails: The Pitfalls of Reasoning for Instruction-Following in LLMs](https://arxiv.org/abs/2505.11423), Li et al., NeurIPS 2025. Reasoning can crowd out simple constraints and add unrequested content.
- [Suppressing Pink Elephants with Direct Principle Feedback](https://arxiv.org/abs/2402.07896), Castricato et al., 2024. Naming what to avoid keeps it present; pairing it with what to do instead works better.
- [Negation: A Pink Elephant in the Large Language Models' Room?](https://arxiv.org/abs/2503.22395), Vrabcova et al., 2025. Short, explicit prohibitions survive better than negations buried in long sentences.
- [LLMs Learn Better In-Context from Rules than from Examples](https://arxiv.org/abs/2609.03213), Fu et al., 2026. Rules transfer more reliably than examples.
- [Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172), Liu et al., TACL 2024. Information at the start and end of the context is used best.

### Guidelines and practitioner writing

- [Improving frontend design through Skills](https://claude.com/blog/improving-frontend-design-through-skills), Anthropic. Distributional convergence and why generic frontends happen.
- [Designing delightful frontends with GPT-5.4](https://developers.openai.com/blog/designing-delightful-frontends-with-gpt-5-4), OpenAI. Design systems up front, visual references and verification in a browser.
- [Design slop](https://www.adriankrebs.ch/blog/design-slop/), Adrian Krebs. Automated detection of common AI design patterns across 1,590 launched sites.
- [Web Interface Guidelines](https://interfaces.rauno.me), Rauno Freiberg. Interaction, forms, focus and motion details that separate finished interfaces from drafts.
- [Laws of UX](https://lawsofux.com) and [Nielsen Norman Group](https://www.nngroup.com/articles/ten-usability-heuristics/). The behavioral principles models reason about least reliably.
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/), [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines) and [Material Design 3](https://m3.material.io). The measurable floor and platform conventions.
