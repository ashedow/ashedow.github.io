---
title: "(Non) Functional Requirements"
date: 2023-09-06
description: ''
featured_image: ""
tags: ["#nfr"]
draft: false
---

# Functional Requirements and Non-Functional Requirements


The traditional comparison between functional and non-functional requirements is as follows:
* **Functional requirements** apply to the specific behaviors of a system.
* **Non-functional requirements** are measurable criteria that you can use to evaluate the success of an overall system, solution, or product.

## Functional Requirements

Answers to the question - "What Should It Do?"
Functional requirements are requirements that define product features or functions that allow users to accomplish their tasks on a system.

Functional requirements are often simple to define, measure, and test. They are more easily described as requirements which tell a particular system to perform a specific function.

Functional requirements are typically less abstract than NFRs and generate very little confusion. If you asked someone to write a requirement, they would more likely create a functional requirement.



## Non-Functional Requirements

Answers to the question - "How Should It Be?"

Non-functional requirements, or NFRs, often describe software attributes like security, reliability, performance, testability, maintainability, accessibility, scalability and usability.


There are two types of non-functional requirements:
* Execution Qualities - These are security, reliability, usability and other factors that are observable during software’s user-facing runtime.
* Evolution Qualities - These are testability, maintainability, scalability and other factors that are embodied in the static structure of the software.


Some NFRs are impossible to test with code. For example, you may not be able to write a test that quantifies the maintainability of a web application. Other NFRs may introduce significant overhead if they’re included in a test suite. 

> For example, a NFR covering performance may require a large sample database in order to test record retrieval times. Development teams must balance these trade-offs when writing tests for NFRs.


[Why Non-Functional Requirements are Non-Negotiable](https://builtin.com/software-engineering-perspectives/non-functional-requirements)
[Non-Functional Requirements Explained](https://www.modernrequirements.com/blogs/pillar/what-are-non-functional-requirements/)