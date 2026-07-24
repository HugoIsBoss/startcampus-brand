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

## Logos

Variantes disponíveis no repo. Escolher pelo fundo:
- **Cores** (`Full_Color`) sobre fundos claros OU sobre fotografias com área clara.
  Preferir a versão a cores na **capa**, mesmo sobre imagem, quando há contraste.
- **White** sobre fundos escuros (verde escuro, foto escura).
- **Black** para monocromático/impressão.
- **Inverse** (`Full_Color_Inverse`) para casos especiais de fundo escuro em que se
  quer manter o verde da marca com o texto a branco.

| Ficheiro | Tipo | Rácio (w:h) | h/w (mult. de altura) |
|----------|------|-------------|------------------------|
| `StartCampus_Horizontal_RGB_Full_Color.png` | Horizontal cor | 6.578:1 | 0.152 |
| `StartCampus_Horizontal_RGB_White.png` | Horizontal branco | 6.578:1 | 0.152 |
| `StartCampus_Horizontal_RGB_Black.png` | Horizontal preto | 6.575:1 | 0.152 |
| `StartCampus_Horizontal_RGB_Full_Color_Inverse.png` | Horizontal cor/inverso | 6.578:1 | 0.152 |
| `StartCampus_Vertical_RGB_Full_Color.png` | Vertical cor | 3.010:1 | 0.332 |
| `StartCampus_Vertical_RGB_White.png` | Vertical branco | 3.010:1 | 0.332 |
| `StartCampus_Vertical_RGB_Black.png` | Vertical preto | 3.010:1 | 0.332 |
| `StartCampus_Vertical_RGB_Full_Color_Inverse.png` | Vertical cor/inverso | 3.010:1 | 0.332 |
| `StartCampus_Favicon_RGB_Full_Color.png` | Marca/favicon cor | 0.96:1 | 1.042 |
| `StartCampus_Favicon_RGB_White.png` | Marca/favicon branco | 0.96:1 | 1.042 |
| `StartCampus_Favicon_RGB_Black.png` | Marca/favicon preto | 0.96:1 | 1.042 |

**Regra anti-distorção (crítica):** ao colocar um logo, deriva SEMPRE a altura a
partir da largura pelo multiplicador acima — nunca fixes uma altura "à mão".
Fórmula: `altura = largura x (h/w)`. Ex.: logo horizontal com 2.6" de largura →
`h = 2.6 x 0.152 = 0.395"`. Em pptxgenjs, uma função helper evita erros:
`const logoH = w => +(w * 0.152).toFixed(3);` e depois `h: logoH(2.6)`.

Recomendação de capa: usar `StartCampus_Horizontal_RGB_Full_Color.png` (versão a
cores) quando o canto onde assenta o logo tem fundo suficientemente claro; caso o
fundo seja escuro, `..._White.png`.

## Rácios e dimensionamento de imagens (evitar esticar)

Rácios nativos das imagens de conteúdo:
- **Fotografias `Start_Campus (N).jpg` e `SC(N).jpg`**: 3:2 landscape (**1.500:1**). NÃO são 4:3.
- **Renders / vistas gerais** (`ALL Campus*`, `ALL Campus_Render`, `SIN02_Render (1/2)`): widescreen **1.78–1.91:1**.
- **`SIN02_Render (3).png`**: **1.5:1** (exceção entre os renders SIN02).
- **Frames de vídeo `START CAMPUS 27-08 v2 4K_*`**: **16:9 (1.778:1)**, 2000×1125.

`sizing: { type: 'cover' }` preserva o rácio no PowerPoint. **MAS** o LibreOffice
(usado no QA) por vezes ignora o cover e estica a imagem quando o rácio do slot é
muito diferente do da imagem — típico ao pôr uma foto 3:2 num slot em retrato
(ex.: painel lateral full-height 6.0"×7.5" = 0.8:1). O resultado parece "ratio
errado" mesmo com o código aparentemente correto.

