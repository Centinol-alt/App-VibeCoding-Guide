# Prompt Library:

## Progress Implementation Verification:
- Sometimes after prompting Claude to implement a particular step or phase it does not fully implement it. I've had experiences where I ask Claude if the step/plan is fully implemented, using the first of the 2 prompt's below, and Claude replies with a break down of what has been implemented and more importantly - what has not been implemented (bastard).
```bash
Have all the steps in phase/step X been fully implemented
```
Or:
```bash
Has all of this been fully implemented:

*copy-paste the entire step/phase
```
Or:
```bash
based on what we've done in our entire chat, how much of phase X is completed?
```
- **Code Generation Template**:
     ```bash
     Generate a [Flutter widget/FastAPI endpoint] for [specific functionality].
     Requirements:
     - Must handle [specific use cases]
     - Should implement [specific design patterns]
     - Needs to integrate with [related components]
     - Follow these patterns from existing code: [examples]
     Error handling should include: [expected error scenarios]
     ```

- **Code Review Template**:
     ```bash
     Review this [component type] code:
     [paste code]
     
     Focus on:
     - Security vulnerabilities
     - Performance issues
     - Adherence to project patterns
     - Potential edge cases
     - Optimization opportunities
     Provide specific recommendations with code examples.
     ```

- **Optimization Template**:
     ```bash
     Optimize this [function/component] for [performance/memory usage/etc]:
     [paste code]
     
     Current issues:
     - [describe specific performance concerns]
     - [mention any constraints]
     
     Required functionality must be preserved:
     - [list key behaviors that cannot change]
     ```

- **Architecture Decision Template**:
     ```bash
     I need to implement [feature]. I'm considering these approaches:
     1. [Approach 1]
     2. [Approach 2]
     
     Key considerations:
     - [scalability needs]
     - [performance requirements]
     - [security concerns]
     - [offline capabilities]
     
     Related components: [list]
     ```
