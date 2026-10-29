<p align="center">
  <img src="assets/banner.png" alt="Bit, a simple rule-based chatbot" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/dependencies-none-2F5BFF?style=flat" alt="No dependencies">
  <img src="https://img.shields.io/badge/license-MIT-16A34A?style=flat" alt="MIT License">
</p>

<p align="center">
  A rule-based chatbot with a minimalist web interface and a live, animated robot.<br>
  Type a message and Bit replies using predefined rules. One HTML file, no frameworks, no build step.
</p>

---

## Preview

<p align="center">
  <img src="assets/chat.png" alt="Light mode chat screen showing hello, how are you and bye with Bit's replies" width="48%">
  &nbsp;
  <img src="assets/chat-dark.png" alt="Dark mode chat screen with Bit thinking" width="48%">
</p>

The page follows your system setting, so it switches between light and dark mode automatically.

## Meet Bit

Bit is drawn in SVG and reacts to what you do.

<p align="center">
  <img src="assets/states.png" alt="Bit in four states: idle, listening, thinking and waving" width="70%">
</p>

| State | What happens |
| --- | --- |
| Idle | Bit smiles, floats gently, and blinks at random |
| Listening | The eyes look down while you type |
| Thinking | The eyes look up and the antenna pulses faster |
| Replying | The mouth moves while Bit talks |
| Waving | Bit waves when you say goodbye |

The eyes and head also follow your cursor or finger across the page.

## Conversation

| You say | Bit replies |
| --- | --- |
| `hello` | Hi! |
| `how are you` | I’m fine, thanks! |
| `bye` | Goodbye! |

Bit also understands `thanks`, `your name`, and `help`. Anything else gets a polite fallback message.

## How It Works

<p align="center">
  <img src="assets/code.png" alt="The getReply function using if and else if rules" width="60%">
</p>

1. `normalize()` cleans the message: lowercase, punctuation removed, extra spaces trimmed.
2. `getReply()` checks the rules from top to bottom and returns the first match.
3. If nothing matches, Bit returns a fallback reply.

The code above is a shortened view. The project has a few more rules.

### Concepts Used

| Concept | Where it appears |
| --- | --- |
| `if / else if` | `getReply()` picks a response by checking rules in order |
| Functions | `normalize()`, `hasWord()`, `hasPhrase()`, `getReply()`, `send()` |
| Loops | `hasWord()` and `hasPhrase()` loop through words and phrases to find a match |
| Input / Output | A text field and buttons for input, chat bubbles for output |

## Features

- Rule-based replies using `if / else if` logic
- Animated SVG robot with blinking, floating, and eyes that follow the cursor
- Minimalist design with a clean layout and a single accent color
- Fully responsive on phones, tablets, and desktops
- Light and dark mode that follows your system setting
- Quick-reply buttons for the three main phrases
- Keyboard friendly, with visible focus states and reduced-motion support

## Getting Started

No installation is needed.

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   ```
2. Open the project folder.
3. Double-click `chatbot.html` to open it in your browser.

### Host it on GitHub Pages (optional)

1. Rename `chatbot.html` to `index.html`.
2. In your repository, go to **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, choose `main` and `/ (root)`, then click **Save**.
4. After a minute, your chatbot will be live at `https://<your-username>.github.io/<your-repo-name>/`.

## Project Structure

```
.
├── chatbot.html        # Markup, styles, chatbot logic, and robot animation
├── assets/
│   ├── banner.png
│   ├── chat.png
│   ├── chat-dark.png
│   ├── states.png
│   └── code.png
└── README.md
```

## Customize

**Add a new rule:** add another `else if` block inside `getReply()` before the final `else`.

```js
} else if (hasWord(words, ["weather"])) {
  return { text: "I can’t check the weather, but I hope it’s sunny!", bye: false };
}
```

**Change the colors:** edit the CSS variables at the top of the `<style>` block (`--accent`, `--bg`, `--ink`, and so on).

**Rename the bot:** change the text inside the `.name` element and the reply in the "your name" rule.

## Future Improvements

- [ ] Add more intents and synonyms
- [ ] Add voice input and spoken replies
- [ ] Add a theme toggle
- [ ] Remember the conversation between visits

## License

This project is open source and available under the [MIT License](LICENSE).