**Regra robusta:** quando o slot e a imagem têm rácios muito diferentes (sobretudo
slots em retrato com fotos landscape), pré-recorta a imagem ao rácio exato do slot
antes de a colocar, e passa-a **sem** `sizing`:

```python
from PIL import Image
im = Image.open("foto.jpg"); w, h = im.size
target = slot_w / slot_h            # ex.: 6.0/7.5 = 0.8
cur = w / h
if cur > target:                    # imagem mais larga -> cortar laterais
    nw = int(h * target); x0 = (w - nw) // 2
    im = im.crop((x0, 0, x0 + nw, h))
else:                               # mais alta -> cortar topo/fundo
    nh = int(w / target); y0 = (h - nh) // 2
    im = im.crop((0, y0, w, y0 + nh))
im.save("foto_crop.jpg", quality=90)
```

Depois: `slide.addImage({ path: 'foto_crop.jpg', x, y, w: slot_w, h: slot_h })`
(sem `sizing`, porque o rácio já coincide). Para slots com rácio próximo do da
imagem (ex.: full-bleed 13.33×7.5 = 1.777 com um render 1.78), `sizing: cover`
continua a chegar.

## Imagens

Imagens de conteúdo no repo. Descrições verificadas visualmente. Biblioteca
**partilhada** por todas as skills Start Campus (`startcampus-pptx`,
`startcampus-docx`, `startcampus-canva`). Preferir .jpg para fotografias em
documentos Word (mais leve). Em PPTX as URLs raw podem ir diretamente ao
`addImage`. No Canva servem de foto para os cards (sharing images) e podem ser
carregadas como asset via o connector. Manter esta tabela quando se adicionam
imagens cujo nome não é auto-explicativo. Todas as `Start_Campus (N)` e `SC(N)`
são 1.5:1 salvo indicação.

### Vistas gerais e renders (widescreen)

| Ficheiro | Rácio | Descrição |
|----------|-------|-----------|
| `ALL Campus.png` | 1.91:1 | Aérea de todo o campus SINES na paisagem, edifícios brancos |
| `ALL Campus with MW.png` | 1.78:1 | Aérea do campus anotada: SIN01 LIVE + SIN02–06 com potência (MW), seawater cooling, subestação VHV. Ótima para diagramas de capacidade/pipeline |
| `ALL Campus_Render.jpg` | 1.875:1 | Render artístico da vista geral do campus completo |
| `SIN02_Render (1).jpg` / `.png` | 1.875:1 | Render SIN02 ao nível do solo, verde e passeio (preferir a `.jpg`) |
| `SIN02_Render (2).png` | 1.875:1 | Render SIN02, vista de conjunto com árvores |
| `SIN02_Render (3).png` | 1.5:1 | Render SIN02 aéreo com o mar ao fundo |

### Aéreas do edifício / localização (SC — 1.5:1)

| Ficheiro | Descrição |
|----------|-----------|
| `SC(0).jpg` | Aérea de SIN01 com o porto de Sines e o mar ao fundo - overview / localização |
| `SC(1).jpg` | Aérea rasante da cobertura/fachada longitudinal, mar ao fundo |
| `SC(2).jpg` | Aérea da fachada e pátio, mar ao horizonte |
| `SC(3).jpg` | Aérea lateral do edifício junto à estrada de acesso, mar ao fundo |
| `SC(4).jpg` | Aérea ampla do edifício na paisagem de Sines |

### Fachadas, pátios e exteriores (Start_Campus — 1.5:1)

