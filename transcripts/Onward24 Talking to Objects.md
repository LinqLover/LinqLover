---
title: Talking to Objects in Natural Language
description: Toward Semantic Tools for Exploratory Programming
---

# Talking to Objects in Natural Language: Toward Semantic Tools for Exploratory Programming

*This is a transcript of my [talk](https://2024.splashcon.org/details/splash-2024-Onward-papers/6/Talking-to-Objects-in-Natural-Language-Toward-Semantic-Tools-for-Exploratory-Program) for the Onward! 2024 conference, polished by AI (ChatGPT) and revised manually. For more details, please check out the [slides](../slides/Onward24%20Talking%20to%20Objects.pdf) and the [full paper](https://doi.org/10.1145/3689492.3690049).*

## Introduction

Thank you for the kind introduction. I hope the weather is nice in LA, and welcome to my presentation. Let me start with a brief introduction to what we’re discussing today: exploratory programming. In this practice, programmers iteratively work with systems to understand problems and create solutions. These programmers have many questions about the objects they are working with, like “What is this object about?” or “How can I invoke this feature?” or “Why does this not work as expected?”

To answer these questions, programmers perform various experiments using different tools and interfaces to interact with the system’s objects. The problem is that many of these interfaces are technical, involving command-line instructions or graphical user interfaces, which can be cumbersome and complex to use. The results these tools provide can also be difficult to interpret, leading to cognitive overload for the programmer. This complexity impedes the overall exploratory programming experience.

![Answering questions about objects requires interactions with the system, which involves technical complexity and cognitive overhead.](Onward24%20Talking%20to%20Objects.assets/intro_complexity.png)

On the other hand, we are seeing more and more generative AI agents being used in software development to support tasks related to code comprehension and interaction. This made us wonder: why can we not use similar agents to streamline and augment the exploration of objects in an interactive and dynamic context?

This brings us to our solution: we propose an **exploratory programming agent** that acts as an intermediary between the programmer and the system. The programmer can ask high-level, natural language questions, which the agent translates into technical experiments. The agent then automatically performs these experiments and provides a natural language response to the programmer.

Our key research question thus is: **how can we support exploratory programming through semantic object interfaces that enable contextual natural language conversations about objects?**

In this paper, we make three contributions:

1. We propose a framework for semantic object interfaces.
2. We implement a prototype for the Squeak/Smalltalk system using GPT-4.0 as the underlying language model.
3. We evaluate our solution based on our experience with this implementation.

## Background

**Exploratory programming** can be defined as programmers understanding problems and systems iteratively. For this, they formulate questions, conduct experiments, and evaluate the results. This process can be thought of as a form of conversation with the system, where these experiments are like dialogue between the programmer and the system.

To support this kind of iterative conversation, we need exploratory programming systems that offer short feedback loops and support vivid, extensive interaction. There are already systems like Smalltalk, operating system shells, computational notebooks, and other domain-specific tools like debuggers and code browsers that aim to provide this interactivity. However, it’s crucial to minimize the feedback cycle and bridge the so-called “gulf of execution and evaluation,” a concept from human-computer interaction that refers to the gap between what programmers intend to do and what the system actually does. Programmers often face challenges in translating their intentions into the technical interfaces of the system and interpreting the system’s output back into their mental model.

Meanwhile, we’ve already seen the successful integration of **generative AI into programming tools** like GitHub Copilot for code completion, conversational agents, and code review tools. However, these tools tend to focus solely on static source code, ignoring dynamic runtime behavior, which is crucial for understanding the system in an interactive context.

## Approach

Our solution is to bridge this gap with **semantic object interfaces,** where programmers no longer need to perform manual experiments to interact with objects in the system. Instead, they can ask high-level, semantic questions through an **exploratory programming agent,** which automatically plans and executes the necessary experiments and provides the answers in natural language.

![Our framework of semantic object interfaces.](Onward24%20Talking%20to%20Objects.assets/approach.png)

The agent can access various interfaces in the system to inspect object states, read implementations, or send messages to objects. It follows specific policies that describe its behavior and maintains a conversation history to ensure that interactions are context-aware and continuous.

The programmer can ask two types of questions: **functional questions** about the state of the system, such as “When was this order created?”, and **epistemic questions** about the behavior of the system, such as “How does the ranking mechanism of this online store work?”.

## Integration in Exploratory Programming Systems

To integrate these semantic object interfaces into existing programming systems, we identified two common entry points that programmers use to explore objects:

**Object inspection tools** are typically found in interactive debuggers, computational notebooks, or Smalltalk systems and allow programmers to view lists of object properties. We added a new **conversation mode** to these tools so programmers can have a natural language conversation about the objects they are inspecting.

![A conversation mode for object inspection tools.](Onward24%20Talking%20to%20Objects.assets/integration_inspector.png)

**Scripting and messaging:** In object-oriented systems, programmers often send messages to objects in the system via scripting. We propose adding support for **semantic messages** that the exploratory agent handles, performing automated experiments and returning answers in the scripting context.

```smalltalk
aProduct orderItems mostOftenBoughtOne == aProduct mostPopularArticle.
aProduct numberOfSalesTo: aCustomer.
aProduct countSalesFrom: '2023Q3' to: '2023Q4'.
```

## Implementation

For our prototype, we used the **GPT-4o language model.** We defined detailed policies that describe the agent’s expected behavior, identity, and output format. One challenge we faced was that the language model was initially “lazy,” performing only minimal experiments before answering a question. To encourage the agent to engage in more thorough exploration, we used few-shot prompting with examples of multiple experiments.

Additionally, we connected the agent to system interfaces, providing it with functions for evaluating code, browsing the implementation, and exploring the call graph.

## Demos

Now let me show you how this works in practice.

### Demo #1: Shopping System

Let’s say we are working with an order object from a shopping system, and I want to find out when this order was created. Typically, I would inspect the object manually: let’s open the object inspector, where we can see various properties. Here’s an integer that looks like a creation timestamp, but it’s not in a human-readable form. I’ll have to convert it, maybe using a Unix timestamp conversion method. Eventually, I figure out that it’s a millisecond timestamp and get the correct date by dividing by 1000, but this process was tedious and time-consuming.

Now, instead, I’ll ask the agent: “When was this order created?” The agent takes over, performs all the necessary experiments, and provides the correct date in seconds, saving me both time and cognitive effort.

![Chatting with an order object from a shopping system.](../assets/SemanticSqueak-agent.png)

### Demo #2: Text Formatting in Squeak

In this next example, let’s explore a text object used for formatting strings in Squeak. I want to know what attributes this text object contains. By using the agent’s conversational interface, I simply ask: “What attributes do you contain?” The agent responds with a list of attributes, like bold or underline codes. Next, I ask: “What do these codes mean?” The agent searches through documentation and finds that the codes represent different formatting instructions. Finally, I ask: “Can you give me some code examples to change this text object?” The agent experiments with the system, trying different approaches and then presents me with working code examples.

![Chatting with a formatted text object in Squeak.](Onward24%20Talking%20to%20Objects.assets/demo_text.png)

### Demo #3: Generic UI Integration

We also have a broader vision for integrating this concept into other types of user interfaces beyond object inspection tools. In fact, many systems—whether in exploratory programming or even other domains like project management or presentation software—use **object-oriented user interfaces.** Our idea is to introduce a generic mechanism that allows programmers to select any domain object within the UI and ask natural language questions about them. Note that for this, individual applications do not have provide their own agents, but instead our exploratory programming agent will research and use the available interfaces of each domain autonomously.

In exploratory programming systems, we can apply this concept by allowing programmers to interact with different tools that employ object-oriented user interfaces. Code browsers already provide access to meta-objects like classes and methods, editors provide access to nodes in the AST, and debuggers offer access to processes and call stacks. With our exploratory programming agent, we can add semantic conversations to these interfaces, enabling direct interaction with code artifacts.

Let me show you a quick demo. I will open a class browser and, instead of manually searching through the class’s responsibilities, I can right-click on the class and ask, “What are the responsibilities of this class?” The agent will access the documentation and implementation, then provide a summary of the class’s responsibilities.

Another example is using the debugger. Suppose I’m debugging a method and encounter a `failBlock` variable. I don’t understand where this block comes from or what it does. Instead of inspecting everything manually, I ask, “Where is `failBlock` from, and what exactly does it do?” The agent will analyze the call stack and provide an answer, helping me understand its role without the need for manual exploration.

![Chatting with the call stack of a program in a debugger.](Onward24%20Talking%20to%20Objects.assets/demo_debugger.png)

## Discussion

We discuss our approach with regard to the feasibility of our agent and the impact of semantic object interfaces on the programming experience.

**Feasibility:** There are limitations to using large language models, including occasional hallucinations, incorrect reasoning, and invalid code generation. However, we believe these issues can be mitigated by training the model on more specific tasks, such as working with Squeak/Smalltalk, or exploratory programming practices in general. Performance can also be an issue, as more complex tasks may take longer or cost more computational resources. When using our prototype continuously for one hour, programmers might spend up to $60. However, we believe this can be optimized by fine-tuning smaller models or improving the prompt design.

**Impact on Programming Experience:** Semantic object interfaces provide a higher level of abstraction, reducing interruptions and cognitive overhead while improving the semantic immediacy and flow of programmers. However, there is a risk of **leaky abstractions,** where the agent fails, requiring the programmer to fall back on manual exploration. Another potential downside is the loss of **serendipitous discoveries**—the kind of learning that happens when programmers manually browse code and accidentally stumble upon useful insights they weren’t initially looking for. Automating too much of this process may prevent these discoveries from happening. On the positive side, the **natural language interface** reduces the gulf of execution and evaluation by allowing more intuitive interaction with the system, and the agent’s ability to carry conversation context makes follow-up questions easier and more natural.

Finally, we are affected by some limitations of LLMs described earlier. First, trust can be an issue, as LLMs are known to sometimes fail or produce errors, including hallucinations or invalid code, which can lead to reduced confidence in relying on the agent. Additionally, temporal distances can occur, as the agent may take too long to respond for more complex tasks, interrupting the workflow. Another limitation we observed is the fear of expenses—often, I found myself debating if asking a question was worth the potential cost. Even a dollar per question can add up, making some programmers hesitant to use the agent frequently if simpler options exist. Finally, there are environmental aspects to consider. For example, depending on the region, using the agent throughout a full workday could consume several hundreds of liters of water. These factors make optimization essential, both from a sustainability and cost-effectiveness perspective.

## Future Work

As for future directions, the first area we’ll focus on is improving the capability and performance of the agent, either by fine-tuning a smaller language model or by optimizing the prompt itself. Additionally, we are interested in finding ways to enhance collaboration between programmers and agents. We aim to avoid fully automating everything and, instead, keep programmers in the loop. One possible approach is to improve the explanations provided by the agent, allowing programmers to build on the intermediate insights offered by the agent rather than depending solely on its final answers.

## Conclusion

In conclusion, we have proposed a framework for semantic object interfaces that allows programmers to ask high-level semantic questions about objects using an exploratory programming agent. We have demonstrated its integration into object inspection tools and scripting environments and shown its potential to improve the programming experience by reducing cognitive overhead and interruptions. However, there are still areas for optimization, especially regarding performance and trust in the agent’s outputs.

Thank you for your attention, and I look forward to the discussion. After the time is over, I’m happy to take further questions on Discord.
