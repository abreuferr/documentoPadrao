# Modelo

Modelo (template) de documento LaTeX em português, baseado na classe `report`: capa, marca d'água, sumário, blocos de comando estilizados e rodapé com metadados de versão/autor.

## Compilar

```
latexmk -pdf documentoPadrao.tex
```

Requer os pacotes TeX Live: `background`, `tcolorbox` (opção `most`), `fvextra`, `microtype`, `booktabs`, `enumitem`, `lipsum`.

## Estrutura

- `documentoPadrao.tex` — arquivo principal do modelo (preâmbulo + conteúdo de exemplo, a ser substituído a cada novo documento).
- `img/` — imagens usadas no documento (logo para marca d'água, figuras de exemplo).

# Agenda

- Curso de Latex
    - https://www.youtube.com/watch?v=xQ3yYqLlHcQ&list=PLa_2246N48_p9ndUHlO255uvKtSR8mshE
    - https://www.youtube.com/watch?v=NN-UyU5qSvE&list=PLJH9xsc0pltklnechNXNZ9EPFRb7IKG2G
    - https://www.youtube.com/watch?v=zR-QuNf3agQ&list=PLb735fZHArLaD_RFIiNQx7_WHSnhdy60e
    - https://www.youtube.com/watch?v=zR-QuNf3agQ&list=PLb735fZHArLamJiCIXsQT6BiHM1IgYQ43
