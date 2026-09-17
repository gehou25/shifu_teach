[archive-contract.md](https://github.com/user-attachments/files/32323520/archive-contract.md)
# Archive contract

Use this contract only after the episode has produced reusable learning evidence and a writable archive target is authorized.

## Reuse before creating

Inspect the target's existing structure. Map equivalent fields into its schema and preserve its formatting. Add missing fields only when compatible. Do not create a second archive, duplicate the conversation, or rewrite unrelated entries.

## Canonical record

Use this domain-independent shape when no compatible schema exists:

```yaml
task: ""
domain: ""
topic: ""
source: []

user_goal: ""
user_original_approach: ""

student_state_before:
  known_knowledge: []
  missing_knowledge: []
  known_skills: []
  missing_skills: []
  current_bottleneck: ""
  misconceptions: []
  help_level: null

problem_decomposition: []
gap_model:
  knowledge: []
  skill: []
  insight: []

error_point: ""
root_cause: ""
error_type: ""

required_knowledge:
  prerequisite: []
  core: []
  direct_extension: []
correct_mental_model: ""
solution_or_reasoning: ""

consolidation:
  problem_specific_summary: ""
  transferable_strategy: ""
  why_it_works: ""
  transfer_value: ""
  personal_learning_point: ""
  student_generated: null

student_state_update:
  changed_items: []
  evidence: ""
  evidence_scope: "this episode"

user_takeaway: ""
teach_back: ""
remaining_uncertainty: ""
timestamp: ""

mastery_status: null
review_needed: null
last_verified: null
```

Leave unknown fields empty rather than inventing evidence. Use `High`, `Medium`, or `Low` for `transfer_value` only when the distinction is useful. Keep `mastery_status`, `review_needed`, and `last_verified` null unless an existing archive already defines durable semantics.

## Compression standard

- Preserve the learner's original approach in compact form.
- Record the first causal break rather than every downstream error.
- Distinguish Knowledge, Skill, and Insight gaps.
- Preserve the replacement mental model and reusable reasoning pattern.
- Record consolidation only when it occurred; distinguish independent from scaffolded reconstruction.
- Record any state change with its evidence and limit the claim to this episode.
- Separate source-derived claims from teaching supplements when relevant.
- Preserve uncertainty rather than claiming mastery.
- Do not copy the full transcript, hidden reasoning, or irrelevant personal data.

## Lifecycle

Use this order when each step is warranted:

`reported solved -> learner reconstruction -> guided refinement -> root-cause reflection -> state update -> archive`

For concept learning or other episodes without a solution route, the compact lifecycle remains `reported solved -> teach-back -> root-cause reflection -> archive`. For a trivial correction, stop after solving. When the learner's own explanation already supplies accurate consolidation evidence, reuse it rather than asking for another summary.
