# Anything

A revolutionary programming language that speaks every language

## Overview
**Anything** is a next-generation programming language that compiles to C++. It breaks down language barriers by allowing you to write code using syntax from virtually any programming language, seamlessly mixing them together, or even creating your own custom syntax.

## The Origin Story
Anything started as a personal learning project to deeply understand compilers, parsers, virtual machines, and language design. What began as an educational journey evolved into an ambitious experiment: What if a language could adapt to you instead of forcing you to adapt to it?

> [!IMPORTANT]
> **Current Status**: This project is actively in development as I work through learning phases of compiler construction, parsing theory, and language implementation. While the vision is comprehensive, many features are being built iteratively as part of the learning process.

## Why Anything?

- **Polyglot by Design**: Write Python-style loops, JavaScript arrow functions, Ruby blocks, or Go channels - all in the same file
- **Universal Code Sharing**: Write in your syntax, let others read it in theirs - same logic, different representation
- **Zero Context Switching**: Use the syntax you're most comfortable with for each task
- **Your Syntax, Your Rules**: Create entirely custom syntax patterns that match your mental model
- **Educational Foundation**: Built from the ground up as a learning project in compiler design, parsing theory, and VM architecture
- **C++ Performance**: Compiles directly to optimized C++ code
- **Interoperability**: Mix and match syntax styles without friction

_Note: Many features are in active development. This README describes both current capabilities and aspirational goals._

## **Syntax Transpilation (One possible approach)**
```bash
Your Custom Syntax → AST → Target Syntax Renderer → Syntax Preferred by Another Developer
```

The AST serves as a universal intermediate representation, allowing code written in one syntax to be viewed and edited in any other supported syntax. This means:

- Teams can collaborate without agreeing on syntax style
- Legacy code can be "translated" for better understanding
- Learning becomes easier - see the same algorithm in multiple notations
- Code reviews focus on logic, not formatting preferences


## Philosophy
**Anything** is built on three core principles:

1. **Learn by Building**: This project exists to explore compiler theory, parser design, and language implementation in depth
2. **Syntax Freedom**: You can write code in the syntax of popular languages (Python, JavaScript, Rust, etc.), mix multiple syntaxes together, or invent your own syntax rules entirely
3. **Zero Compromises**: Regardless of syntax style, compile to efficient C++ code

## The Translation Vision
> [!WARNING]
> This code is a simplified conceptual illustration, not an exact or fully correct implementation.
##
Imagine this scenario:

**Alice** writes a sorting algorithm in her custom mathematical notation:

```anything
∀ array A, sort(A) := 
    ∑(i=0 to |A|-1) min(A[i:])
```

**Bob** doesn't understand mathematical notation, so he transpiles Alice's code to Python:

```python
def sort(array):
    result = []
    for i in range(len(array)):
        result.append(min(array[i:]))
    return result
```

**Carol** prefers natural language, so she converts the same code:

```anything
define function sort with parameter array:
    for each position from start to end of array:
        find the smallest value in remaining elements
        add it to the result
    return the result
```

**David** is reviewing a complex 200-line function and getting lost in the details. He converts it to a visual block diagram to see the structure at a glance:

```anything
// Original complex function (abbreviated)
function processUserData(user, settings, cache) {
    let validated = validateUser(user)
    if (!validated) throw new Error("Invalid")
    let profile = cache.get(user.id) || fetchProfile(user.id)
    let permissions = calculatePermissions(user.role, settings)
    let data = mergeData(profile, permissions, settings.defaults)
    if (settings.encrypt) data = encrypt(data, settings.key)
    cache.set(user.id, data, settings.ttl)
    return data
}

// David's visual block view - same logic, clearer structure
┌─────── function processUserData ───────┐
│ INPUT: user, settings, cache           │
│ OUTPUT: processed data                 │
│ ─────────────────────────────────────  │
│                                        │
│  ┌─ validate user ─┐                   │
│  │ if invalid: throw error             │
│  └────────────────┘                    │
│           ↓                            │
│  ┌─ get profile ───┐                   │
│  │ from cache OR fetch from DB         │
│  └────────────────┘                    │
│           ↓                            │
│  ┌─ calculate permissions ─┐           │
│  │ based on role + settings            │
│  └────────────────────────┘            │
│           ↓                            │
│  ┌─ merge all data ─┐                  │
│  │ profile + permissions + defaults    │
│  └──────────────────┘                  │
│           ↓                            │
│  ┌─ conditional encryption ─┐          │
│  │ if enabled: encrypt with key        │
│  └──────────────────────────┘          │
│           ↓                            │
│  ┌─ cache result ─┐                    │
│  │ save with TTL                       │
│  └────────────────┘                    │
│           ↓                            │
│      return data                       │
└────────────────────────────────────────┘
```

## 
Write Anything. Compile Anywhere. Run Everywhere.