| Ficheiro | Descrição |
|----------|-----------|
| `Start_Campus (5).jpg` | Fachada frontal envidraçada ao nível do pátio, céu azul - hero exterior |
| `Start_Campus (6).jpg` | Fachada frontal com entrada, pátio pavimentado - full-width |
| `Start_Campus (7).jpg` | Fachada frontal em perspetiva, nuvens - variação de (6) |
| `Start_Campus (8).jpg` | Aérea do data hall SIN01 na paisagem - overview |
| `Start_Campus (9).jpg` | Aérea ampla do data hall e estrada de acesso na paisagem de Sines |
| `Start_Campus (10).jpg` | Fachada frontal com passadeira e entrada - exterior ao nível do solo |
| `Start_Campus (11).jpg` | Fachada frontal com pátio amplo, vista frontal simétrica |
| `Start_Campus (12).jpg` | Fachada envidraçada em perspetiva longitudinal, pátio |
| `Start_Campus (13).jpg` | Fachada em perspetiva com árvores jovens no pátio |
| `Start_Campus (14).jpg` | Fachada longitudinal ao nível do solo, grande angular do pátio |
| `Start_Campus (15).jpg` | Pátio amplo com postes e edifício ao fundo |
| `Start_Campus (16).jpg` | Fachada em contrapicado com canteiro de gravilha - detalhe/textura |
| `Start_Campus (17).jpg` | Fachada envidraçada em perspetiva fechada - detalhe de arquitetura |
| `Start_Campus (18).jpg` | Canto do edifício em contrapicado com pilar branco - arquitetura |
| `Start_Campus (19).jpg` | Entrada envidraçada em perspetiva, revestimento metálico |
| `Start_Campus (20).jpg` | Empena/topo do edifício com portas técnicas, pavimento |
| `Start_Campus (21).jpg` | Empena do edifício, variação de (20) |
| `Start_Campus (22).jpg` | Fachada longitudinal panorâmica, pátio largo |
| `Start_Campus (23).jpg` | Fachada com pessoas ao fundo, escala humana - pátio |
| `Start_Campus (24).jpg` | Fachada envidraçada em perspetiva ao nível do solo |
| `Start_Campus (25).jpg` | Pátio com poste de sinalética e edifício ao fundo |
| `Start_Campus (26).jpg` | **Interior**: sala de madeira clara com iluminação circular e logo Start Campus na parede - "about us" / cultura |
| `Start_Campus (27).jpg` | **Interior**: mesma sala, ângulo alternativo com logo na parede |
| `Start_Campus (28).jpg` | **Interior**: corredor branco minimalista em perspetiva - divisor de secção |

### Frames de vídeo 4K (`START CAMPUS 27-08 v2 4K_*.jpg`, 16:9)

~70 stills extraídos do vídeo institucional (2000×1125, 1.778:1). Cobrem material
que as fotos não têm: **interiores técnicos** (equipamento elétrico/MV, corredores
de racks), **o porto e a vila de Sines vistos de cima**, e **a costa/ondas**
(útil para o tema de arrefecimento por água do mar). Os nomes são timestamps
(`_01_00_01_180`, etc.), não descritivos - selecionar por inspeção visual. Ideais
para slides técnicos, de localização e de sustentabilidade/mar. Descobrir a lista
atual via `discover_images.py` ou pela API do repo.

### Ícones temáticos (PNG numerados)

`01_Sustainability`, `02_Location`, `03_Energy`, `04_Water`, `05_SolarPanel`,
`06_WindTurbine`, `07_Cooling`, `08_Adaptability`, `08_Waves`, `10_Realiability`
[sic], `11_Support`, `12_Security`, `13_Connectivity`, `14_DataCenter`,
`15_Commnunity` [sic]. Usar como iconografia de secção. Nota: há dois `08_` e o
`09` está em falta na numeração; os nomes `Realiability`/`Commnunity` contêm gralhas
no ficheiro de origem - referenciar pelo nome exato do ficheiro.

## Sharing images (cards sociais)

Cards de partilha reais no repo (raiz), servidos por `raw.githubusercontent.com`.
São imagens achatadas (referência de estilo) - a fonte editável é o Canva
(brand templates). **Standard: sempre 1200×630 px** (OG/LinkedIn/Facebook). Os
ratios indicados abaixo são os dos ficheiros originais; ao criar templates novos,
usar 1200×630. Usados pela skill `startcampus-canva`.

