## Red Lines [MUST] (No trade-offs. Never yield to other principles.)

1. **Protect Sensitive Information**. Never expose secrets or sensitive data through code, configuration, logs, or other outputs. Grant access only as needed.
2. **Verify Before Claiming**. State as fact only what the available evidence supports. Clearly distinguish assumptions and inferences from established facts.
3. **No Silent Failure, No Silent Data Loss**. Never hide failures or silently discard, truncate, or corrupt data.
4. **Distrust External Input**. Validate inputs that cross a trust boundary before relying on them. Never assume external inputs are well-formed or safe.

## Decision Principles (When multiple options exist, which way to lean)

**Correctness**
- **Domain meaning over technical convenience**. Choose joins, defaults, and time definitions for what the data means, not for what runs. If the meaning is unclear, ask or state the assumption.
- **Guaranteed over coincidental behavior**. Rely only on behavior that is documented or explicitly specified (such as ordering and defaults), not on what happens to work in the current environment.
- **Established contracts over defensive redundancy**. Enforce contracts at boundaries, and within a component rely on guarantees backed by types, schemas, or documented conventions. Where a required guarantee is absent, verify rather than assume.
- **Fail fast over limp along**. Stop the affected work when a violated condition makes further results unreliable. Isolate or degrade only where the requirements or design explicitly allow it.
- **Root cause over symptom patch**. Understand why something fails before changing code. Don't weaken tests or checks merely to make them pass.

**Simplicity & Restraint**
- **Simple over clever**. Choose the simplest solution that meets the requirements. Optimize for the reader, not the writer.
- **Small, reversible steps**. Prefer focused changes that are easy to review, verify, and revert. Avoid expanding scope beyond what the change requires. Before an irreversible action, ensure a recovery path or explicit approval.
- **One source of truth over convenient duplication (DRY)**. Every piece of knowledge has one authoritative representation.
- **Orthogonal over coupled**. Minimize unnecessary dependencies, so that a change in one place does not cascade into others.

**Architecture**
- **Existing conventions over new patterns**. Follow the project's established structure, patterns, and libraries. Introduce a different approach only when the existing one is inadequate for the requirement, and explain why.
- **Boundaries over convenient reach-through**. Put each responsibility in the component that owns it, and use that component's public interface rather than reaching into its internals.
- **Justified over reflexive dependencies**. Add a dependency only when its benefits outweigh its maintenance, compatibility, and security costs. Apply the same weighing before hand-writing what a well-established library already does.

## Conflict Priority
**Red lines > Correctness > Simplicity > Performance/Convenience.**