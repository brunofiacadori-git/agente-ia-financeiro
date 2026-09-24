# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Pra que Serve na FinanIA |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores ou seja, dar continuidade ao atendimento de forma eficiente |
| `perfil_investidor.json` | JSON | Armazenar informações financeiras e objetivos do usuário para personalizar as análises |
| `produtos_financeiros.json` | JSON | Fornecer informações sobre produtos financeiros disponíveis quando relevantes para a análise|
| `transacoes.csv` | CSV | Registrar e analisar receitas, despesas, categorias e padrões de gastos do usuário |


---

## Adaptações nos Dados

Os dados mockados originais não foram modificados ou expandidos. A FinaIA utiliza os mesmos arquivos disponibilizados na pasta data.

A adaptação está na forma como os dados são interpretados e utilizados pelo agente. As informações existentes passam a ser utilizadas para identificar padrões financeiros, analisar receitas e despesas, comparar períodos, identificar gastos relevantes e auxiliar o usuário na tomada de decisões relacionadas à sua organização financeira.

---

## Estratégia de Integração

### Como os dados são carregados?

Os arquivos JSON e CSV existentes na pasta data são carregados pela aplicação e utilizados como base de conhecimento da FinaIA.

As informações são processadas conforme a necessidade da solicitação do usuário, permitindo que o agente utilize os dados financeiros relevantes para cada análise.

### Como os dados são usados no prompt?

Os dados relevantes são utilizados dinamicamente como contexto para o modelo de linguagem.

A FinanIA interpreta a pergunta do usuário, identifica quais informações da base são necessárias e utiliza esses dados para elaborar a resposta. Dessa forma, o agente evita depender apenas de informações genéricas e consegue fornecer respostas contextualizadas com os dados disponíveis.

---

## Exemplo de Contexto Montado

```
Dados do Cliente:
- Nome: João Silva
- Perfil financeiro: Moderado
- Renda mensal: R$ 5.000
- Objetivo financeiro: Economizar e organizar o orçamento Resumo financeiro:
- Receitas: R$ 5.000 - Despesas: R$ 3.850
- Saldo disponível: R$ 1.150

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
- 05/11: Transporte - R$ 120
- 08/11: Restaurante - R$ 180

Sugestão de investimento:
    "nome": "LCI/LCA",
    "categoria": "renda_fixa",
    "risco": "baixo",
    "rentabilidade": "95% do CDI",
    "aporte_minimo": 1000.00,
    "indicado_para": "Quem pode esperar 90 dias (isento de IR)"
...
```

Análise solicitada:
"Quais gastos posso reduzir este mês?"

A FinanIA utiliza os dados disponíveis para identificar categorias relevantes,
comparar os gastos e apresentar sugestões baseadas nas informações fornecidas.

Observação: O exemplo acima representa apenas a estrutura do contexto. Os valores reais utilizados pelo agente devem ser obtidos diretamente dos datasets existentes na pasta data.