### Layout A - Blog post card com foto (dominante)
Painel esquerdo (branco ou lavanda `#F4F4FF`) + corte diagonal + foto à direita.
Logo, label "BLOG POST", título com palavras-chave a verde, autor opcional
("by Nome" verde / cargo preto), botão verde ("Read"/"Read now"/"Read More").

| Ficheiro | Ratio orig. | Notas |
|----------|-------------|-------|
| `ROB_BLog.png` | 1.91 | Painel branco, título itálico, "by Rob Dunn / CEO", botão "Read" |
| `BLOG_StartCampus_Sustainability_Planet.png` | 1.71 | Painel lavanda, botão "Read now" |
| `BLOG_FBA_PTC.png` | 1.91 | Lavanda, autor "Fernando B. Azevedo / Head of Connectivity" |
| `NIS2_BLOG.png` | 1.91 | Lavanda, autor "Fernando Fainzilber / Head of Security" |
| `BLOG_OmerW.png` | 1.71 | Lavanda, autor "Omer Wilson / CMO" |
| `Environmental_Awareness_Program.jpg` | 1.71 | Lavanda, sem label "BLOG POST", botão "Read More" |

Campos autofill: `panel_color`, `label`, `title`, `author_name`, `author_role`,
`photo` (imagem), `button_text`.

### Layout B - Award / highlight
Como A mas sem label e sem botão; título domina o painel (preto + verde).

| Ficheiro | Ratio orig. | Notas |
|----------|-------------|-------|
| `DCD_Award.png` | 2.00 | Lavanda, "SIN01 Wins European Data Center Project of the Year 2025" |

Campos autofill: `title`, `photo` (imagem).

### Layout C - Press release (sem foto)
Painel lavanda inteiro. Localização + data a verde, título a preto, botão
"Press Release" em baixo à esquerda.

| Ficheiro | Ratio orig. | Notas |
|----------|-------------|-------|
| `PR_Case_oct.jpg` | 1.71 | "Lisbon, Portugal – October 14, 2024" + título + botão "Press Release" |

Campos autofill: `location_date`, `title`, `button_text`.

### Layout D - Study / download (com thumbnail de documento)
Título grande verde+preto à esquerda, parágrafo, botão "Download now",
infográfico/documento à direita.

| Ficheiro | Ratio orig. | Notas |
|----------|-------------|-------|
| `Copenhagen_Economics.png` | 1.71 | "Unlocking Portugal's Digital Potential: The €26 Billion Opportunity" |

Campos autofill: `title`, `body`, `button_text`, `document_image` (imagem).

### Layout E - Announcement com logos de parceiros (fundo escuro)
Fundo `#0A3638`/preto, logo SC branco, título verde+branco, ícones decorativos
verdes, logos de parceiros no rodapé. Logos de parceiros NÃO estão no repo -
fornecidos pelo utilizador.

| Ficheiro | Ratio orig. | Notas |
|----------|-------------|-------|
| `Share_Nvidia2.png` | 1.91 | "Nscale to Deliver 66,000+ NVIDIA Rubin GPUs to Microsoft…" + NSCALE/NVIDIA/Microsoft |

Campos autofill: `title`, `partner_logos` (até 3 imagens, fornecidas pelo utilizador).

### Layout F - Co-branding split / community
Split 50/50 vertical com dois logos (sem texto), ou card lavanda com ícones
decorativos, título verde e parágrafo centrado.

| Ficheiro | Ratio orig. | Notas |
|----------|-------------|-------|
| `Feature-Image-EDP.jpg` | 1.91 | Split 50/50: logo SC (lavanda) \| logo parceiro (verde-escuro), sem texto |
| `Gamma.png` | 1.71 | Lavanda, ícones, "GAMMA COMMUNITY" + título verde + parágrafo + botão "Know more" |

Campos autofill (split): `partner_logo` (imagem). (community): `title`, `body`,
`button_text`.

## Pessoas / Equipa

