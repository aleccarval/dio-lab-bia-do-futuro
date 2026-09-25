# Base de Conhecimento

> [!TIP]
> **Prompt Sugerido para esta etapa:**
> Preciso organizar a base de conhecimento do meu agente financeiro educativo.
> Tenho estes arquivos de dados: [liste os arquivos].
> Me ajude a: (1) entender o que cada arquivo contém, (2) decidir como usar cada um, (3) criar um exemplo de contexto formatado para incluir no prompt.


## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores através do registro de atendimentos |
| `perfil_investidor.json` | JSON | Personalizar as conversas com os usuários |
| `produtos_financeiros.json` | JSON | Demonstrar os produtos disponíveis para o perfil do usuário|
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados

O produto Fundo Imobiliário  (FII) substituiu o Fundo Multimercado.

---

## Estratégia de Integração

### Como os dados são carregados?
``` python
import pandas as pd
import json

# ============ CARREGAR DADOS ============
perfil = json.load(open('./data/perfil_investidor.json'))
transacoes = pd.read_csv('./data/transacoes.csv')
historico = pd.read_csv('./data/historico_atendimento.csv')
produtos = json.load(open('./data/produtos_financeiros.json'))
```

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

[Sua descrição aqui]

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
