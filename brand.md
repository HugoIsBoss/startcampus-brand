# Start Campus — Brand Reference

Fonte única de verdade para a marca Start Campus em documentos, apresentações e materiais. Atualizar aqui reflete em todos os skills que consomem este ficheiro.

## Cores

| Papel | Hex |
|-------|-----|
| Verde escuro (fundo) | #0A3638 |
| Verde primário (destaques) | #00C159 |
| Verde conector (linhas) | #12BD64 |
| Quase-preto (corpo de texto) | #272726 |
| Branco | #FFFFFF |
| Cinza claro (fundos de painel) | #EDEBEB |
| Lavanda subtil (painéis leves) | #F4F4FF |
| Cinza rodapé (confidencialidade) | #7F7F7F |

Paleta intencionalmente estreita: verde escuro + verde vivo + quase-preto + branco. Nunca usar azuis, laranjas ou roxos genéricos.

## Tipografia

- Fonte principal: **Figtree** (sempre especificada explicitamente)
- Fallback: **Inter** (nunca Arial ou Calibri)

| Elemento | Peso | Tamanho (pt) |
|----------|------|--------------|
| Título de documento | Bold | 24-32 |
| Cabeçalho de secção (H1) | Bold | 18-22 |
| Subcabeçalho (H2) | Bold | 14-16 |
| Corpo de texto | Regular | 10-12 |
| Rodapé / nota de confidencialidade | Regular | 8-9 |

## Convenção de títulos

Palavras-chave, números e afirmações de marca a verde (#00C159); palavras de ligação a quase-preto (#272726).

## Rodapé padrão

Logo Start Campus à esquerda, separador vertical, "Strictly private and confidential" em cinza (#7F7F7F), número de página à direita.

## Disclaimer legal (padrão)

This document and any files transmitted with it are the property of Start Campus. All rights, including without limitation copyright, are reserved. This document contains information that may be confidential and may also be privileged. It is for the exclusive use of the intended recipient(s) and for the purpose indicated in it. This document and any files transmitted with it do not constitute any form of commitment by Start Campus, they are solely for your information and should not be relied upon for any effects. No liability whatsoever (including negligence or otherwise) is accepted by Start Campus or any of its affiliates, directors, officers, employees, representatives or advisers in relation to any information or opinion contained herein.

Start Campus is registered in Portugal, with number 515949841. Main office address is: START – Sines TransAtlantic Renewable & Technology Campus, S.A., Av. Eng. Duarte Pacheco, Tower 1, Floor 13, 1070-100 Lisboa, Portugal

## Tom e língua

- Documentos externos em inglês (British English) salvo indicação em contrário
- Documentos internos PT em português de Portugal (PT-PT)
- Confiante e direto; números em destaque (1.2GW, PUE 1.10)
- Termos técnicos corretos (PUE, WUE, HVO, MMR, MSA, GPU, HPC, AI)

## Imagens

Imagens de conteúdo no repo (vistas do campus e renders). Preferir .jpg para
fotografias em documentos Word (mais leve). Manter esta tabela quando se
adicionam imagens cujo nome não é auto-explicativo.

| Ficheiro | Descrição |
|----------|-----------|
| `ALL Campus.png` | Vista geral de todo o campus SINES |
| `ALL Campus with MW.png` | Vista geral do campus com anotação de potência (MW) |
| `ALL Campus_Render.jpg` | Render artístico da vista geral do campus |
| `SIN02_Render (1).jpg` | Render do edifício SIN02 - vista 1 (preferir esta) |
| `SIN02_Render (2).png` | Render do edifício SIN02 - vista 2 |
| `SIN02_Render (3).png` | Render do edifício SIN02 - vista 3 |
| `Start_Campus (5).jpg` | Aérea do data hall com paisagem verde - conteúdo + imagem à direita |
| `Start_Campus (6).jpg` | Vista ao nível do solo pela fachada do data hall, oceano no horizonte - full-width |
| `Start_Campus (7).jpg` | Perspetiva próxima do revestimento metálico exterior - detalhe de arquitetura |
| `Start_Campus (8).jpg` | Aérea de SIN01 com o porto de Sines e oceano atrás - overview / localização |
| `Start_Campus (9).jpg` | Aérea ampla de todo o campus junto ao mar - hero "the campus" |
| `Start_Campus (10).jpg` | Aérea do campus na paisagem de Sines - contexto de localização |
| `Start_Campus (11).jpg` | Pôr do sol na costa com o campus em primeiro plano - slide de fecho / "Thank You" |
| `Start_Campus (12).jpg` | Aérea da costa de Sines, estuário e campus - geografia, sustentabilidade, arrefecimento por água do mar |
| `Start_Campus (13).jpg` | Interior técnico com equipamento de arrefecimento (unidades azuis) - capacidade técnica |
| `Start_Campus (14).jpg` | Passadiço coberto / corredor envidraçado com jardim - arquitetura, two-panel split |
| `Start_Campus (15).jpg` | Corredor interior branco, perspetiva minimalista - divisor de secção |
| `Start_Campus (16).jpg` | Interior de data hall vazio / cais de carga - "ready to deploy", build-out |
| `Start_Campus (17).jpg` | Poste de sinalética exterior com edifício atrás - slide de detalhe / textura |
| `Start_Campus (18).jpg` | Foto de grupo da equipa Start Campus - pessoas / cultura, "about us" |
| `Start_Campus (19).jpg` | Logo Start Campus retroiluminado em parede verde escura - cover / brand / fecho |

## Contexto por skill

Este ficheiro serve os vários skills Start Campus. Cada skill descarrega
os seus assets via `fetch_brand.sh` com um contexto explícito.

| Contexto (`--for`) | Skill | Assets esperados no repo |
|--------------------|-------|--------------------------|
| `pptx` | `startcampus-pptx` | Decks de referência `.pptx` + logos + imagens de conteúdo |
| `docx` | `startcampus-docx` | Template `SC_Word_Design_Normal_Template_V4.dotx` + logos + imagens |

Decks de referência PPTX no repo:
- `PPT_StartCampus_Presentation_30102024_PUBLIC.pptx` (master público, o mais completo)
- `2025 09 04_Introduction to Start Campus and SIN02-06.pptx` (intro / pipeline SIN02-06)
- `SINES DC ONE PAGER PDF.pptx` (one-pager / fact-sheet)

As cores, tipografia, convenção de títulos, rodapé, disclaimer e tom acima
aplicam-se a **ambos** os contextos. Os logos são partilhados. As imagens de
conteúdo (secção `## Imagens`) servem tanto documentos como apresentações — em
Word preferir `.jpg`; em PPTX as URLs raw podem ir diretamente ao `addImage`.