Retratos profissionais para slides "leadership team", bios, organograma, etc.
Todos 4:3 landscape (1.333:1; originais de câmara 4032×3024 ou 2000×1500; versões
web 1000×750). Enquadramento é retrato de meio-corpo em ambiente de escritório —
para um slot quadrado ou vertical de card, aplicar a regra de pré-recorte (secção
Rácios), tipicamente cortando as laterais e mantendo o rosto centrado.

Bios abaixo são texto fornecido pelo Hugo (fonte interna). NÃO inventar dados
biográficos — usar apenas o que está aqui. Bios em inglês (British), tom de marca.

### Resolvido

- **CFO confirmado: Nicolas Le Brouster** (`Nicolas_Le_Brouster.png`) — a foto na
  página executiva manda.
- **Manuel Macedo Santos** (`Manuel.jpg`) — **Strategy & Growth Director** (não CFO).
  A bio fornecida menciona "Chief Financial Officer"; tratar o cargo atual como
  Strategy & Growth Director e a menção a CFO na bio como desatualizada.

### Equipa executiva

| Ficheiro | Nome | Cargo | LinkedIn |
|----------|------|-------|----------|
| `Rob_DUnn.jpg` | Robert Dunn | Chief Executive Officer (CEO) | linkedin.com/in/robertnortondunn |
| `Luis Rodrigues.jpg` | Luís Rodrigues | Chief Operating Officer (COO) | linkedin.com/in/rodrigues-luis |
| `Nicolas_Le_Brouster.png` | Nicolas Le Brouster | Chief Financial Officer (CFO) | linkedin.com/in/nicolas-le-brouster |
| `Caroline.jpg` | Caroline Romanski | Chief Corporate Officer | linkedin.com/in/carolineromanski |
| `Daniela.jpg` | Daniela Silva e Sousa | General Counsel | linkedin.com/in/daniela-silva-e-sousa-51043321 |
| `Warren-1.jpg` | Warren Barrie | Chief Revenue Officer (CRO) | linkedin.com/in/wbarrie |
| `Omer2.jpg` | Omer Wilson | Chief Marketing Officer (CMO) | linkedin.com/in/omerwilson |
| `Carla.jpg` | Carla Vieira Calisto | Chief People Officer | linkedin.com/in/carla-calisto-81b25b1 |

### Liderança alargada (heads / leads)

Nome de ficheiro coincide com o nome próprio → associação fiável. `LuisMarques`,
`bill`, `fabio`, `filipe`, `marcio` existem no repo mas não têm bio nem cargo
confirmado — não atribuir.

| Ficheiro | Nome | Cargo |
|----------|------|-------|
| `ALberto.jpg` | Alberto Petermann | Head of Design and Delivery |
| `Manuel.jpg` | Manuel Macedo Santos | Strategy & Growth Director |
| `denis.jpg` | Denis Browne | R&D Lead |
| (sem foto identificada) | Liviu Iusan | Head of Operations |
| (sem foto identificada) | Jorge Paraíba | Head of Power |
| (sem foto identificada) | Ieuan Spencer | Renewable Power Generation Lead |
| (sem foto identificada) | India Oliveira | Sustainability Lead |
| (sem foto identificada) | Fernando Fainzilber | Head of Security |
| (sem foto identificada) | Fernando Azevedo | Head of Connectivity |

### Bios (texto fornecido — usar tal e qual, não expandir com dados inventados)

**Robert Dunn — CEO**

- *Short:* Robert Dunn is Chief Executive Officer of Start Campus, developer of the industry-leading 1.2 GW SINES DC in Portugal. With over 15 years of experience in the data center industry he and the Lisbon-headquartered team are responsible for Europe's largest and most sustainable AI-ready data ecosystem. Before joining Start Campus, Dunn held key roles at Digital Realty and Laing O'Rourke, leading new-build, conversion, and fit-out data center projects.
- *Extended:* Robert Dunn is the Chief Executive Officer of Start Campus, the developer of the 1.2 GW SINES DC in Portugal. With over 15 years of experience in the data center industry, Dunn joined Start Campus in 2022 as Head of Design and Delivery, where he played a pivotal role in advancing the SINES DC project, set to become Europe's largest and most sustainable AI-ready data ecosystem. Prior to Start Campus, Dunn held a key leadership role at Digital Realty, serving as Senior Construction Director, where he oversaw the development of data center projects across Europe. Dunn's career is marked by a consistent ability to drive transformation, successfully execute complex projects, and champion sustainable growth within the industry, resulting in Start Campus today offering Europe's most advanced AI-ready DC infrastructure.

