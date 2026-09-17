# Evaluations

A Skill is not considered mature because its instructions are long. It is mature when its intended behavior is observable and testable.

## Evaluation Layers

1. Normal cases — common user requests.
2. Edge cases — ambiguous or incomplete inputs.
3. Failure cases — unsafe, incorrect, or misleading assumptions.
4. Regression cases — previously fixed behavior must remain correct.

Each evaluation should record:

- scenario
- input
- expected behavior
- unacceptable behavior
- notes / result

Evaluation will be added as each production Skill is introduced.