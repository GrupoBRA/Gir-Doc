# Gir-Doc
Documentação da API e App para gestão de Guias de Recolhimento no OnyxERP

# GIR(L-1105)
Aplicação para gestão de Guias de Informação e Recolhimento.


# Escopo

Documento para empenho do débito da contribuição previdenciária devida ao RPPS.
 - Eu recebo a informação das contribuições previdenciárias dos servidores ATIVOS dos seus respectivos Entes;
 - Eu gero uma guia a partir destas informações;
 - Eu envio essa guia para quitação junto as Entidades.

### Configurações
  * Número sequencial
  * Dia de vencimento mensal
  * Vencimento: Mes corrente ou subsequente
  * Percentual de Juros
  * Cálculo do Juros: Por Mês ou Pró-rata(por dia)
  * Percentual de Multa
  * Legislação Juros
  * Legislação Multa
  * Agência
  * Conta Corrente

# Funcionalidades

  * Cadastro de GIRs por lotação
  * Cadastro de GIRs por Entidade
  * Cadastro de GIRs por Segurado(pf_id+servidor_id)
  * Emissão de GIRs Patronal
  * Emissão de GIRs Segurado
  * Emissão de GIRs Completa
  * Emissão de GIRs de Aporte
  * Cálculo parcial dos valores conforme o lançamento
  * Marcar uma Guia paga: parcial ou completa
  * Ao 'pagar' uma Guia parcialmente, informar se o pagamento é referente ao valor Patronal ou Segurado e;
  * Gerar uma nova Guia, com o valor não quitado de forma automática, com o saldo devedor da parte informada no passo anterior
  * Suporte para emissão de Guia com boleto e código de barras

## Descrição
  Patronal
    - A guia deve ser emitida considerando somente os valores da contribuição patronal(Órgão) + Custo Suplementar

  Segurado
    - A guia deve ser emitida considerando somente os valores da contribuição do segurados

  Completo
    - A guia deve ser emitida considerando os valores de contribuição do segurados e do Órgão somados

  Aporte
    - A guia deve ser emitida considerando somente os valores do campo Aporte

### Cadastro
  * Órgão
  * Lotação
  * Segurado(pf_id+servidor_id)
  * Número Sequencial(automático)
  * Informação de parcelamento(quando oriúnda de Guia parcialmente quitada(saldo devedor))
  * Número de Servidores
  * Competência
  * Emissão
  * Vencimento
  * Contribuição Patronal(R$)
  * Aporte
  * Contribuição Segurado(R$)
  * Valor da Folha Base(R$)
  * Valor da Folha Bruta(R$)
  * Custo Suplementar(R$)
  * Juros(R$)
  * Multas(R$)
  * Restituições(R$)
  * Situação(Aberta/Quitada/Parcial)
  * Texto livre(editor)

  Patronal/Segurado/Individual
    - Devem ser informados os valores: Patronal, Suplementar, Segurado e Folhas

  Aporte
    - Devem ser informados somente os valores de Aporte

### Exibição
 Listagem em GRID, dos seguintes campos:
  * Número
  * Competência
  * Entidade
  * Lotação
  * Nome/Matrícula(pf_id)
  * Situação


### Filtros

  * Número
  * Entidade
  * Lotação
  * Segurado(pf_id+servidor_id)
  * Sitaução
  * Data de Emissão(Intervalo)
  * Data de Vencimento(Intervalo)


### Especificações

  * Número sequencial customizável
  * Cálculo automático dos valores de contribuição a partir das alíquotas, considerando as alíquotas Patronal, Patronal Suplementar e Segurado
  * Cálculos automáticos de Juros e Multa
  * Exibir informações de Sacado(Entidade), Sacador(RPPS), dados bancários, informações de Juros e Multas, conforme boletos convencionais
  * Registrar pagamento da Guia, informando o tipo de quitação(quando parcial) e data de pagamento
  * Ao registrar o pagamento de uma Guia individual, os valores do campos Competência, Patronal e Segurado devem ser registrados no histórico de contribuição do sergurado juntamente com as informações das alíquotas de contribuição, na RhAPI 

# Relatórios

Por:
  * Entidade
  * Lotação
  * Segurado(pf_id+servidor_id)
  * Sitaução
  * Data de Emissão(Intervalo)
  * Data de Vencimento(Intervalo)
  * Situação
  * Tipo de quitação(Segurado ou Patronal)
