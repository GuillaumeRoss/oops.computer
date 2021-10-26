---
title: "Hello World"
date: 2021-10-20T20:51:26-04:00
draft: false
tag: ["mermaid"]
categories: ["Secure Startup"]

---

# Mermaid Test

## Flow

<div class="mermaid">
graph TD;
  A-->B;
  A-->C;
  B-->D;
  C-->D;
</div>

## Gantt
<div class="mermaid">
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
</div>
