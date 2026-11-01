---
description: Rules for writing code and types.
---

## Write code

- Write declarative code that reads as a statement of what it does. Build behavior from small, focused pieces, such as pipes, layers, schemas, and plain functions, that each read well alone and combine cleanly.
- Prefer explicit code over generators and factories. Inline a helper that has one caller. Add an abstraction only when it makes the code clearer, not only shorter.
- Keep configuration explicit. Derive duplicate values and types from their authoritative definition. Infer types from the value, registry, or return type that defines them, and annotate only what inference cannot reach.
- Use the strictest type settings. Narrow types instead of asserting them.
- Use the primitives of the libraries and platform the code already uses, such as Effect, Hono, or Expo, before you write your own.
- Represent errors as tagged errors, not as sentinel flags or boolean fields.
- Encode the domain in a data structure instead of scattered conditionals. Use a state machine instead of booleans that must stay in sync, and a discriminated union or lookup table instead of an if/else chain that grows by one branch per feature.
- Parse external input, such as requests, config, environment variables, database rows, and CLI arguments, into domain types at the boundary. Trust those types inside the system, and do not validate them again deeper in the call chain.
- Brand primitives that mean different things, such as `UserId` and `OrderId`, so that the type checker rejects mixing them.
- Make state-changing commands and lifecycle steps idempotent. Read the current state, compare it to the goal, and apply only the difference, so that a second run or a run after a crash ends in the same state.
