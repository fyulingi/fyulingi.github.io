## VS Code + LaTex Workshop

This article trys to help you compile LaTex document with [Visual Studio Code](https://code.visualstudio.com/).

* 1 Download the **LaTex Workshop** extension 
![image of LaTex Workshop](/1.jpg)

* 2 edit the **latex-workshop.latex.recipes**
  * clike "File-Preferences-settings", search "latex-workshop.latex.recipes" 
  ![image of recipes](/2.jpg)
  * clike "**Edit in settings.json**"
  * copy the following codes to your **settings.json**
  
```
{
    "editor.wordWrap": "on",
    "workbench.startupEditor": "newUntitledFile",
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk",
        "*.gz"
    ],
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

Now, you can enjoy your time to coding LaTex documents in your VS code environment.

## Some Useful Shortcut

* `ctrl`+`alt`+`b` to compile LaTex document
* `ctrl`+`alt`+`v` to preview your document
* `ctrl`+`clike` to reverse synctex
