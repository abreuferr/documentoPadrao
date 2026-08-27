# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Visão geral

Repositório de um modelo (template) de documento LaTeX em português, baseado na classe `report`. Não é uma aplicação de software: é um único arquivo `.tex` que serve de ponto de partida para relatórios/documentos técnicos, com capa, marca d'água, sumário, blocos de código estilizados e um rodapé de "copyleft" com metadados de versão/autor.

## Comandos

Compilar o PDF (resolve sumário/referências automaticamente, rodando pdflatex quantas vezes for preciso):

    latexmk -pdf documentoPadrao.tex

Limpar artefatos de compilação (.aux, .log, .toc, .out, etc.):

    latexmk -c

Compilação manual equivalente, sem latexmk (a segunda passada é necessária para atualizar o sumário):

    pdflatex documentoPadrao.tex
    pdflatex documentoPadrao.tex

Pacotes TeX Live usados além do básico: `background`, `tcolorbox` (opção `most`), `fvextra`, `microtype`, `booktabs`, `enumitem`, `lipsum`.

## Arquitetura

- `documentoPadrao.tex` é um arquivo único com preâmbulo (pacotes/configuração) e conteúdo (capítulos) misturados — não há separação entre "template" e "conteúdo de exemplo". `\lipsum`, "Título do Documento", "Nome do Autor", o comando OpenSSL e a figura do OpenBSD são conteúdo de exemplo a ser substituído a cada novo documento derivado deste modelo.
- Marca d'água: pacote `background` aplica `img/logo.png` centralizado em todas as páginas via `\backgroundsetup`.
- Blocos de comando: `tcolorbox` + `fvextra` (ambiente `Verbatim` redefinido com `breaklines=true, breakanywhere=true`) para exibir saídas de shell com quebra de linha automática.
- Metadados do PDF em `\hypersetup` (pdftitle/pdfauthor) são independentes de `\title`/`\author` e não estão sincronizados — ao mudar título/autor do documento, atualizar os dois lugares.
- O `\chapter*{}` final (antes de `\end{document}`) guarda metadados de versionamento do próprio documento (propósito, versão, autor), distintos do versionamento do repositório via git.
- `img/` contém só as imagens referenciadas no `.tex`; novas imagens de conteúdo entram aqui.
