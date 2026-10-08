# Modelo

Modelo (template) de documento LaTeX em português, baseado na classe `report`: capa, marca d'água, sumário, blocos de comando estilizados e rodapé com metadados de versão/autor.

## Compilar

```
latexmk main.tex
```

O PDF sai em `build/main.pdf` (configurado em `latexmkrc`).

Requer os pacotes TeX Live: `background`, `tcolorbox` (opção `most`), `fvextra`, `microtype`, `booktabs`, `enumitem`, `lipsum`.

## Estrutura

- `main.tex` — documento raiz: capa, sumário e `\input` do preâmbulo e dos capítulos.
- `config/preambulo.tex` — pacotes, hyperlinks, marca d'água e estilos.
- `capitulos/` — um `.tex` por capítulo (conteúdo de exemplo, a ser substituído a cada novo documento).
- `img/` — imagens usadas no documento (logo para marca d'água, figuras de exemplo).
- `build/` — saída da compilação (fora do git).

# Agenda

- Curso de Latex
    - https://www.youtube.com/watch?v=xQ3yYqLlHcQ&list=PLa_2246N48_p9ndUHlO255uvKtSR8mshE
    - https://www.youtube.com/watch?v=NN-UyU5qSvE&list=PLJH9xsc0pltklnechNXNZ9EPFRb7IKG2G
    - https://www.youtube.com/watch?v=zR-QuNf3agQ&list=PLb735fZHArLaD_RFIiNQx7_WHSnhdy60e
    - https://www.youtube.com/watch?v=zR-QuNf3agQ&list=PLb735fZHArLamJiCIXsQT6BiHM1IgYQ43
