# Análise de incidentes de Segurança com Python

Análise exploratória de registros públicos de incidentes de segurança da informação utilizando Python, Pandas, Matplotlib e Seaborn.

## Objetivo

Analisar padrões presentes em registros públicos de incidentes de segurança, utilizando dados estruturados segundo o framework VERIS.

A análise busca identificar diferenças na distribuição dos incidentes entre setores e observar quais categorias de ação e vetores aparecem com maior frequência nos registros analisados.

## Pergunta de análise

> Quais padrões de ocorrência e características dos incidentes de segurança podem ser observados nos registros analisados?

## Fonte dos dados

Os dados utilizados são provenientes do **VERIS Community Database (VCDB)**.

O **Verizon Data Breach Investigations Report (DBIR) 2026** é utilizado como referência metodológica e contextual. O conjunto completo de registros utilizado no DBIR não é disponibilizado publicamente; por isso, esta análise utiliza o VCDB como fonte pública de dados estruturados segundo o VERIS.

Fonte:

* VCDB: https://github.com/vz-risk/VCDB
* Verizon DBIR: https://www.verizon.com/business/resources/reports/dbir/

## Tecnologias utilizadas

* Python
* Pandas
* Matplotlib
* Seaborn
* Jupyter Notebook
* Git
* GitHub

## Estrutura do projeto

```text
analise-incidentes-seguranca/
│
├── notebooks/
│   └── 01_exploracao_inicial.ipynb
│
├── data/
│   └── raw/
│       └── vcdb.csv
│
├── .gitignore
└── README.md
```

Os dados brutos não são versionados neste repositório devido ao seu tamanho. O `.gitignore` também impede o envio acidental desses arquivos para o GitHub.

## Metodologia

A análise foi realizada em etapas:

1. Carregamento dos dados do VCDB.
2. Seleção das variáveis relevantes para a análise.
3. Limpeza básica dos dados.
4. Análise da distribuição dos incidentes por setor.
5. Análise das categorias de ação.
6. Análise da relação entre setores e categorias de ação.
7. Análise dos principais vetores de Hacking, Malware, Social Engineering e Error.
8. Visualização dos resultados por meio de gráficos e mapas de calor.
9. Identificação das principais limitações dos dados.

A análise final utiliza **10.596 registros de incidentes** e 142 variáveis selecionadas a partir da estrutura original do VCDB.

## Principais análises

### Categorias de ação

As categorias de ação analisadas foram:

* Hacking
* Malware
* Social
* Physical
* Misuse
* Error
* Environmental
* Unknown

As categorias não são mutuamente exclusivas. Um mesmo incidente pode apresentar mais de uma categoria de ação.

### Setores

A análise considera a distribuição dos registros entre diferentes setores, com destaque para:

* Healthcare
* Public
* Educational
* Finance
* Information
* Retail
* Professional

### Vetores de Hacking

Entre os incidentes classificados como Hacking, foram analisados os principais vetores conhecidos, incluindo:

* Web application
* Backdoor
* Other
* Partner
* Physical access

### Vetores de Malware

Entre os incidentes classificados como Malware, foram analisados:

* Direct install
* Remote injection
* Email attachment
* Web application
* Web drive-by

### Vetores de Social Engineering

Entre os incidentes classificados como Social Engineering, foram analisados:

* Email
* In-person
* Phone
* Documents
* SMS

### Vetores de Error

Entre os incidentes classificados como Error, foram analisados:

* Carelessness
* Inadequate processes
* Web application
* Random error
* Other

## Principais observações

* Hacking e Error estão entre as categorias de ação mais frequentes na base analisada.
* Healthcare, Public e Educational possuem as maiores quantidades de registros na base analisada.
* A distribuição das categorias de ação varia entre os setores.
* Web application é o vetor conhecido mais frequente entre os incidentes classificados como Hacking.
* Direct install e Remote injection aparecem entre os vetores conhecidos mais frequentes de Malware.
* Email é o vetor conhecido mais frequente entre os incidentes classificados como Social Engineering.
* Carelessness é o vetor conhecido mais frequente entre os vetores conhecidos de Error.
* Uma parcela relevante dos registros possui informações não especificadas, especialmente nos vetores de Error.

Essas observações descrevem padrões presentes nos registros analisados e não representam necessariamente a distribuição global dos incidentes de segurança.

## Limitações

### Dados não completos

A base contém registros com informações não especificadas, representadas principalmente por `Unknown`.

Essa ausência de informação pode limitar a interpretação de determinadas variáveis.

### Sobreposição das categorias

As categorias de ação não são mutuamente exclusivas.

Um mesmo incidente pode apresentar mais de uma categoria de ação ou mais de um vetor. Portanto, os percentuais apresentados não devem ser somados como se representassem partes exclusivas de um total.

### Distribuição dos registros

A quantidade de registros varia entre os setores.

Setores com poucos registros podem apresentar proporções menos estáveis e devem ser interpretados com maior cautela.

### Representatividade

O VCDB é uma base pública de incidentes e não deve ser interpretado como um levantamento completo de todos os incidentes de segurança existentes.

A composição dos registros pode refletir critérios de seleção, disponibilidade de informações e outras características da coleta.

Portanto, os resultados descrevem os padrões observados na base analisada e não devem ser generalizados diretamente para todos os incidentes de segurança.

### Associação não implica causalidade

A análise possui caráter exploratório e descritivo.

A associação observada entre um setor, uma categoria de ação ou um vetor não permite concluir que uma característica tenha causado outra.

## Reprodução da análise

Para reproduzir o projeto:

1. Clone o repositório.
2. Crie um ambiente virtual Python.
3. Instale as dependências.
4. Obtenha o arquivo `vcdb.csv` a partir do VCDB.
5. Coloque o arquivo em:

```text
data/raw/vcdb.csv
```

6. Abra o notebook:

```text
notebooks/01_exploracao_inicial.ipynb
```

7. Execute as células na ordem apresentada.

## Objetivo do projeto

Este projeto foi desenvolvido como estudo prático de análise de dados aplicada à segurança da informação, com foco em:

* manipulação de dados com Pandas;
* exploração de bases de dados reais;
* criação de visualizações;
* interpretação de padrões;
* documentação de limitações;
* organização de um projeto de análise no GitHub.
