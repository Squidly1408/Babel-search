# Babel Search 🔍

**Babel Search** is a word-hunting game set in the infinite [Library of Babel](https://libraryofbabel.info/).
Every page is random letters. Somewhere in there is a real English word. Find it before the clock runs away from you.

▶️ **Play it:** [babel-search.github.io](https://babel-search.github.io/)

## How to play

1. Press **Start Game** to open a random page from the Library of Babel.
2. Highlight any real English word that is 3–20 letters long.
3. Press **Check Word**.
   - Correct: the timer stops and your time is recorded.
   - Wrong: you get a 60 s penalty and a new page.
4. Stuck? **Next Page** skips to a new page, also with a 60 s penalty.
5. Long words pay off: you get **−5 s for every letter after the 4th**.

Lowest time wins.

### Keyboard shortcuts

| Key   | Action                |
| ----- | --------------------- |
| `C`   | Check selected word   |
| `N`   | Next page (+60 s)     |
| `Esc` | Close a pop-up        |

## Features

- Random pages pulled live from the Library of Babel
- Word checking against a ~370k word English dictionary
- Time penalties and length bonuses
- Personal top-20 leaderboard
- 50 achievements, from *First Word!* to *Master of Babel*
- Works on desktop and mobile, and can be installed as an app (PWA manifest)
- No build step, no dependencies: one HTML file

Scores, stats and achievements are stored in your browser's `localStorage`, so they stay on your device.

## Running locally

Any static file server works:

```sh
git clone https://github.com/Squidly1408/Babel-search.git
cd Babel-search
python -m http.server 8000
```

Then open <http://localhost:8000>.

You need an internet connection. Pages and the dictionary are fetched at runtime.

## How it works

| Piece      | Source |
| ---------- | ------ |
| Pages      | `libraryofbabel.info/random.cgi`, fetched through the [allorigins](https://allorigins.win/) CORS proxy |
| Dictionary | [`dwyl/english-words`](https://github.com/dwyl/english-words) (`words_alpha.txt`) |

Everything else (game logic, timer, leaderboard, achievements) is plain JavaScript in [`index.html`](index.html).

## Project structure

```
index.html      the whole game: markup, styles and script
404.html        "lost in the library" page
manifest.json   PWA manifest
favicon.png     icon
```

## Contributing

Issues and pull requests are welcome. Keep it dependency-free, and test in a browser on both desktop and mobile before opening a PR.

## License

[MIT](LICENSE) © Squidly1408

---

Made with ❤️ by [Squidly1408](https://github.com/Squidly1408).
