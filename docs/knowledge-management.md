<p align="right">
  <a href="./knowledge-management.md">English</a> | <a href="./knowledge-management_zh-CN.md">简体中文</a>
</p>

# 🧠 My Knowledge Management System: A Deep Dive

This document provides a detailed breakdown of the philosophy, tools, and workflow behind my knowledge management system, which was summarized on the main `README.md`.

### The Philosophy: Library vs. Lab

I view knowledge management as a two-stage process:

1.  **The Library (Input & Storage)**: This is where I collect and preserve high-fidelity information from the outside world. The goal is accuracy and preservation. It's my personal, incorruptible archive.
2.  **The Lab (Synthesis & Creation)**: This is where I take the raw materials from the library and experiment. I break them down, connect them with other ideas, and forge my own understanding. The goal is creation, not just collection.

---

### The Tools in Detail

#### 📚 Personal Library: [Zotero](https://www.zotero.org/)

*   **Zotero**: My central hub for managing all source materials.
    *   **Why Zotero?**: It's open-source, non-profit, and has an incredible browser connector for one-click capture of web pages, articles, and PDFs. It handles metadata flawlessly.
    *   **My Setup**: I use the Zotero desktop client. Metadata is synced via Zotero's free service, which is highly reliable.
*   **hacdias/webdav**: My self-hosted backend for file storage.
    *   **Why hacdias/webdav?**: It provides a robust WebDAV server. All my PDFs and web snapshots are synced to my own VPS via WebDAV, giving me full data ownership and unlimited storage.

#### 🧠 Second Brain: [Trilium Notes](https://github.com/zadam/trilium)

*   **Why Trilium?**: It's a hierarchical note-taking app designed for building personal knowledge bases.
    *   **Key Features I Use**:
        *   **Note Hierarchy**: Perfect for structuring thoughts from broad topics to fine details.
        *   **Note Cloning & Linking**: Allows a single note to exist in multiple places, creating a powerful, non-linear knowledge graph.
        *   **Self-Hosted**: My entire knowledge base resides on my VPS, ensuring privacy and longevity.

---

### The Complete Workflow: A Step-by-Step Example

1.  **Capture**: I find an interesting article on C++ Concepts. I click the Zotero Connector in my browser. The article's metadata and a full offline snapshot are saved to Zotero. The snapshot file is automatically uploaded to my hacdias/webdav server.
2.  **Consume**: Later, I open Zotero and read the article. I use the built-in reader to highlight key sentences and add annotations.
3.  **Create**: I open Trilium. I create a new note titled "C++ Concepts Explained" under my "C++ Programming" parent note.
4.  **Synthesize**: I **do not copy-paste**. I read my highlights in Zotero and, **in my own words**, summarize the core ideas into my Trilium note.
5.  **Connect**: While writing, I mention "template metaprogramming." I immediately create a link `[[like this]]` to my existing note on that topic. My new knowledge is now officially part of my existing mental map.