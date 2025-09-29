# Live Word Abbreviator

A tiny, client-side utility (live [here](https://thiagovscoelho.github.io/abbreviator/)) that **compresses everyday English prose by replacing very common words and suffixes with single Unicode symbols**.  
Flip the switch and it instantly reverses the process, restoring the original text.

*Why?*  
- Write shorter social posts or personal notes.  
- Have fun designing ultra-compact codes with friends.  
- Explore creative, emoji-rich “shorthand” without losing meaning (everything rounds-trips!).

---

## ✨ Features
- **Live conversion** – keystroke-by-keystroke in the browser, no page reloads.
- **Bidirectional** – _Abbreviate_ ✧ _Un-abbreviate_ with a single radio button.
- **Plain HTML/JS** – drop the file anywhere; no build step or network calls.
- **Extensible maps** – add or change symbols in one place.

---

## 🚀 Quick Start

```bash
git clone https://github.com/your-handle/live-word-abbreviator.git
cd live-word-abbreviator
open index.html          # or serve it with any static web server
```

Type in the first box, watch the second box transform.

---

## 🔡 Word-to-Symbol Map

| Word   | Symbol | Word    | Symbol | Word      | Symbol |
| ------ | :----: | ------- | :----: | --------- | :----: |
| after  |    ≻   | all     |    ∀   | also      |    ∧   |
| am     |   𝐦   | an      |   𝐧   | and       |    &   |
| any    |    ✲   | are     |   𝐫   | as        |    ∷   |
| at     |    @   | be      |   𝐛   | because   |    ∵   |
| been   |   🚮   | before  |   ≺   | both      |    ⊓   |
| but    |    ⧹   | by      |   𝑏   | call      |   📞   |
| can    |   🥫   | could   |    ◇   | different |    ≠   |
| during |    ∥   | each    |   𝐞   | first     |   🥇   |
| for    |   𝟒   | four    |    4   | from      |    ⊸   |
| had    |    ⊐   | has     |    ⊃   | have      |    ⋑   |
| he     |    ▲   | her     |    ▽   | hers      |    ▿   |
| him    |    △   | his     |    ▴   | if        |   𝐶   |
| in     |    ⊆   | ing¹    |   𝑛   | into      |    ➲   |
| is     |    ∈   | it      |    ▶   | its       |    ▸   |
| known  |    κ   | later   |   🌇   | less      |    <   |
| look   |   👀   | main    |   📌   | many      |    ∞   |
| may    |    ◆   | more    |    >   | most      |    ⊤   |
| new    |   🆕   | no      |    ∄   | not       |    ¬   |
| number |    №   | of      |    ∩   | often     |    ◕   |
| on     |   🔛   | one     |   𝟏   | only      |    只   |
| or     |    ∨   | other   |    ≢   | out       |    出   |
| over   |    ⧸   | people  |   👥   | same      |    =   |
| she    |    ▼   | small   |    ϵ   | so        |    ☰   |
| some   |    ∃   | such    |    ∋   | system    |   🌌   |
| than   |    ⊱   | that    |    那   | the       |    τ   |
| their  |    ◂   | theirs  |    ◃   | them      |    ◁   |
| then   |    →   | there   |   📍   | these     |   🥜   |
| they   |    ◀   | think   |   🧠   | this      |    这   |
| three  |    3   | through |    ⇀   | time      |   🕰️  |
| to     |    ⇒   | two     |    2   | up        |   🆙   |
| us     |   𝑠   | use     |   🔧   | used      |    유   |
| want   |    要   | was     |    ω   | well      |   🚰   |
| were   |    ώ   | when    |   𝑡   | where     |   🗺️  |
| which  |    ⦂   | who     |   👤   | will      |    ⇛   |
| with   |   𝐰   | work    |   𝑊   | would     |   🪵   |
| you    |   𝐮   | your    |   𒌨   | again         |    又   |
| therefore    |   ∴   |     |      |          |       |

¹*See the suffix table below.*

---

## 🔣 Suffix Map

| Suffix    | Symbol | Example    | ➜ | Abbrev.   |
| --------- | :----: | ---------- | - | --------- |
| **-tion** |    श   | nation     | → | naश       |
| **-ship** |   🚢   | friendship | → | friend🚢  |
| **-ing**  |   𝑛   | running    | → | run𝑛     |
| **-ed**   |   𝑑   | replaced   | → | replac𝑑 |
| **-er**   |   𝑟   | builder    | → | build𝑟   |
| **-ers**  |   𝑟s  | players    | → | play𝑟s   |
| **-or**   |   𝓇   | creator    | → | creat𝓇   |
| **-ors**  |   𝓇s  | investors  | → | invest𝓇s |
| **-ss**   |   ß  | moss        | → | moß      |

---

## 🛠 How It Works

1. **Whole-word phase** – Replaces complete words using a case-insensitive lookup (`wordMap`).
2. **Suffix phase** – Runs longest-suffix-first replacements (`suffixMap`).
3. **Reverse mode** – Uses the same tables in reverse, plus a tiny regex to respect word boundaries.

Everything happens in \~200 lines of vanilla JavaScript—no dependencies.

---

## 🧩 Customisation

Open `index.html`, find the **Data** section, and add entries:

```js
const wordMap = {
  ...,
  "example": "🔰"      // new word
};

const suffixMap = {
  ...,
  "ology": "🧪"        // new suffix
};
```

---

## 👩‍💻 Development Scripts

```bash
# Serve with live reload (requires VS Code Live Server, http-server, etc.)
npx http-server .
```

No build step needed; just edit and refresh.

---

## 📄 License

Public domain (CC0)

---

Enjoy shrinking your sentences! ✂️
