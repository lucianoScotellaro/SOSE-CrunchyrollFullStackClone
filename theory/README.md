The idea and the **goal** of the **project**, as mentioned in the [project README](../README.md), is to **build** an **over-the-top video on-demand streaming system**. In order to do this it is firstly needed to understand the following basic concepts:

1. What is an over-the-top video on-demand streaming system
2. How does an over-the-top video on-demand streaming system work
3. How does an over-the-top video on-demand streaming system is implemented

All these topics are discussed in this **document** that covers **all** the **theoretical background** needed for the design and the implementation of the project.

## Streaming Systems

To **understand** what an **over-the-top video on-demand streaming system** is, and what are its goals, we firstly **need** to understand the definition and the goals of **streaming systems** **in general**. For this reason the first two sections of the document will focus on giving a broader view on streaming systems as a whole.  

### Definition: what is a streaming system

A streaming system is a system whose **goal** is to **produce**, **transmit**, and **consume** a **continuous**, and potentially **unbounded**, **stream** of **data** in an **incremental manner**.

_N.B. The **incremental handling** of these three operations is **crucial** in the definition of a streaming systems, since it makes them able to **solve** the **problems** they are **built for**._

### Motivation: why do streaming systems exist

The **existence** of streaming systems was made **necessary** by the need for the implementation of **two classes** of **real-world problems**:

1. **Problems** dealing with potentially **unbounded data**, in which **waiting** for the **complete availability** is **not possible** (e.g. monitoring problems and/or analytics problems).
2. **Problems** with **big data transfers** and **low-latency requirements**, in which **waiting** for the **complete availability** is **not desirable** (e.g any real-time problem).

The ideation of **streaming systems** has **allowed** to **deal with** these two classes of **problems** by **incrementally handling** the data **stream**. This incremental handling enables the computation of potentially unbounded streams of data in the first class of problems, and the lowering of latencies in the second class of problems.

### Over-the-top video on-demand streaming systems

**Over-the-top video on-demand streaming systems** are a **specific subclass** of streaming systems whose purpose is **allowing** **users** to **play** **video content** **whenever they want** with **low playback latency**. 

In over-the-top video on-demand streaming systems the **data stream** is **composed** by **multimedia data** (video), **transmitted** **upon** user's **request** (on-demand), **using** the **Internet infrastructure** as communication mean (over-the-top).

_N.B. Since the problem that these systems are trying to solve is mainly a latency problem, they belong to the **second class** of **streaming systems** mentioned earlier._

## Functioning: how do streaming systems work

### Anatomy: what are the components of streaming systems

### How does an over-the-top video on-demand streaming system work

### Need for speed (spiegazione sistemi di streaming in generale hanno bisogno di velocità)
Performance => Content Delivery Networks to lower latency

Being streaming systems, one of the most important requirements for over-the-top video on-demand systems is the ability to deliver content very fast (in real time(?)).

This need for very low latencies between content provider and client is typically handled using networks of distributed servers that can rapidly deliver in any point of a given area. These networks are called content delivery networks and are the backbone of any streaming system.

## How does an over-the-top video on-demand streaming system is built (spiegazione implementazione)

### Content Delivery Networks (spiegazione content delivery networks)

#### What are Content Delivery Networks

#### How do Content Delivery Networks work

Mapping clients to edge servers through DNS resolution

### Domain Name System

#### What is the Domain Name System

#### How does Domain Name System work