# Chai: A Language for Agents and Trust

Welcome to **chai** — a declarative language brewed for developers and intelligent agents to work together with *trust, safety, and clarity*. Whether you're building agent pipelines, exploring alignment, or prototyping explainability constraints, chai provides a principled, elegant foundation.

## 🌟 What Makes Chai Unique

- 🔗 **Agent Chaining** with intuitive operators (`->`, `|`, `&`, `||`, `or`)
- 🔐 **Trust Enforcement** via `align.verify(...)` and `.ti`/`.ii` agent metadata
- 🧠 **Policies as Contracts**, not comments: composable, immutable, programmable
- 📦 **Rich Data Types** including `tensor`, `df`, `ndarray`, and `obj` blobs
- 🧪 **Alignment Research Hooks**: context isolation, verifier orchestration, explainability enforcement
- 🚫 **Opinionated Defaults** that prevent prompt injection, output leakage, and unsafe chaining
- 🔁 **Turing-Complete**, recursive, but built with safety-first constraints

Chai is not just a DSL. It's an **alignment platform** for composable, verifiable agent systems.

## ✨ Quick Example

```chai
def main():
  let prompt = "summarize the history of tea"
  let draft = openai(prompt)
  let verified = align.verify(draft)? using tea_safety
  return verified
````

## 🧭 Flow Operators

* `A -> B`: Pass `A.o` to `B.i` (payload only, by default)
* `A | B`: Sequential steps
* `A or B`: Failover chaining
* `A & B`: Required parallel (both must succeed)
* `A || B`: Competitive parallel (first successful wins)

## 🛡️ Safety & Verification

Chai enforces:

* Mandatory `align.verify(...)` for dynamic/unfrozen agents
* Explicit `.ii`, `.io` when full input/output is passed
* Context isolation for parallelism (`&`, `||`)
* Immutable policies within a `def`
* No accidental sharing of mutable state or secrets

Example:

```chai
let x = openai("summarize") -> summarizer
let y = align.verify(x, using=safe_summary)
```

## 🔧 Supported Agent Types

* OpenAI / LLM agents
* REST APIs (GET/POST agents)
* Python functions (pure or impure)
* Local DB, FS, networked I/O
* Verifiers, explainers, goal reasoners

## 🧱 Supported Data Types

* `int`, `long`, `dec`, `real`
* `string`, `map`, `set`, `tuple`, `list`
* `ndarray` (NumPy arrays)
* `df` (DataFrames)
* `tensor` (Torch-compatible)
* `datetime`, `timespan`
* `obj` (restricted binary blobs, max 10MB)

## 🔬 Alignment Research Use-Cases

* Schema-based agent verification
* Explainability scoring (`.ti`)
* Goal-reasoning primitives (future)
* Composable verifier chains
* Policy sandboxing / contamination detection
* Parallel trust evaluation pipelines

## 📚 Documentation

The full tour of chai (the language manual) is in [Tour of Chai →](./Tour%20Of%20Chai.md)

Includes:

* Language overview
* Execution semantics
* Agent interface model
* Policy system
* Built-in safety rules
* Appendices on alignment and obj-handling

## 🧪 Status

Chai is currently **in alpha**.

* Syntax is stable
* Core primitives implemented
* Kernel and runtime integration with Python/Jupyter is in progress
* CLI + runtime interpreter WIP

## 🧠 Why Chai?

Because trust shouldn't be an afterthought. Chai lets you compose intelligent systems **with alignment built-in**, not bolted on.

## 📜 License

MIT
