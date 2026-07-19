---
name: amazzzing-prompts
description: Use when a user wants to create, draft, improve, rewrite, or optimize a prompt for a general-purpose AI, especially when the request is vague, incomplete, or needs multi-turn clarification.
---

# Amazzzing-prompts

## Objective

Turn an initial idea or an existing Prompt into one complete, directly usable Prompt through adaptive clarification. Stay independent of specific AI products and task categories.

## Manage the dialogue

1. Count every assistant response after this skill activates as one round. Rounds 1 through 6 may clarify. Round 7 must deliver the final Prompt.
2. Determine whether the user is creating a new Prompt, optimizing an existing one, or has already supplied enough information for immediate generation.
3. Maintain an internal task brief. Consider the desired result, scenario, necessary inputs, audience, output form, constraints, quality criteria, and handling of uncertainty. Ignore dimensions irrelevant to the task. Do not expose this brief as a questionnaire.
4. Before asking, identify the single unanswered point most likely to change the task path, constraints, or output. Ask it only when its value justifies using another round.
5. Infer low-risk details from context. Never repeat answered questions or ask questions merely to prolong the dialogue.

Ask exactly one concise question per clarification response and request exactly one answerable decision or information field. Do not append requests for identifiers, sources, examples, supporting material, or related details, even as optional or conditional additions. Options must be alternative answers to that same field. If the answer later needs disambiguation, use another round. Place the recommended option first when offering options, and allow a free-form answer.

If the user supplies multiple goals, combine them only when they share one workflow and deliverable. Otherwise ask which goal to prioritize.

## Stop clarifying

Generate the final Prompt immediately when any condition applies:

- The information is sufficient for a high-quality, executable Prompt.
- Another answer would not materially improve the result.
- The user asks to generate now or delegates the remaining choices.
- The current response is round 7.

When the user is unsure, says “you decide,” or repeatedly gives vague answers, choose reasonable defaults from the context. At the round limit, resolve remaining ambiguity in favor of the main goal and produce internally consistent instructions.

## Build the Prompt

Use only components that improve the task: objective, relevant role or perspective, context, inputs and boundaries, execution requirements, constraints, output structure, quality criteria, and uncertainty handling. Omit ceremonial role assignments and generic filler.

For an existing Prompt, preserve valid intent and information while fixing ambiguity, omissions, conflicts, redundancy, and non-executable requirements. Ask only about gaps that materially affect the result.

Before delivery, check that the Prompt:

- Has one clear objective and no conflicting instructions.
- Distinguishes source material, user input, and execution instructions.
- Specifies the output form and observable completion criteria.
- Handles missing or uncertain information without unsupported invention.
- Uses the user's language unless the task requires another language.
- Works with a general-purpose AI and avoids product-specific features.
- Contains only information useful to completing the task.

## Deliver

Return exactly one complete Prompt inside one Markdown code block. Put no title, explanation, score, summary, alternative version, or follow-up question outside the code block. Choose a fence length that safely contains any code fences required inside the Prompt.
