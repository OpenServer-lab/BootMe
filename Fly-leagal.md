# Fly Legal

## The boring-but-important page

So, you found Fly.

You read the source code.

You downloaded it.

You built it.

You made something with it.

Cool.

Before you accidentally start a company around it, read this page.

**Fly is free to use for noncommercial purposes.**

That is intentional.

Fly is **not** being presented as an OSI open-source licensed compiler. Fly uses a **dual-license model** consisting of:

1. **PolyForm Noncommercial License 1.0.0**
2. **Fly Commercial License**

The actual license texts in this repository are the legal terms that matter. This file exists to explain the model in normal human language.

> **This document is an explanation, not a replacement for the actual licenses.**
>
> When there is a conflict between this document and the actual license text, the actual license text wins.

---

# So... Can I Use Fly?

## Yes.

For normal noncommercial use, the answer is **yes**.

You can learn Fly.

You can experiment with Fly.

You can write programs in Fly.

You can make personal projects.

You can make school projects.

You can make hobby projects.

You can study the compiler.

You can modify your local copy.

You can build weird things with it.

You can make software because you think it would be funny.

That is what the noncommercial license is there for.

---

# "But Is Fly Open Source?"

Not in the strict licensing sense.

Fly is **free for noncommercial use**.

That distinction is deliberate.

The word "open source" has a specific meaning in software licensing, and the Fly licensing model does not use an OSI-approved open-source license for the compiler.

So the simple description is:

> **Fly is free for noncommercial use.**

Not:

> "Fly is open source."

That distinction matters when you are deciding whether a commercial product can use, redistribute, or modify Fly.

---

# The Two Licenses

Fly has two licensing paths.

## 1. PolyForm Noncommercial License 1.0.0

This is the normal path for **noncommercial use**.

It is the license intended for people who want to use Fly without using it as part of a commercial business activity covered by the license restrictions.

The PolyForm license text in the repository contains the actual permissions and restrictions.

Read that license when you need the exact legal definition of:

* commercial activity
* noncommercial activity
* redistribution
* modification
* permitted use
* restricted use

Do not rely on a one-line summary when the exact legal meaning matters.

## 2. Fly Commercial License

The second path is for **commercial use**.

This is the license to look at when you are making money from software, products, services, or other commercial activity involving Fly and your use does not fit within the noncommercial license.

The commercial license contains the actual commercial terms.

So:

> **Noncommercial? Use the PolyForm Noncommercial license where permitted.**

> **Commercial? Use the Fly Commercial License.**

That is the whole idea behind the dual-license setup.

---

# Why Does Fly Do This?

Because Fly is a project being developed by an actual human being, not a magic cloud that generates compiler engineers.

Making a compiler and its ecosystem takes work.

The goal is to keep Fly accessible to people who want to learn it, experiment with it, build hobby software, and help the ecosystem grow — while still having a licensing path for organizations that want to use Fly commercially.

In other words:

> **Use Fly. Learn Fly. Build with Fly.**
>
> **And when you turn Fly into part of a commercial business, use the commercial license.**

Yes, that is the joke.

**Laughs in dual license.**

---

# Examples

These examples are simplified explanations. The actual license text is controlling.

## Personal Project

You are learning Fly and build:

```text
my-cool-project/
├── main.fly
└── README.md
```

You are not using it as a commercial business.

That is the kind of use the noncommercial license is intended to cover.

---

## School Project

You write a Fly program for school.

You are learning.

You are experimenting.

You are turning in a project.

Again, this is the sort of noncommercial use Fly is intended to allow.

---

## Hobby Game

You write a game in Fly because you want to.

You test it with friends.

You put the source on your personal GitHub.

You keep working on it for fun.

That's exactly the sort of ecosystem Fly is meant to encourage.

---

## Open-Source Showcase Project

A project can be open source while being written in Fly.

For example, a tool can use an open-source license of its own while being implemented in Fly.

**That project's license does not automatically change Fly's license.**

This is an important distinction.

For example:

```text
Duster
├── open-source project
└── written in Fly

Fly compiler
└── PolyForm Noncommercial + Fly Commercial License
```

Duster being open source does not make Fly open source.

A program being open source does not automatically give you an open-source license to the compiler used to build it.

---

# "Can I Read the Fly Source?"

Yes, subject to the license terms.

Reading source code and having permission to use, modify, redistribute, or commercially exploit software are different questions.

Do not assume:

> "I can see the source, therefore I can do anything I want with it."

Read the license.

---

# "Can I Modify Fly?"

The noncommercial license provides permissions subject to its terms.

That means you can experiment with the compiler within the permissions granted by the license.

However, modifying Fly does not magically remove the license.

A modified Fly compiler is still subject to the applicable license terms.

You cannot take a licensed project, change some code, and declare:

> "Mine now."

That's not how software licenses work.

---

# "Can I Make Money With a Fly Program?"

This is where you need to stop and read the license that applies to your use.

The fact that **your program** is yours does not automatically mean that **your commercial use of Fly** is unrestricted.

Fly deliberately has a commercial licensing path.

So if your project becomes a business, product, paid service, or other commercial activity involving Fly, check the **Fly Commercial License**.

Do not guess.

Do not rely on:

* a random Reddit comment
* an AI answer
* a forum post from 2017
* "my friend said it's MIT"
* "it's on GitHub so it's open source"
* or anything else that isn't the actual license

