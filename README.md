<p align="center">
  <img src="images/image_readme.png" alt="Descrição da Imagem">
</p>

# Projeto de Inadimpliência de Clientes de Cartão de Crédito 

_Este projeto consiste no trabalho final do 2º módulo da trilha de Data Science do Programa Santander Coders 2024.2._ 

* **Módulo** Técnicas de Programação I
* **Instrutor:** Prof. Roberto Pontes 
* **Grupo**: Filipe Sousa ([GitHub](https://github.com/filsousa) / [LinkedIn](https://www.linkedin.com/in/filipel-sousa/)), Gabriel Marques ([GitHub](https://github.com/marqsleal) / [LinkedIn](https://www.linkedin.com/in/marqsleal/)), Gabriel dos Santos e Maria Paula Andrade ([GitHub](https://github.com/MariaPaulaAndrade) / [LinkedIn](https://www.linkedin.com/in/maria-paula-andrade/)).

## Dependências 

Para instalar as dependências do projeto, execute:

```bash
pip install -r requirements.txt
```

## Instalação 

1. Clone o repositório:

```bash
git clone https://github.com/marqsleal/tecnicas-prog-projeto-final.git
```

2. Abra o arquivo `Projeto Final Tec Prog Inadimplência.ipynb` com o visualizador de notebooks de sua preferência:

```bash
code Projeto\ Final\ Tec\ Prog\ Inadimplência.ipynb
```

## Contexto de Negócios 

A inadimplência é um dos maiores desafios enfrentados pelo mercado, não apenas para empresas que prestam serviços financeiros mas também para firmas de varejo, imóveis, automóveis. O descumprimento de uma obrigação financeira dentro do período de vencimento pode ser explicado por diversos motivos, tais como desemprego, choque negativo de renda, despesas inesperadas, falta de planejamento financeiro, incompatibilidades no custo de vida e orçamento doméstico. Os prejuízos provocados pela inadimplência são inúmeros, tanto para consumidores como para empresas. 

Na tentativa de evitar ou minimizar prejuízos financeiros, empresas de diversos segmentos buscam fazer um mapeamento de perfis de pagadores para caracterizá-los em 'bons' ou 'ruins'. Uma vez mapeados os perfis, as empresas podem direcionar o seu plano de estratégia e recursos operacionais para determinados perfis e alcançar os seus objetivos de forma mais eficiente e assertiva. Por exemplo, empresas de cobrança podem canalizar os seus esforços para clientes que tenham maior probabilidade de pagamento a fim de recuperar o crédito. Da mesma forma, instituições financeiras podem mirar em bons pagadores para minimizar os riscos e eventuais prejuízos.

## Objetivos 

O principal objetivo deste projeto é mapear e identificar se um usuário de cartão de crédito é bom ou mau pagador com base em suas características financeiras e demográficas para da suporte a tomada de decisão de empresas de cobrança/recuperação de crédito e concessão de empréstimo. Os objetivos técnicos deste estudo de caso são:
* Entender as características do conjunto de dados (dimensão, tipo de variáveis).
* Avaliar a integridade e consistência dos dados (valores ausentes, duplicidades etc).
* Elaborar estatísticas descritivas das variáveis numéricas.
* Analisar as relações entre inadimplência e variáveis demográficas e financeiras.
* Utilizar as bibliotecas NumPy e Pandas para executar as atividades anteriores.

## Dados 

O conjunto de dados usado neste projeto é uma versão modificada do dados originais hospedados no UCI Machine Learning Repository, que podem ser encontrados [neste link](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients). O conjunto de dados foi adaptado por Setephen Klosterman no livro 'Data Science Projects with Python' com o objetivo de adicionar dados que demandassem tratamento inicial. O dataset possui 30.000 linhas onde cada qual corresponde a uma conta bancária/cliente e 24 variáveis contendo informações financeiras e demográficas. Os dados são mensais e vão de Abril de 2005 a Setembro de 2005. Todas as variáveis de valor financeiro estão em dólares de Taiwan (\$NT).

1. **Identificador**
   - ID - código de identificação do cliente
2. **Variáveis demográficas**
    - SEX (sexo biológico)
    - EDUCATION (nível de escolaridade)
    - MARRIAGE (estado civil)
    - AGE (idade)
3. **Variáveis financeiras**
    - LIMIT_BAL (limite de crédito em NT\\$)
    - PAY_1 a PAY_6 (status de pagamento de Setembro a Abril de forma regressiva)
    - BILL_1 a BILL_6 (valor da fatura mensal de Setembro a Abril de forma regressiva)
    - PAY_AMT1 a PAY_AMT6 (valor da fatura paga no mês anterior para cada mês do intervalo de Setembro a Abril)
4. **Variável de Inadimplência**
   - default payment next month (se o cliente pagou ou não a dívida em Outubro de 2005)

## Bibliotecas 

* NumPy (para cálculo numérico)
* Pandas (para manipulação de dados)
* Matplotlib (para visualização de dados)

## Resumo do Projeto 

- **Entendendo a base de dados:** Verificação da dimensão dos dados, da quantidade de missing values e de duplicidades.
- **Tratamento de dados:** Exclusão de identificadores duplicados, rearranjo e exclusão de novas classes que surgiram nas variáveis categorias, checagem e tratamento de inconsistências nos dados de status de pagamento de séries temporais, substituição dos valores das variáveis categóricas pelos nomes das suas respectivas classes, renomeação de variáveis, conversão monetária de dólares taiwaneses para dólares americanos. 
- **Análise Gerais:** Proporção de adimplentes e inadimplentes por classes das variáveis categóricas, estatísticas descritivas das variáveis numéricas dividas por grupo de adimplentes e inadimplentes, comparação das proporções de adimplentes e inadimplentes por classes derivadas de interações (por exemplo, diferenças de bons e maus pagadores por sexo e nível de escolaridade).
- **Principais observações**
  - A base tem 77.83\% de adimplentes e 22.17\% de inadimplentes.
  - A maior parte do conjunto de dados é composta de mulheres, pessoas com graduação, solteiros e adimplentes (bons pagadores).
  - A média de idade do grupo de adimplentes e inadimplentes é de 35 anos. Mas existem diferenças entre os dois grupos de pagadores quando a idade é sgmentada.
  - Em média, o limite de crédito é maior para adimplentes do que para inadimplentes.

## Próximos passos 

- Aplicar algorítimos de aprendizagem de máquina supervisionada para identificar as variáveis preditoras de inadimplência.
- Aplicações de testes estatísticos com o objetivo de verificar a distribuição das variáveis.