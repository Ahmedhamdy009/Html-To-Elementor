# Universal HTML to Elementor Conversion Skill
### Next-Gen Agent Skill for Frontier AI Models & Agentic IDEs

A professional, autonomous, and future-proof **Universal Agent Skill** designed for frontier AI reasoning models (**Gemini 3+, Claude 3.7+, OpenAI o1 / o3 / GPT-4o, DeepSeek R1 / V3, Llama 3.3/4**, and open weights) across modern agent runtimes (**Google Antigravity, Claude Code, Cursor, Windsurf, Cline, Roo Code, Aider, GitHub Copilot**).

It enables coding agents to convert static HTML/CSS/JavaScript websites into native, fully-editable WordPress Elementor pages, theme components, and exportable/importable JSON templates (`version: 0.4, type: page`) with zero HTML dumping.

---

## ⚡ Future-Proof Highlights

* **Model & Agent Agnostic**: Compatible with any AI agent supporting the Agent Skills format or markdown system instructions.
* **Modern Container Architecture**: Fully supports Elementor 3.18+ / 3.24+ / 4.x Flexbox Containers and native CSS Grid Containers (`container_type: "grid"`).
* **Strict Anti-HTML-Dump Mandate**: Enforces client editability. Headings ➔ `heading`, paragraphs ➔ `text-editor`, buttons ➔ `button`, icons ➔ `icon`, media ➔ `image`.
* **Zero Entity Sanitization Pitfalls**: Built-in rules against using child combinators (`>`) in Elementor custom CSS, preventing WordPress DB entity corruptions (`&gt;`).
* **Bidirectional Layouts (RTL / LTR)**: Native handling of Arabic, Hebrew, and Latin layouts with automatic flex reversal and mirrored paddings.
* **Autonomous Forensic Verification**: Includes a local, zero-dependency Python validator (`validate_elementor_template.py`) that performs schema validation, checks ID uniqueness, and computes an automated **Editability Score**.

---

## 📂 Repository Structure

```text
html-to-elementor/
├── SKILL.md                                 # Core agent instructions & 5-phase conversion workflow
├── README.md                                # Setup, usage & platform integration guide
├── references/
│   └── elementor-template-schema.md         # Elementor JSON schema specification & widget dictionary
└── scripts/
    └── validate_elementor_template.py       # Standalone Python validator (zero external dependencies)
```

---

## 🛠️ Multi-Platform Setup Guide

### 1. Google DeepMind Antigravity
Clone directly into your global skills directory:
```bash
# Windows
git clone https://github.com/Ahmedhamdy009/antigravity-html-to-elementor.git "%USERPROFILE%\.gemini\config\skills\html-to-elementor"

# Linux / macOS
git clone https://github.com/Ahmedhamdy009/antigravity-html-to-elementor.git ~/.gemini/config/skills/html-to-elementor
```

### 2. Claude (Claude Code CLI / Desktop / Web)
* **Claude Code**: Clone or copy into your project's `.claude/skills/` directory:
  ```bash
  mkdir -p .claude/skills
  git clone https://github.com/Ahmedhamdy009/antigravity-html-to-elementor.git .claude/skills/html-to-elementor
  ```
* **Claude Web / Desktop Projects**: Attach or paste the content of `SKILL.md` into your Project Knowledge or initial prompt.

### 3. Cursor IDE
* Place this repository inside `.cursor/skills/html-to-elementor` or reference `SKILL.md` directly in your `.cursorrules`:
  ```markdown
  When converting HTML/CSS to Elementor, strictly adhere to the guidelines in .cursor/skills/html-to-elementor/SKILL.md.
  ```

### 4. Windsurf IDE
* Add a reference inside your `.windsurfrules`:
  ```markdown
  Follow the 5-phase conversion workflow defined in html-to-elementor/SKILL.md for all Elementor template generation tasks.
  ```

### 5. Cline / Roo Code / Aider
* Reference `SKILL.md` directly in your system prompt or `.clinerules` / `.aider.conventions.md`.

### 6. OpenAI Codex / ChatGPT / Custom GPTs
* Upload `SKILL.md` and `references/elementor-template-schema.md` as Knowledge files in your Custom GPT configuration.

---

## 💡 How to Use With Any AI Assistant

In any agent session, simply prompt:

> *"Using the `html-to-elementor` skill guidelines, analyze this website and convert it into native, client-editable Elementor JSON importable templates."*

---

## 🧪 Testing & Validation

Validate any generated Elementor JSON template locally before importing:

```bash
python scripts/validate_elementor_template.py "path/to/template-importable.json"
```

---

## 📄 License
MIT License. Free to use, modify, and distribute.
