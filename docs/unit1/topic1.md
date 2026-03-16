# Introduction to Software Architecture

> The fundamental organization of a system embodied in its ==**components**==, their ==**relationships to each other, and to the environment**==, and the ==**principles guiding**== its design and evolution.

## 1.1 Background and Histroy

## 1.2 Introduction

The industry as a whole has struggled to precisely define “software architecture”. Some architects refer to software architecture as the blueprint of the system, while others define it as the roadmap for developing a system. The issue with these common definitions is understanding what the blueprint or roadmap actually contains.
For example, what is analyzed when an architect analyzes an architecture?

In the book, _"The Fundamentals of Software Architecture"_[^1] gives a way to think about software architecture. In this definition, software architecture consists of the

1. Structure of the system (denoted as the heavy black lines supporting the architecture)
2. Architecture characteristics (“-ilities”) the system must support
3. Architecture decisions
4. Design principles.

### 1.2.1 Structure of the System

<figure markdown="span">
    ![structure](/image/Structure.png){width="80%"}
    <figcaption>Structure: Refering to the type of architecture style used in the system</figcaption>
    <p align='right' style="font-size:0.8em"><i>Image Source: Fundamental of Software Architecture, chapter 1, pg 3</i></p>
</figure>

The structure of the system, as illustrated in the figure, refers to the type of architecture style (or styles) the system is implement in (such as microservices, layered, microkernel, and so on).

### 1.2.2 Architecture characteristics

<figure markdown="span">
    ![structure](/image/Characteristics.png){width="80%"}
    <figcaption>Structure: Refering to the type of architecture style used in the system</figcaption>
    <p align='right' style="font-size:0.8em"><i>Image Source: Fundamental of Software Architecture, chapter 1, pg 3</i></p>
</figure>

Architecture characteristics is another dimension of defining software architecture. The architecture characteristics define the success criteria of a system, which is generally orthogonal to the functionality of the system. They are the important non functional requirements of the system.

### 1.2.3 Architecture decisions

<figure markdown="span">
    ![structure](/image/DesignPrinciples.png){width="80%"}
    <figcaption>Structure: Refering to the type of architecture style used in the system</figcaption>
    <p align='right' style="font-size:0.8em"><i>Image Source: Fundamental of Software Architecture, chapter 1, pg 3</i></p>
</figure>

### 1.2.4 Design principles.

<figure markdown="span">
    ![structure](/image/ArchitectureDesign.png){width="80%"}
    <figcaption>Structure: Refering to the type of architecture style used in the system</figcaption>
    <p align='right' style="font-size:0.8em"><i>Image Source: Fundamental of Software Architecture, chapter 1, pg 3</i></p>
</figure>

[^1]: The Fundamentals of Software Architecture by Mark Richards & Neal Ford
