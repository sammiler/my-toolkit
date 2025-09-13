<p align="right">
  <a href="./knowledge-management.md">English</a> | <a href="./knowledge-management_zh-CN.md">简体中文</a>
</p>

# 🧠 My Knowledge Management System: A Deep Dive

This document provides a detailed breakdown of the philosophy, tools, and workflow behind my knowledge management system, which was summarized on the main `README.md`.

### The Philosophy: Library -> Workbench -> Lab

I view knowledge management as a three-stage process, not just two:

1.  **The Library (Input & Storage)**: This is where I collect and preserve high-fidelity information from the outside world. The goal is accuracy and preservation. It's my personal, incorruptible archive.
2.  **The Workbench (Drafting & Incubation)**: This is the messy, creative space where raw materials from the library are first processed. It's for drafting notes, capturing fleeting ideas, and letting thoughts marinate before they are ready for permanent structuring.
3.  **The Lab (Synthesis & Creation)**: This is where refined ideas from the workbench are forged into lasting knowledge. I break them down, connect them with other ideas, and build my own understanding. The goal is creation, not just collection.

---

### The Tools in Detail

#### 📚 The Library: [Zotero](https://www.zotero.org/) 

*   **Zotero**: My central hub for managing all source materials.
    *   **Why Zotero?**: It's open-source, non-profit, and has an incredible browser connector for one-click capture of web pages, articles, and PDFs. It handles metadata flawlessly.
    *   **My Setup**: I use the Zotero desktop client. Metadata is synced via Zotero's free service, which is highly reliable.

#### 📝 The Workbench: [Joplin](https://joplinapp.org/)

*   **Why Joplin?**: If Trilium is the "lab" for building a permanent palace of knowledge, Joplin is my "field notebook" and "workbench." It's where I capture daily fleeting thoughts, meeting minutes, article drafts, and quick ideas. Its core strengths are its outstanding cross-platform sync, robust Markdown editor, and end-to-end encryption.
*   **Key Features I Use**:
    *   **Excellent Markdown Editor**: First-class support for Markdown, including code blocks, math notation, and diagrams, makes it ideal for drafting technical notes.
    *   **Web Clipper**: Unlike Zotero's archival-grade capture, Joplin's clipper saves articles as editable Markdown, which is perfect for deconstruction and synthesis later.
    *   **End-to-End Encryption (E2EE)**: All notes are encrypted on the client before being sent to my sync target, ensuring maximum privacy.
    *   **Self-Hosted Sync Target**: I point Joplin to my Nextcloud instance (via WebDAV), meaning all my notes are securely stored on my own server, achieving full data sovereignty.

#### 🧠 The Lab (Second Brain): [Trilium Notes](https://github.com/zadam/trilium)

*   **Why Trilium?**: It's a hierarchical note-taking app designed specifically for building personal knowledge bases. It is the permanent, structured home for my synthesized knowledge.
*   **Key Features I Use**:
    *   **Note Hierarchy**: Perfect for structuring thoughts from broad topics to fine details.
    *   **Note Cloning & Linking**: Allows a single note to exist in multiple places, creating a powerful, non-linear knowledge graph that mimics the brain.
    *   **Self-Hosted**: My entire knowledge base resides on my VPS, ensuring privacy and longevity.

---

### The Complete Workflow: A Step-by-Step Example

1.  **Capture (The Library)**: I find an interesting article on C++ Concepts. I click the Zotero Connector in my browser. The article's metadata and a full offline snapshot are saved to Zotero. The snapshot file is automatically uploaded to my hacdias/webdav server.
2.  **Consume (The Library)**: Later, I open Zotero and read the article. I use the built-in reader to highlight key sentences and add annotations.
3.  **Draft & Incubate (The Workbench)**: I open Joplin. I create a new note like "Initial thoughts on C++ Concepts." Here, I jot down my first reactions, copy a few key quotes, and write a disorganized draft. This note is an "incubator"—a temporary holding space for ideas before they are moved into the permanent knowledge base.
4.  **Synthesize (The Lab)**: I open Trilium, with Zotero's highlights and my Joplin draft side-by-side. I **do not copy-paste**. I read my own draft and the source highlights, and then, **in my own words**, I distill and structure the core ideas into a new, permanent Trilium note titled "C++ Concepts Explained."
5.  **Connect (The Lab)**: While writing in Trilium, I mention "template metaprogramming." I immediately create a link `[[like this]]` to my existing note on that topic. My new, synthesized knowledge is now officially woven into my existing mental map.