Read the actual license.

---

# "Can I Sell My Fly Program?"

Your program and the Fly toolchain are separate pieces of software.

The fact that you wrote a program in Fly does not automatically make your program Fly.

Your program has its own licensing situation.

However, your **use of Fly itself** still needs to comply with the Fly license that applies to you.

So there are two separate questions:

### What license does my program have?

You decide that for your project, subject to any third-party components and their licenses.

### Am I allowed to use Fly in that way?

That is determined by the Fly license.

Do not mix those two questions together.

---

# "I Made an Open-Source Project in Fly"

That's fine.

A project written in Fly can have its own license.

For example, a project could choose MIT, GPL, Apache-2.0, or another license that is appropriate for that project.

But the project's license is **not the Fly compiler's license**.

Think of it this way:

```text
Your project license
        +
Fly license
        +
Other dependency licenses
        =
The complete licensing situation
```

Every layer has its own rules.

---

# "Can I Redistribute Fly?"

Read the applicable license.

The important thing is that redistribution permissions come from the actual license, not from the fact that somebody uploaded a binary to GitHub.

If you redistribute Fly or a modified version of Fly, make sure you comply with the license's requirements.

Again:

> **The license text is the source of truth.**

---

# "Can I Fork the Fly Repository?"

A GitHub fork is not the same thing as receiving unlimited copyright permissions.

You may use GitHub's fork functionality according to GitHub's rules and the repository's license, but what you may actually do with the source code is determined by the applicable Fly license.

A fork does not magically convert Fly into MIT.

---

# "Can I Make a Commercial Fork of Fly?"

This is exactly the sort of question the **Fly Commercial License** exists for.

Do not assume that modifying the source code changes the licensing requirement.

If you want to build a commercial product around a fork or modified version of Fly, review the commercial license and follow its terms.

---

# Why Not Just MIT?

Because Fly is not being licensed as a completely unrestricted MIT project.

That is intentional.

MIT is an excellent license for many projects, but it is not the licensing model chosen for Fly.

Fly is intended to be:

* accessible for noncommercial users
* usable for learning and experimentation
* available for ecosystem development
* while providing a commercial licensing path

That is why Fly has a dual-license model instead of a single permissive open-source license.

---

# What About Projects Written in Fly?

This deserves its own section because it is easy to get confused.

A project written in Fly does **not** automatically inherit Fly's license.

For example:

```text
Duster
License: MIT
Implementation language: Fly
```

That does not mean:

```text
Fly compiler
License: MIT
```

It means:

```text
Duster -> MIT
Fly    -> PolyForm Noncommercial + Fly Commercial
```

The same applies to other programs written in Fly.

The language used to write software and the license of the toolchain used to build it are not the same thing.

---

# Commercial Use: The Simple Rule

Here is the deliberately oversimplified version:

```text
Not commercial?
    |
    v
Use Fly under the noncommercial license,
subject to its actual terms.

Commercial?
    |
    v
Read and use the Fly Commercial License.
```

When in doubt, read the actual license.

When **really** in doubt, ask a lawyer.

Yes, I know.

Terrifying.

---

# Things This File Does NOT Do

This file does not:

* replace the actual licenses
* redefine legal terms
* grant additional rights
* remove restrictions from the licenses
* define the commercial pricing or commercial terms
* override the license files
* turn Fly into an OSI open-source project
* give legal advice

The purpose of this file is simply to stop people from having to decode a wall of legal text just to understand the basic idea.

---

# The Actual License Wins

This is worth repeating.

If this file says something that appears to conflict with the actual license:

**the actual license wins.**

Always.

This page is documentation.

The license is the legal agreement.

---

# A Very Short Version

Because apparently some people will skip directly here:

> **Fly is free for noncommercial use under the PolyForm Noncommercial License 1.0.0, subject to its terms.**
>
> **Commercial use is handled through the Fly Commercial License.**
>
> **Fly is not being described as OSI open-source software.**
>
> **Projects written in Fly can have their own licenses.**
>
> **Duster and other open-source Fly projects do not change Fly's own license.**
>
> **When the exact legal answer matters, read the actual license files.**

---

# Why The Dual License Exists

Fly is being developed as a real programming language and toolchain.

The goal is to make it easy for people to:

* learn Fly
* experiment with Fly
* build hobby projects
* build educational projects
* create open-source ecosystem software
* contribute improvements
* demonstrate what the language can do

At the same time, there needs to be a clear path for commercial users.

That's what the dual-license model provides.

So yes:

> **You can use Fly for free for noncommercial purposes.**

And yes:

> **There is a commercial license when you're doing commercial things.**

That's not hidden.

That's the entire point of this file existing.

---

# Final Note

Please do not treat this document as a substitute for reading the actual license.

Software licensing can become complicated very quickly once money, distribution, incorporation, hosting, bundled software, trademarks, patents, or modified toolchains enter the picture.

For ordinary use, the important distinction is simple:

```text
Fly
├── Noncommercial use
│   └── PolyForm Noncommercial License 1.0.0
│
└── Commercial use
    └── Fly Commercial License
```

Use the license that applies to what you are doing.

Build cool stuff.

And please do not make the compiler into a billion-dollar corporation before checking the commercial license.

Seriously.
