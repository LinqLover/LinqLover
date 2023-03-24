---
title: Christoph Thiede
description: Software Engineering student with a strong interest in building programming tools
---

<a href="./assets/skills.svg"><img alt="Skills" src="./assets/skills.svg" align="right" height="200"></a>
Hi, I‘m Christoph! I am a **master student in Computer Science and Software Engineering** and am interested in building and researching **innovative programming tools.** I have developed a novel **back-in-time debugger** for Squeak/Smalltalk, a downstream dependency analysis tool for VS Code, and several other prototypes. As a core developer of the **interactive programming system Squeak,** I explore and contribute to several areas such as its **code browsing tools** and its **regular expression engine.** In my spare time, I also play squash, jazz piano, and am owned by four cats.

***Contact:** [Email](mailto:christoph.thiede@outlook.de) · [Twitter](https://twitter.com/LinqLover) · [LinkedIn](https://www.linkedin.com/in/christoph-thiede-20a0b8207/) · [GitHub](https://github.com/LinqLover)*

## Experiences

- ### Student Research Assistant

  Hasso Plattner Institute, Software Architecture Group  
  2019-08 – present
  
  As a student research assistant, I help maintain and extend [Squeak](#contributions-to-squeak), participate in [research projects](https://www.hpi.uni-potsdam.de/hirschfeld/) on programming and debugging tools, and have co-authored a [textbook](#publications) on Squeak.
  
  ***Skills:** Squeak/Smalltalk · OOP · Academic Writing*
  
- ### Student Teaching Assistant

  Hasso Plattner Institute, Software Architecture Group  
  2022-04 – 2022-08
  
  As a teaching assistant, I supervised a team of undergraduate students in a [software engineering project](https://hpi-de.translate.goog/studium/im-studium/lehrveranstaltungen/it-systems-engineering-ba/lehrveranstaltung/sose-22-3471-softwaretechnik-i.html?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=de&_x_tr_pto=wapp) and provided them guidance in mastering agile methods and technical issues.
  
  ***Skills:** Agile Methods · Teaching*
  
- ### Student Data Engineering Assistant
  
  Museums of the Hasso Plattner Foundation  
  2020-08 – present
  
  At the HPF, I am responsible for maintaining and extending [Barberini Analytics](https://github.com/Museum-Barberini/Barberini-Analytics), a data mining and analytics platform that provides management and PR teams with business insights from data sources such as social media, review platforms, and the internal customer system.
  
  ***Skills:** Python · PostgreSQL · Basic Linux Administration*

## Education

- ### *M.Sc. IT-Systems Engineering*

  Hasso Plattner Institute  
  2021-04 – 2024-09 (expected)  
  
  Highlighted courses: Programming Experience · Reverse Engineering · Advanced Programming Tools · Parallel Programming and Heterogeneous Computing · Neurodesign · Global Design Thinking Workshop
  
- ### B.Sc. IT-Systems Engineering

  Hasso Plattner Institute  
  2017-10 – 2021-03
  
  Highlighted courses: Project Management · Programming of User Interfaces · Agile Software Development in Large Teams

## Featured Projects

- ### [TraceDebugger](https://github.com/hpi-swa-lab/squeak-tracedebugger)

  2021-10 – present
  
  <a href="./assets/TraceDebugger.png"><img alt="TraceDebugger" src="./assets/TraceDebugger.png" height="200"></a>
  
  TraceDebugger is a **back-in-time debugger** for Squeak that aims to improve the navigation experience and immediacy during debugging. Among other things, I proposed a **novel state-centric perspective** and presented it in our [scientific paper](#publications) at the Programming Experience 2023 workshop.

- ### [Contributions to Squeak](https://squeak.org)

  2019-05 – present
  
  <a href="./assets/Squeak-inspectors.png"><img alt="New inspectors in Squeak" src="./assets/Squeak-inspectors.png" height="200"></a>
  
  [Squeak](http://squeak.org/) is an **interactive programming system** for Smalltalk that is completely implemented in itself and promotes values such as flexibility, liveness, and explorability. I am engaging in the design and implementation of several subsystems, including **tools for code browsing, debugging, and version control, the UI system, the exception handling system, and others.** Since 2021, I am also a member of the **core developers** team. Working on a system of this complexity also gives me many opportunities to learn about common trade-offs such as compatibility and modularity, quality and quantity, or products and people.

  Major accomplishments:

  - **Reworked the inspector tool family,** added watch expressions, and designed a new extension API.
  - Fixed several critical bugs in the **debugging infrastructure** and the exception handling system.
  - Supported the **Squeak 6.0 release,** in particular by authoring the [release notes](https://raw.githubusercontent.com/squeak-smalltalk/squeak-app/squeak-trunk/release-notes/6.0).

- ### [Contributions to VBRegex](https://source.squeak.org/trunk/Regex-Core-ct.78.diff)

  2020-03 – present
  
  <a href="./assets/Regex-Tools-backreference.png"><img alt="Visualization of a matcher with a backreference" src="./assets/Regex-Tools-backreference.png"></a>
  
  VBRegex is a **regular expression engine** for Squeak/Smalltalk that emphasizes an explorable implementation and a clean object-oriented design. I co-maintain the project and have contributed **several bug fixes** and new features such as **named capture groups (`(?<name>)`, lookarounds (`(?<=)` etc.), match resets (`\K`), and others.** I also built a [visualization tool](https://github.com/LinqLover/Regex-Tools) to explore the matcher‘s behavior.

- ### [SimulationStudio](https://github.com/LinqLover/SimulationStudio)

  2021-05 – present
  
  <a href="./assets/SimulationMethodFinder.png"><img alt="Simulation Method Finder" src="./assets/SimulationMethodFinder.png" height="150"></a><a href="./assets/SimulationProtocolExplorer.png"><img alt="Simulation Protocol Explorer" src="./assets/SimulationProtocolExplorer.png" height="150"></a>
  
  SimulationStudio exploits the flexible nature of Squeak‘s call stack model and provides a **framework for fine-grained control of the execution** through code simulation. Building on this, SimulationStudio offers a **sandbox for isolated execution** and multiple tools for the **behavior-centric exploration** of classes and objects.

- ### [Downstream Repository Mining](https://github.com/LinqLover/downstream-repository-mining)

  2021-04 – 2022-04
  
  <a href="./assets/dowdep-dependencies.png"><img alt="VS Code Extension: Downstream Dependencies" src="./assets/dowdep-dependencies.png" height="200"></a>
  
  I developed a **VS Code extension in TypeScript** that **collects downstream dependency projects** for npm packages from GitHub & Co. and allows package developers to **analyze usage samples** from their IDE. I presented the tool and the underlying approach in our [scientific paper](#publications) at the ENASE/2022 conference.

- ### [**Sonyx**](https://hpi.de/neurodesign/projects/sonyx.html)

  2021-04 – 2022-05
  
  <!-- <video alt="Sonyx" src="https://user-images.githubusercontent.com/38782922/131224109-b474991a-5558-4a62-aff4-ed17e512e663.mp4" height="200"> -->
  <a href="https://youtu.be/t6or4fR2c-k" target="_blank"><img alt="Sonyx" src="./assets/sonyx-thumbnail.png" height="200"></a>
  
  Sonyx is a research prototype that attempts to **support exploratory programming tasks** through the use of **auditory displays.** Programmers can define custom **ad-hoc sonifications** of individual program elements to inspect and monitor their source code. Our user study indicated that auditory displays can make programmers more satisfied and effective.

## Publications

- Christoph Thiede, Marcel Taeumel, and Robert Hirschfeld. 2023. [Object-centric Time-Travel Debugging: Exploring Traces of Objects.](https://2023.programming-conference.org/details/px-2023-papers/9/Object-centric-Time-Travel-Debugging-Exploring-Traces-of-Objects) In Proceedings of the Programming Experience 2023 (PX/23) Workshop, companion volume to the International Conference on the Art, Science, and Engineering of Programming (\<Programming\>), Tokyo, Japan. 7 pages. To appear.
- Christoph Thiede, Willy Scheibel, Daniel Limberger, and Jürgen Döllner. 2022. [Augmenting Library Development by Mining Usage Data from Downstream Dependencies.](https://www.researchgate.net/publication/360231022_Augmenting_Library_Development_by_Mining_Usage_Data_from_Downstream_Dependencies) In Proceedings of 17th International Conference on Evaluation of Novel Approaches to Software Engineering (ENASE 2022). 221–232. DOI: [10.5220/0011093700003176](https://doi.org/10.5220/0011093700003176)
- Christoph Thiede and Patrick Rein. 2021. [Squeak by Example.](https://wiki.squeak.org/squeak/6546) Vol. 5.3.1.

## Philosophy

I am striving to base my work on the following values:

- [**Agile:**](https://agilemanifesto.org/) Engineering should be fun, but rigid processes aren‘t! Just as slow feedback loops in your IDE can get you tired and risk-averse, delayed human feedback can also be deadly for any project. In my projects, I always seek to stay flexible and give and receive feedback as early as possible.
- **Openness by default:** Black boxes are mean, whether on an implementational or organizational level. Transparent artifacts teach us, inspire us, and they can avoid annoying communication overhead. Whenever possible, I document and publish each of my projects.
- **Talk to people, not to machines:** Code should always tell us a story and not be obfuscated by tiny optimizations. If the computer does not get your code fast, optimize the compiler, not your code. In 90% of all cases, readability matters more than performance. In the remaining 10%, I make sure to document my intentions.
- **[Kaizen](https://en.wikipedia.org/wiki/Kaizen) (改善, change for the better):** There is no perfect process, so reflection and improvement should be part of every process. In particular, I also apply kaizen to my own philosophy. :-)
