# My Resume

My version-controlled [JSON resume](https://jsonresume.org/) conveniently exported to HTML and PDF formats.

## Dependencies

-   [jsonresume/resume-cli](https://github.com/jsonresume/resume-cli) (do NOT install globally, use the `resume` command with [npx](https://www.npmjs.com/package/npx) instead)
-   [wkhtmltopdf](https://wkhtmltopdf.org/index.html)

## Making Updates

These are mostly for my future self as I'll almost definitely forget all of the magic commands I used to get here.

```bash
# install dependencies ...
sudo apt-get install xvfb # only for Ubuntu (WSL)
sudo apt-get install xfonts-100dpi xfonts-75dpi xfonts-scalable xfonts-cyrillic # only for Ubuntu (WSL)
sudo apt-get install wkhtmltopdf

npm install resume-cli
npm install --save-dev jsonresume-theme-stackoverflow


# export resume.json (full) html (using temp.html so that we don't accidentally override manual changes to resume.html)
npx resume export --theme=stackoverflow temp.html
npx resume export --resume=short.resume.json --theme=stackoverflow short-temp.html

# export short.resume.json as pdf (since I'll usually want it on a single page if it's a pdf)
xvfb-run wkhtmltopdf ./short-resume.html short-resume.pdf # Ubuntu (WSL)
wkhtmltopdf --enable-local-file-access ./short-resume.html short-resume.pdf # MacOS

```
