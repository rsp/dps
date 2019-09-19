# Rafał Pocztarski

You may know me from Stack Overflow

[<img alt="rsp on Stack Overflow" src="https://stackexchange.com/users/flair/303952.png" height="116">](https://stackoverflow.com/users/613198/rsp)

# pocztarski.com

<small>(and also from Medium, Quora, etc.)</small>

---

# <small>Deno privileges<br>and sandboxing</small>

rethinking the security model in a new secure JavaScript/TypeScript runtime

---

# Timeline

2009 Node.js

2012 TypeScript

2018 Deno

---

# Architecture

Node = Server-side JS with V8 + libuv in C++

Deno = Server-side TS with V8 + Tokio in Rust

---

# Deno

deno is a standalone executable<br>
it doesn't use Node.js<br>
it is distributed as a single binary<br>
it contains the TypeScript compiler as a V8 snapshot<br>
it has no dependencies<br>
it is a runtime written in Rust using Tokio

---

# Installation

get a single binary (not even a tarball)

https://deno.land/

---

For the brave:

`curl -fsSL https://deno.land/x/install/install.sh | sh`

or just get a single file from:

https://github.com/denoland/deno/releases

---

# Dependencies

import URLs directly

`import { hello } from 'https://pocztarski.com/hello.ts';`

---

# Running

work on TS files, run TS files with deno

`deno run script.ts`

`deno run https://pocztarski.com/hi.ts`

---

# Security

No network and filesystem access by default

`deno run --allow-write script.ts`

`deno run --allow-net script.ts`

---

# Example

```
$ cat hi.ts 

import { hello } from 'https://pocztarski.com/hello.ts';

hello('Warsaw TypeScript');
```

---

# Running

```
$ deno run hi.ts 
Compile file:///Users/rsp/talks/ts-runtimes/hi.ts
Download https://pocztarski.com/hello.ts
Hello, Warsaw TypeScript!

$ deno run hi.ts 
Hello, Warsaw TypeScript!
```

---

# Libraries

https://deno.land/x/

---

# Caching

Deno downloads and caches all the files globally by default

Cleaning the cache (on Mac)<br>
`rm -rvf ~/Library/Caches/deno`

Using local caches<br>
`DENO_DIR=$(pwd)/.deno deno run hi.ts`

---

# GitHub Issues

<small>
- Capability-based security model [#378](https://github.com/denoland/deno/issues/378)
- More granular privilege separation [#515](https://github.com/denoland/deno/issues/515)
- Security concern [#720](https://github.com/denoland/deno/issues/720)
- Sandbox mode for external scripts [#1639](https://github.com/denoland/deno/issues/1639)
- Potential security issues with shebang script with flags [#1704](https://github.com/denoland/deno/issues/1704)
- Per-import permissions? [#1860](https://github.com/denoland/deno/issues/1860)
- deno eval [#2081](https://github.com/denoland/deno/issues/2081)
- New permission to run Deno programs to avoid `--allow-run` privilege escalation [#2128](https://github.com/denoland/deno/issues/2128)

</small>

---

# Examples

<small>
`$ deno --allow-net=localhost --no-prompt run script.ts`

</small>

---

Related info

https://man.openbsd.org/pledge.2

http://www.cap-lore.com/

- [MicroEssays on Capability Theory](http://www.cap-lore.com/CapTheory)
- [Computer Security, the Very Idea](http://www.cap-lore.com/Dual.html)

---

Interesting Systems

- [OpenBSD](https://www.openbsd.org/)
- [KeyKOS](http://cap-lore.com/CapTheory/upenn/)
- [EROS](https://en.wikipedia.org/wiki/EROS_(microkernel))
- [CapROS](https://en.wikipedia.org/wiki/CapROS)
- [Coyotos](https://archiveos.org/coyotos/)

---

Papers

- [GNOSIS - A Prototype Operating System for the 1990's](http://cap-lore.com/CapTheory/upenn/Gnosis/Gnosis.html) (1979)
- [KeyKOS - A Secure, High-Performance Environment for S/370](http://cap-lore.com/CapTheory/upenn/Key370/Key370.html) (1988) 
- [The KeyKOS Architecture](http://cap-lore.com/CapTheory/upenn/OSRpaper.html) (1985) 
- [The Checkpoint Mechanism in KeyKOS](http://cap-lore.com/CapTheory/upenn/Checkpoint.html) (1992)
- [The KeyKOS NanoKernel Architecture](http://cap-lore.com/CapTheory/upenn/NanoKernel/NanoKernel.html) (1992)
- [BitC: A Modern Language for Systems Programming](http://www.cis.upenn.edu/~plclub/schedule/2009_spring_shap.pdf) (1999)

---

Recommended talks

- [Ryan Dahl: Original Node.js presentation (2009)](https://www.youtube.com/watch?v=ztspvPYybIY)
- [History of Node.js by Ryan Dahl (2011)](https://www.youtube.com/watch?v=SAc0vQCC6UQ)
- [10 Things I Regret About Node.js by Ryan Dahl (2018)](https://www.youtube.com/watch?v=M3BM9TB-8yA)
- [Deno, A New Server-Side Runtime by Ryan Dahl (2018)](https://www.youtube.com/watch?v=FlTG0UXRAkE)
- [From Node.js to Deno - JS/TS runtime built with V8 and Rust by Rafał Pocztarski (2019)](https://www.youtube.com/watch?v=Aib1OZLy0_c&t=5s)

---

# Resources

<small>
- https://deno.land/
- https://denoland.org/
- https://deno.land/manual.html
- https://deno.land/typedoc/
- https://deno.land/x/
- https://www.typescriptlang.org/
- https://github.com/TypeStrong/ts-node
- https://nodejs.org/en/

</small>

---

# Deno in Poland

[Bartek Iwańczuk](https://github.com/bartlomieju)<br>
[Michał Sabiniarz](https://github.com/mhvsa)<br>
[Rafał Pocztarski](https://github.com/rsp)

<small>
[DenoWarsaw.com](https://DenoWarsaw.com/)<br>
[meetup.com/DenoWarsaw](https://meetup.com/DenoWarsaw)<br>
[twitter.com/DenoWarsaw](https://twitter.com/DenoWarsaw)

[DenoPoland.com](https://DenoPoland.com/)<br>
[meetup.com/DenoPoland](https://meetup.com/DenoPoland)<br>
[tweeter.com/DenoPoland](https://tweeter.com/DenoPoland)

</small>

---

# Questions?

Slides: https://pocztarski.com/dps

## Rafał Pocztarski

## [pocztarski.com](https://pocztarski.com)

“The only thing that matters in software is the experience of the user.” - Ryan Dahl