**Luís Rodrigues — COO**

Luís Rodrigues joined Start Campus in 2021 and holds the role of Chief Operating Officer, with a seat on the Board of Directors. An engineer by training, he built deep data center experience over eight years at Google, holding data center operations and facility management roles across Spain, the Netherlands and Finland, before returning to his home country to join Start Campus, where he first served as Data Center Chief Operations Officer.

**Manuel Macedo Santos — Strategy & Growth Director**

Manuel Macedo Santos is Start Campus' Strategy & Growth Director and brings more than 15 years' experience in investment banking, private equity and management consulting at firms including Alantra, Eaglestone and Oliver Wyman.

**Nicolas Le Brouster — Chief Financial Officer**

Nicolas Le Brouster is Chief Financial Officer at Start Campus, an international finance executive with over 20 years' experience in finance leadership, operations and transactions across real assets and services in Europe, spanning France, Spain and the UK. Before joining Start Campus in 2025, he was Group Chief Financial Officer at Groupe PERIAL, and previously spent more than 15 years at GE Capital in senior finance roles including CFO France and FP&A Director Europe. A recognised business partner to CEOs and leadership teams, he combines strategic planning, business performance management and financial analysis with a strong track record in real estate acquisitions, financing, valuation and investment disposals.

**Caroline Romanski — Chief Corporate Officer**

Caroline Romanski draws on more than a decade at J.P. Morgan — most recently as Executive Director in EMEA Energy Investment Banking in London — in her role as Chief Corporate Officer at Start Campus, which she joined in 2023. She oversees business operations and heads business development for the SINES DC project.

**Daniela Silva e Sousa — General Counsel**

Daniela Silva e Sousa is Start Campus' General Counsel. With over 20 years of legal experience, she began as an M&A lawyer at Uría Menéndez Lisbon and, before recently joining Start Campus, she was Head of Legal Business at Banco Santander Portugal, after 10 years in the banking sector. She was recognised on the Portugal GC Powerlist 2023 by Legal 500.

**Carla Calisto — Chief People Officer**

Carla Calisto is Chief People Officer at Start Campus, which she joined in 2024. She brings more than two decades of senior HR experience, most recently as Chief People Officer and Interim GM at VML MAP, and previously in HR leadership roles at Sonae Sierra, Nike and Staples.

**Denis Browne — R&D Lead**

Denis Browne, R&D Lead at Start Campus, contributes his specialisation in data center infrastructure. Prior to joining Start Campus, he gained vast experience through his previous role as Regional Operations Director of Google Data Centers in addition to 17 years at Intel in various roles within their waferfab and data center facilities.

**Alberto Petermann — Head of Design and Delivery**

Alberto Petermann, Head of Design and Delivery, joined Start Campus in 2022 as Senior Program Manager. With a background in Industrial Engineering, Alberto has, since 2009, worked across the five continents with end users and developers on mission critical projects and throughout the whole life cycle of data centers. Alberto is certified AOS and ATD by Uptime Institute.

**Liviu Iusan — Head of Operations**

Liviu Iusan is the Head of Operations at Start Campus, joining in July of 2023. Having previously worked with Google for nearly a decade, he brings an in-depth understanding of and delivery in operations management, network communications, and systems infrastructure.

**Jorge Paraíba — Head of Power**

Jorge Paraíba has held the position of Head of Power at Start Campus since 2022, where he is responsible for the power strategy, energy management and commercial energy activity to efficiently supply renewable energy to the campus.

