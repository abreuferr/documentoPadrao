# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

Ver README.md para visão geral, comando de compilação principal e pacotes TeX Live requeridos.

## Comandos

Além do `latexmk main.tex` do README: limpar artefatos de compilação com `latexmk -c` (age em `build/`). Compilação manual sem latexmk exige duas passadas (a segunda atualiza o sumário):

    pdflatex -output-directory=build main.tex
    pdflatex -output-directory=build main.tex

## Arquitetura

- Não é uma aplicação de software. O preâmbulo fica em `config/preambulo.tex` e cada capítulo em `capitulos/`, incluídos por `main.tex` via `\input`. Os capítulos são conteúdo de exemplo: `\lipsum`, "Título do Documento", "Nome do Autor", o comando OpenSSL e a figura do OpenBSD são conteúdo de exemplo a ser substituído a cada novo documento derivado deste modelo.
- Marca d'água: pacote `background` aplica `img/logo.png` centralizado em todas as páginas via `\backgroundsetup`.
- Blocos de comando: `tcolorbox` + `fvextra` (ambiente `Verbatim` redefinido com `breaklines=true, breakanywhere=true`) para exibir saídas de shell com quebra de linha automática.
- Metadados do PDF em `\hypersetup` (pdftitle/pdfauthor) são independentes de `\title`/`\author` e não estão sincronizados — ao mudar título/autor do documento, atualizar os dois lugares.
- O `\chapter*{}` de `capitulos/99-colofao.tex` (último, antes de `\end{document}`) guarda metadados de versionamento do próprio documento (propósito, versão, autor), distintos do versionamento do repositório via git.
- `img/` contém só as imagens referenciadas no `.tex`; novas imagens de conteúdo entram aqui.
