## VS Code + LaTeX Workshop

This text trys to help you compile LaTeX documents with [Visual Studio Code](https://code.visualstudio.com/).

* 1 Download the **LaTeX Workshop** extension 
![image of LaTeX Workshop](/1.jpg)

* 2 Edit the **latex-workshop.latex.recipes**
  * Clike "File"-"Preferences"-"settings", search "latex-workshop.latex.recipes" 
  ![image of recipes](/2.jpg)
  * Clike "**Edit in settings.json**"
  * Copy the following codes to your **settings.json**
  
```
{
    "editor.wordWrap": "on",
    "workbench.startupEditor": "newUntitledFile",
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.latex.recipes": [
 {
            "name": "xelatex",
            "tools": [
              "xelatex",
              "xelatex"
            ]
          },
        {
            "name": "xelatexb",
            "tools": [
              "xelatex",
              "bibtex",
              "xelatex",
              "xelatex"
            ]
          },
        {
          "name": "latexmk",
          "tools": [
            "latexmk"
          ]
        },
        {
          "name": "pdflatex -> bibtex -> pdflatex*2",
          "tools": [
            "pdflatex",
            "bibtex",
            "pdflatex",
            "pdflatex"
          ]
        }
      ],
      "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
          "name": "latexmk",
          "command": "latexmk",
          "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "-pdf",
            "%DOC%"
          ]
        },
        {
          "name": "pdflatex",
          "command": "pdflatex",
          "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
          ]
        },
        {
          "name": "bibtex",
          "command": "bibtex",
          "args": [
            "%DOCFILE%"
          ]
        }
      ]
}
```

Now, you can enjoy your time writing LaTeX documents in your VS Code environment.

## Some Useful Shortcut

* `ctrl`+`alt`+`b` to compile LaTeX document
* `ctrl`+`alt`+`v` to preview your document
* `ctrl`+`clike` to reverse synctex[^1]

[^1]To use this function right, you need to disable "Auto Clean", or add `"latex-workshop.latex.autoBuild.cleanAndRetry.enabled": false,` to your settings.json
