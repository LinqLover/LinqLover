---
title: "How to Perform a Brain Surgery on Yourself: Safe Bootstrapping for Self-Supporting Systems"
description: Talk at HPI Research School on Systems Design Meeting 2024-06-03 - Abstract
---

Self-supporting systems promise a powerful form of live programming: the foundations of the system—such as compilers, editors, debuggers, and even garbage collectors—can themselves be inspected and changed from within the running environment. But this power comes with a bootstrapping hazard. When the system depends on the component being changed, even a short-lived mistake can break the environment needed to recover from it.

In this talk, I will briefly compare several designs of self-supporting systems and virtual machines and discuss how they affect live programming. I will review a few existing strategies to perform “brain surgeries” on self-supporting systems and then present our own approach for bootstrapping userland components via out-of-place execution. Through a case study on Sista/Scorch, an adaptive optimizer for the OpenSmalltalk VM, I will show how our approach lets us evolve userland and VM components together at runtime while preserving a live, uninterrupted programming flow.

---

Slides: [PDF (with embedded screencasts)](https://linqlover.github.io/assets/slides/SDRSM_Bootstrapping.pdf)
