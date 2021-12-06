## Os privilegiados da água no cerrado baiano
Repositório para documentar os dados e a metodologia da análise de dados da reportagem "**Os privilegiados da água no cerrado baiano**" publicada pela Agência Pública de Jornalismo Investigativo.

## Como utilizar este repositório:
* Em `dados` estão as portarias em formato CSV;
* Em `código` estão os notebooks com os códigos em Python usado para a extração de portarias e para os cálculos de vazão.
* No repositório `visualização` estão os arquivos CSV utilizados para a produção dos infográficos no [flourish.studio](https://flourish.studio/)

## Metodologia da análise de dados:
### 1) Coleta/extração das portarias do Diário Oficial da Bahia
Inicialmente, as portarias foram coletadas manualmente no DOE. A extração com código foi realizada a partir de setembro de 2021;

### 2) Busca de expressões regulares:
A partir do texto das portarias, fizemos a busca por expressões regulares no Excel para extrair alguns elementos de cada portaria, descritos abaixo: 
* Nº da portaria
* Data de publicação
* Documento (CPF ou CNPJ)
* Nome/Razão social
* Bacia hidrográfica = Rio Grande, Rio Corrente e Rio São Francisco
* Município
* Validade da outorga
* Vazão (soma de todos os pontos de captação)
* Finalidade
* Tipo de captação
* Decisão (se é autorização, renovação, suspensão, etc)

### 3) Padronização do texto e filtros
A escrita foi padronizada, normalizando grafias diferentes de um mesmo assunto. Em seguida, aplicamos os seguintes filtros:
* Bacia hidrográfica = Rio Grande, Rio Corrente e Rio São Francisco;
* Para as portarias a partir de setembro de 2021 (obtidas através de código), foi aplicado o filtro **Município** = Angical, Baianópolis, Barreiras, Brejolândia, Canápolis, Catolândia, Cocos, Coribe, Correntina, Cotegipe, Cristópolis, Formosa Do Rio Preto, Jaborandi, Luís Eduardo Magalhães, Mansidão, Riachão Das Neves, Santa Maria Da Vitória, Santa Rita De Cássia, Santana, São Desidério, São Félix Do Coribe, Serra Dourada, Tabocas Do Brejo Velho, Wanderley;
* Decisão = "Autorizar o direito de uso dos recursos hidricos", "Autorizar a renovacao de outorga do direito de uso dos recursos hidricos", "Autorizar sob a forma de Outorga Preventiva a reserva das aguas dos recursos hidricos".

### 4) Análise Agrupando valores de vazão e de quantidade de outorgas por CPF e CNPJ
Agrupamos os valores por CPF/CNPJ, calculando a quantidade de outorgas e a soma da vazão autorizada para captação por pessoa física/jurídica, divididos pelas bacias analisadas.
