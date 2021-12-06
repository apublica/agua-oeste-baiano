## Os privilegiados da água no cerrado baiano
Repositório para documentar os dados e a metodologia da análise de dados da reportagem "**Os privilegiados da água no cerrado baiano**" publicada pela Agência Pública de Jornalismo Investigativo.

## Como utilizar este repositório:
* Em `dados` estão as portarias em formato CSV;
* Em `código` estão os notebooks com os códigos em Python usado para a extração de portarias e para os cálculos de vazão.
* No repositório `visualização` estão os arquivos CSV utilizados para a produção dos infográficos no [flourish.studio](https://flourish.studio/)

## Metodologia da análise de dados:
### 1) Coleta/extração das portarias do Diário Oficial da Bahia
Inicialmente, as portarias foram coletadas a partir dos arquivos em PDF do DOE. O código utilizado pode ser visto no notebook `extracao_doe` na pasta com `códigos`.

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
A escrita foi padronizada, normalizando grafias diferentes de um mesmo assunto. Em seguida, filtramos as bacias de interesse (Rio Grande, Rio Corrente e Rio São Francisco), municípios do Oeste Baiano e as decisões "Autorizar o direito de uso dos recursos hidricos", "Autorizar a renovacao de outorga do direito de uso dos recursos hidricos", "Autorizar sob a forma de Outorga Preventiva a reserva das aguas dos recursos hidricos". Em alguns casos, foram incluídas portarias de alteração de outorga, pois modificava uma outra portaria já incluída na análise.

### 4) Análise
Agrupamos os valores por CPF/CNPJ, obtendo a soma da vazão autorizada para captação por pessoa física/jurídica em cada uma das bacias analisadas.