**Ieuan Spencer — Renewable Power Generation Lead**

Ieuan Spencer is the Renewable Power Generation Lead at Start Campus, joining in October 2023. An accomplished professional in the field of solar energy, in previous positions, he has worked extensively in the development, construction, and management of assets for international clients.

**India Oliveira — Sustainability Lead**

India Oliveira, as Sustainability Lead, is responsible for implementation of Start Campus' environmental strategy, ensuring that the company's core value of sustainability is at the center of its actions.

**Fernando Fainzilber — Head of Security**

Fernando Fainzilber, Head of Security, has a deep understanding of security in data center newbuilds and launches, having worked internationally for Amazon Web Services, most recently as Cluster Security Manager in Israel.

**Fernando Azevedo — Head of Connectivity**

Fernando Azevedo, Head of Connectivity, joined from Amazon Web Services in Dublin where he worked as Network Development Manager for the AWS global backbone. He previously worked for leading connectivity players, including Angola Cables.

**Warren Barrie — Chief Revenue Officer**

Warren Barrie is Chief Revenue Officer at Start Campus, an entrepreneurial senior executive with a career spanning sales and business development leadership across the data center industry. Before joining Start Campus in 2025, he was Senior Vice President at Kevlinx and Director of Data Centers at Bulk Data Centers, leading international business development for large-scale data center leasing, and earlier held Sales Director roles at Global Switch and Digital Realty. A hands-on strategic business leader, he focuses on building lasting, genuine relationships with clients and partners and on delivering exceptional, sustainable customer outcomes over the long term.

**Omer Wilson — Chief Marketing Officer**

Omer Wilson is Chief Marketing Officer at Start Campus, a marketing leader with extensive international experience across the data center and technology sectors. Before joining Start Campus in 2025, he was Founder and Consultant at Anatolia.Asia Consulting and Chief Marketing Officer at Qarbon Technologies, and has served on advisory boards including Açık Veri ve Teknoloji Derneği and Dokuz Eylül University. He leads Start Campus' marketing and communications for Europe's largest and most sustainable AI-ready data ecosystem.

> Nota sobre nomes de ficheiro: inconsistentes (`Rob_DUnn`, `Warren-1`,
> `Luis Rodrigues` com espaço, `ALberto` com L maiúsculo). Referenciar sempre pelo
> nome exato do ficheiro e percent-encode nas URLs raw.

## Contexto por skill

Este ficheiro serve os vários skills Start Campus. Cada skill descarrega
os seus assets via `fetch_brand.sh` com um contexto explícito.

| Contexto (`--for`) | Skill | Assets esperados no repo |
|--------------------|-------|--------------------------|
| `pptx` | `startcampus-pptx` | Decks de referência `.pptx` + logos + imagens de conteúdo |
| `docx` | `startcampus-docx` | Template `SC_Word_Design_Normal_Template_V4.dotx` + logos + imagens |
| `canva` | `startcampus-canva` | Sharing images de referência (raiz) + logos; templates editáveis vivem no Canva (brand templates) |
| `xlsx` | `startcampus-xlsx` | `brand.md` + logos (sem template nem decks - as folhas constroem-se de raiz) |

Decks de referência PPTX no repo:
- `PPT_StartCampus_Presentation_30102024_PUBLIC.pptx` (master público, o mais completo)
- `2025 09 04_Introduction to Start Campus and SIN02-06.pptx` (intro / pipeline SIN02-06)
- `SINES DC ONE PAGER PDF.pptx` (one-pager / fact-sheet)

As cores, tipografia, convenção de títulos, rodapé, disclaimer e tom acima
aplicam-se a **todos** os contextos. Os logos são partilhados. As imagens de
conteúdo são uma biblioteca partilhada pelas três skills — em Word preferir
`.jpg`; em PPTX as URLs raw podem ir diretamente ao `addImage`; no Canva servem
de foto para os cards e podem ser carregadas como asset via o connector. Os
rácios e a regra anti-distorção (crop-to-cover) aplicam-se a todos.
