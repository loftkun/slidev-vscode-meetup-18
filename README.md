# slidev-vscode-meetup-18

## live demo

SPA on [Netlify](https://loftkun-slidev-vscode-meetup-18.netlify.app/)

## usage

```bash
git clone https://github.com/loftkun/slidev-vscode-meetup-18.git
cd slidev-vscode-meetup-18
npm install
npm run dev -- slides.md
```

Visit `http://localhost:3030/` and confirm the slides showed as SPA.

## publish SPA

```bash
# For GitHub Pages, require setting assets path on server with "--base" param.
npm run build -- --base slidev-vscode-meetup-18/dist/
ls -Fla dist/
```
