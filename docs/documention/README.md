# Getting Started

Mkdocs is currently my favorite documentation medium. It is lightweight, easy to setup, and the Material theme just hit's all the checkmarks out of the box.

Docasourus is a close second.

## Diagrams

When it comes to diagrams there is no one size fits all... Yet.

???+ TLDR
    As much as Mermaid fits all of my philosophy points it's just not ready for prime time. So I seattle for a combination of structurizr and Diagrams.net.

### Diagram Philosophy

I am a believer in diagrams as code. In a programming environment with many developers it is important that even a new programer on a project feels empowered to update all aspects of the documentation. Diagrams as code gives them that power in two ways.

1. There is no need to hunt down original diagrams to modify, or install/learn a new program. Vi/Emacs will do just fine ;)

2. A simple pull request will allow for developers with more domain knowledge to accurately and easily proof these changes. This makes proposing documentation and diagrams changes zero risk.

### C4 Architecture Model (Structurizr)

Site: [C4 Model](https://c4model.com)
DL: [Structurizr](https://structurizr.com/help/lite)

This model gave birth to a Domain language that treats an application architecture like a zoom-able map with separate context views.

The cons to this right now is imbedding this into other documentation systems like mkdocs is cumbersome at best.

### Mermaid

Site: [Mermaid](https://mermaid.js.org/)

Mermaid is a js renderer that takes mkdown code and converts it into a diagram.

There is a plugin for MkDocs Material already and it also supports basic Structurizr,

Controlling object placement is problematic and sometimes down right ugly or unreadable.

Structurizr support is limited and artifacts are to small to ready comfortably.

### Diagrams.net (draw.io)

Site: [diagrams.net](https://app.diagrams.net)

It can be pretty and you can embed the original diagram in a PNG file so that there is no need to hunt for the original file. The artifact is both the image and the original.