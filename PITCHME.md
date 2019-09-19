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

# Recommended talks

<small>
- [Ryan Dahl: Original Node.js presentation (2009)](https://www.youtube.com/watch?v=ztspvPYybIY)
- [History of Node.js by Ryan Dahl (2011)](https://www.youtube.com/watch?v=SAc0vQCC6UQ)
- [10 Things I Regret About Node.js by Ryan Dahl (2018)](https://www.youtube.com/watch?v=M3BM9TB-8yA)
- [Deno, A New Server-Side Runtime by Ryan Dahl (2018)](https://www.youtube.com/watch?v=FlTG0UXRAkE)
- [From Node.js to Deno - JS/TS runtime built with V8 and Rust by Rafał Pocztarski (2019)](https://www.youtube.com/watch?v=Aib1OZLy0_c&t=5s)

</small>

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
