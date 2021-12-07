## Os privilegiados da água no cerrado baiano
Repositório para documentar os dados e a metodologia da análise de dados da reportagem "**Os privilegiados da água no cerrado baiano**" publicada pela Agência Pública de Jornalismo Investigativo.

## Como utilizar este repositório:
* Em [`dados`](https://github.com/apublica/agua/tree/main/dados) estão as portarias em formato CSV;
* Em [`código`](https://github.com/apublica/agua/tree/main/c%C3%B3digo) estão os notebooks com os códigos em Python usado para a extração de portarias e para os cálculos de vazão.

## Metodologia da análise de dados:
### 1) Coleta/extração das portarias do Diário Oficial da Bahia
Inicialmente, as portarias foram coletadas "manualmente", nas edições em html do [Diário Oficial do Estado da Bahia](https://dool.egba.ba.gov.br/) e dos arquivos em PDF (após cadastro no site). O código utilizado pode ser visto no notebook [`extracao_doe_bahia`](https://github.com/apublica/agua/blob/main/c%C3%B3digo/extracao_doe_bahia.ipynb).

### 2) Busca de expressões regulares:
A partir do texto das portarias, fizemos a busca com editores de planilhas por expressões comuns na estrutura da portaria, descritas abaixo: 
* Nº da portaria
* Data de publicação
* Documento (CPF ou CNPJ)
* Nome/Razão social
* Bacia hidrográfica
* Município
* Validade da outorga
* Vazão (soma de todos os pontos de captação)
* Finalidade
* Tipo de captação
* Decisão (se é autorização, renovação, suspensão, etc)

### 3) Padronização do texto e filtros
A escrita foi padronizada, normalizando grafias diferentes de um mesmo assunto. Em seguida, filtramos as bacias de interesse (Rio Grande, Rio Corrente e Rio São Francisco), municípios do Oeste Baiano e as decisões "Autorizar o direito de uso dos recursos hídricos", "Autorizar a renovação de outorga do direito de uso dos recursos hídricos", "Autorizar sob a forma de Outorga Preventiva a reserva das águas dos recursos hídricos". Em alguns casos, foram incluídas portarias de alteração de outorga, pois modificava uma outra portaria já incluída na análise.

### 4) Análise
Agrupamos os valores por CPF/CNPJ, obtendo a soma da vazão autorizada para captação por pessoa física/jurídica em cada uma das bacias analisadas. Os resultados podem ser vistos [aqui](https://github.com/apublica/agua/blob/main/dados/dados_limpos.csv).
