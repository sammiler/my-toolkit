<p align="right">
  <a href="./information-intake.md">English</a> | <a href="./information-intake_zh-CN.md">简体中文</a>
</p>

# 🌊 Deep Dive: Information Intake Workflow

This workflow is my defense against information overload. It's a systematic process for discovering, filtering, and consuming high-quality content from the web, designed to feed my knowledge system with valuable input rather than noise.

---

### 📡 Radar: [FreshRSS](https://freshrss.org/)

**Why I chose it**: RSS is the cornerstone of a self-directed information diet, free from algorithmic control. I chose FreshRSS because it offers a comprehensive, feature-rich, and mature platform for aggregating feeds.

**Core Advantages**:
*   **Feature-Complete**: It's a "batteries-included" solution with multi-user support, robust feed management, powerful filtering rules, and statistics, covering all my needs out of the box.
*   **Healthy Ecosystem**: As a long-standing project, FreshRSS is supported by a wide array of excellent third-party mobile clients (like Reeder or NetNewsWire) via its Fever and Google Reader APIs.
*   **Extensible**: It supports a plugin system that allows for further enhancements, such as a one-click "Send to Wallabag" integration.

**Alternatives Considered**:
*   `Miniflux`: An excellent choice for minimalists who prioritize raw speed. However, I prefer the richer feature set and more traditional UI of FreshRSS for managing a large number of feeds.

---

### 🍵 Reading Room: [Wallabag](https://wallabag.org/)

**Why I chose it**: Wallabag is the perfect companion to an RSS reader. It serves as a dedicated space for long-form, focused reading. When I find an article in FreshRSS that requires deep attention, I send it to Wallabag.

**Core Advantages**:
*   **Distraction-Free Reading**: Wallabag extracts the core content of an article, stripping away ads, pop-ups, and other clutter. This creates a serene reading environment.
*   **Archiving**: It saves a permanent copy of the article on my server. This protects against link rot and ensures I always have access to the content, even if the original page disappears.
*   **Annotation and Portability**: It allows for highlighting and note-taking. Articles can also be exported to e-reader formats like EPUB, which is perfect for offline reading on a Kindle or similar device.

---

### 🕵️ Scout: [ChangeDetection.io](https://github.com/dgtlmoon/changedetection.io)

**Why I chose it**: RSS is fantastic, but not every website offers a feed. ChangeDetection.io fills this critical gap. It acts as a vigilant scout, monitoring specific pages for any visual or textual changes. This is perfect for tracking software updates, price changes, or any important information on static pages.

**Core Advantages**:
*   **Granular Control**: It can monitor an entire page, a specific area defined by CSS selectors, or even just a snippet of text. This precision filtering eliminates false positives.
*   **Powerful Notifications**: It integrates with a vast array of notification services, ensuring I get alerted immediately in the way I prefer.
*   **Fills the RSS Gap**: It effectively allows me to "create a feed" for any website, making my information intake system comprehensive and complete.