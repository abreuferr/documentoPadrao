# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

Ver README.md para visão geral, comando de compilação principal e pacotes TeX Live requeridos.

## Comandos

Além do `latexmk -pdf documentoPadrao.tex` do README: limpar artefatos de compilação com `latexmk -c` (.aux, .log, .toc, .out etc.). Compilação manual sem latexmk exige duas passadas (a segunda atualiza o sumário):

    pdflatex documentoPadrao.tex
    pdflatex documentoPadrao.tex

## Arquitetura

- `documentoPadrao.tex` não é uma aplicação de software: é um arquivo único com preâmbulo (pacotes/configuração) e conteúdo (capítulos) misturados — não há separação entre "template" e "conteúdo de exemplo". `\lipsum`, "Título do Documento", "Nome do Autor", o comando OpenSSL e a figura do OpenBSD são conteúdo de exemplo a ser substituído a cada novo documento derivado deste modelo.
- Marca d'água: pacote `background` aplica `img/logo.png` centralizado em todas as páginas via `\backgroundsetup`.
- Blocos de comando: `tcolorbox` + `fvextra` (ambiente `Verbatim` redefinido com `breaklines=true, breakanywhere=true`) para exibir saídas de shell com quebra de linha automática.
- Metadados do PDF em `\hypersetup` (pdftitle/pdfauthor) são independentes de `\title`/`\author` e não estão sincronizados — ao mudar título/autor do documento, atualizar os dois lugares.
- O `\chapter*{}` final (antes de `\end{document}`) guarda metadados de versionamento do próprio documento (propósito, versão, autor), distintos do versionamento do repositório via git.
- `img/` contém só as imagens referenciadas no `.tex`; novas imagens de conteúdo entram aqui.
