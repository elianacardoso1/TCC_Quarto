<h1 align="center">
  <img alt="Quarto ABNT" title="Quarto ABNT" src=".github/logo.png" width="300px" />
</h1>

<p align="center">
  <img alt="License" src="https://img.shields.io/badge/license-MIT-%2304D361">


   <a href="https://www.linkedin.com/in/flaviopangracio/">
    <img alt="Made by Flávio Pangracio" src="https://img.shields.io/badge/made%20by-Flávio Pangrácio-%2304D361">
  </a>

  <a href="https://github.com/flaviohugo14/quarto-abnt/stargazers">
    <img alt="Stargazers" src="https://img.shields.io/github/stars/flaviohugo14/quarto-abnt?style=social">
  </a>
</p>

---

Quarto ABNT é um template para escrita de artigos científicos com as normas da ABNT que utiliza o [Quarto](https://quarto.org/). O objetivo do projeto é fornecer uma estrutura pré-pronta para que qualquer pesquisador gere estudos reprodutíveis e bem formatados, de forma ágil.

## Principais tecnologias 🚀

- [R](https://www.r-project.org/)
- [Markdown](https://www.markdownguide.org/)
- [Latex](https://www.latex-project.org/)
- [Quarto](https://quarto.org/)

## Estrutura ⚙️
Os principais arquivos do projeto estão dentro da pasta `article`:

```
article
├── cite_styles
│   └── abnt.csl
├── data
│   ├── Basico_SP1.csv
│   ├── Basico_SP1.xls
│   ├── Domicilio01_SP1.xls
│   ├── DomicilioRenda_SP1.csv
│   ├── matrix
│   │   ├── distance2.gwt
│   │   ├── knn4.gwt
│   │   └── rainha1.gal
│   └── shapefinal
│       ├── shapefinal.dbf
│       ├── shapefinal.prj
│       ├── shapefinal.shp
│       └── shapefinal.shx
├── exports
│   ├── icb.pdf
│   ├── icf.pdf
│   ├── ico.pdf
│   ├── imoranicf.pdf
│   ├── imoraniqf.pdf
│   ├── iqf.pdf
│   ├── irc.pdf
│   ├── ird.pdf
│   ├── ire.pdf
│   ├── irf.pdf
│   ├── irl.pdf
│   ├── irr.pdf
│   ├── moranlocal.pdf
│   ├── moranlocalicf.pdf
│   ├── plb.pdf
│   ├── plbe.pdf
│   └── plp.pdf
├── images
│   ├── brasil.png
│   └── ufv2.png
├── main.pdf
├── main.qmd
├── referencies
│   └── ref.bib
└── tex_files
    ├── before-body.tex
    └── doc-class.tex
```

O arquivo `main.qmd` concentra quase todo código e texto do artigo. Esse arquivo é formado por um *header* e *chunks* de código.

Exemplo de *header* utilizado no artigo:

```
---
title: "MODELAGEM DA VARIÁVEL ORDINAL COM EFEITO ALEATÓRIO:"
subtitle: "Comparação entre as abordagens de regressão linear e regressão logística ordinal em um estudo de caso."
author: "ELIANA CARDOSO GONÇALVES"
author-upper: "ELIANA CARDOSO GONÇALVES"
#registration_number: "2021035292"
advisor: "Prof. Dr. Ilka Afonso Reis"
institution: "UNIVERSIDADE FEDERAL DE MINAS GERAIS"
setor: "INSTITUTO DE CIÊNCIAS EXATAS"
Departamento: "DEPARTAMENTO DE ESTATÍSTICA"
city: "BELO HORIZONTE"
state: "MG"
month: "Junho"
year: "2025"
confirm_text: "Monografia apresentada ao Departamento de Estatística da Universidade Federal de Minas Gerais como parte das exigências para obtenção do título de Bacharel em Estatística"
keywords: "Variável ordinal, Escala de Likert, Regressão Ordinal, Regressão Linear, Efeito Aleatório."
dedication: "Dedico esta monografia à curiosidade e à busca por compreender o mundo, mesmo sabendo que, como disse o estatístico britânico George Box, “todos os modelos estão errados, mas alguns são úteis”. Que este estudo represente uma tentativa sincera de encontrar utilidade na complexidade dos dados e contribuir, ainda que modestamente, para o conhecimento científico."
confirm_date: "30/06/2025"
advisor-name: " Dr. Ilka Afonso Reis"
advisor-name2: "Dr. Sarah Prates"
#bibliography: referencies/ref.bib
csl: cite_styles/abnt.csl
number-sections: true
lang: pt-BR
linkcolor: "black"
highlight-style: kate
fig-cap-location: top
format:
    pdf:
        template-partials:
            - tex_files/before-body.tex
            - tex_files/doc-class.tex
        mainfont: "Times New Roman"
keep-tex: true
editor: source
resources: 
  - "scr.R"
execute:
  echo: false
  warning: false
editor_options: 
  chunk_output_type: console
output:
  pdf_document: # Change to appropriate LaTeX template
    includes:
      in_header: 'gt_packages.sty'
---

```

Exemplo de um *chunk* de código R:
```
```{r echo=FALSE, warning=FALSE, message=FALSE, eval=FALSE}
# Download ESTBAN data from BigQuery
project_id <- "cloud-learning-doing"

sql <- "SELECT * FROM estban.estban_agencias_geolocalizadas WHERE data_base = '2010-12-01'"

query <- bigrquery::bq_project_query(
  project_id,
  sql,
)

agencias_2010 <- bigrquery::bq_table_download(query)```
```

A folha de estilo das citações ABNT é definida no arquivo `article/cite_styles/abnt.csl`, é lá que você precisará alterar para adequar sua citação à uma norma específica.

As referências podem ser incluídas no arquivo `article/referencies/ref.bib`, utilizando o já conhecido BibTeX.

O arquivo `article/tex_files/before-body.tex` contém o código LaTeX que gera a capa do artigo. Edite para se adequar às suas necessidades.

O arquivo `article/tex_files/doc_class.tex` contém todos os pacotes, funções e definições do projeto LaTeX. É possível incrementar bibliotecas por lá.

As demais pastas são completamente opcionais e serviram apenas para organizar o projeto: separar imagens, dados, arquivos .pdf gerados com `ggplot`, etc.

## Como utilizar 🧑‍🏫
Clone o repositório:
```{sh}
git clone https://github.com/flaviohugo14/quarto-abnt.git](https://github.com/elianacardoso1/TCC_final.git
```

Acesse a pasta do projeto:
```{sh}
cd quarto-abnt
```

Abra o projeto no seu editor de código preferido:
```{sh}
code .
```

Leia a documentação do [Quarto](https://quarto.org/) para entender seu funcionamento.

## Como contribuir 💡
- Realize um fork do repositório

```
# Faça um fork do repositório
$ gh repo fork flaviohugo14/quarto-abnt

# Clone o seu fork
$ git clone link-do-seu-fork

# Entre na pasta clonada
$ cd quarto-abnt

# Crie uma branch para sua feature
$ git checkout -b sua-feature

# Commite suas alterações
$ git commit -m "feature: Minha feature"

# Faça o push para a sua branch
$ git push origin sua-feature

```

---

