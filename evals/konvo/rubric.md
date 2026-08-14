# KONVO Rubric

Score each dimension from `0` to `2`.

- `0`: poor or absent
- `1`: partially present or inconsistent
- `2`: clearly present and effective

Maximum score: `16`

## Dimensions

### 1. Trigger Fit

- `0`: the skill style clearly should not have been used
- `1`: partly suitable, but over-applied or under-applied
- `2`: clearly the right style for the prompt

### 2. Intuition First

- `0`: opens with definitions or jargon and stays abstract
- `1`: some intuition work, but too late or too thin
- `2`: builds understanding in plain language before getting formal

### 3. Teaching Anchor

- `0`: no stable example, analogy, toy model, or transformation pattern
- `1`: anchor exists but is weak, inconsistent, or abandoned
- `2`: strong anchor carries the explanation cleanly

### 4. Structure and Flow

- `0`: rambling, flat, or poorly staged
- `1`: some structure, but conceptual jumps are too large
- `2`: clean progression with well-scoped sections and strong momentum

### 5. Visual Thinking

- `0`: no visual support where it would obviously help
- `1`: some visual support, but not well integrated
- `2`: diagrams, image directions, or state framing noticeably improve comprehension

### 5b. Visual Planning

Scored only when the piece calls for images at all. A code-carried article that
correctly runs light on visuals should not be penalized here.

- `0`: images are gestured at in prose, mistyped, or dumped at the end
- `1`: markers are present and roughly in the right places, but vague, uncaptioned by any setup sentence, or over-budget on levity
- `2`: each marker is placed inline, introduced by the sentence before it, specific enough to build, correctly typed as teaching or levity, and carries alt text

### 6. Tone and Readability

- `0`: stiff, generic, hypey, or obviously AI-sounding
- `1`: readable, but uneven or too neutral
- `2`: warm, human, precise, and easy to follow

### 7. Technical Precision

- `0`: misleading or inaccurate
- `1`: mostly correct but hand-wavy in key places
- `2`: technically reliable while still accessible

### 8. Rule Compliance

- `0`: breaks one or more hard constraints such as double dashes
- `1`: mostly compliant with small issues
- `2`: fully compliant with the important skill rules

## Pass Guidance

Dimension 5b only applies when the piece calls for images, so the maximum is 18
when it is scored and 16 when it is not. Judge against the share of the
available total rather than a fixed number:

- `80%+` (`15/18` or `13/16`): strong value add
- `60-79%` (`11/18` or `10/16`): useful, but should be refined
- `40-59%` (`8/18` or `7/16`): weak value
- below `40%`: likely not helping

## A/B Comparison Rule

When comparing baseline vs. skill-assisted output, mark the skill as a success only if:

- the skill-assisted version scores higher overall, and
- it does not score lower on technical precision, and
- it does not fail the hard regression checks
