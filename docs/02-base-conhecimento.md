# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados

Sem adaptações.

---

## Estratégia de Integração

### Como os dados são carregados?

Os dados serão injetados diretamente no prompt (Ctrl + C/V) ou os arquivos serão carregados via código, como no exemplo abaixo:

```python
import pandas as pd
import json

#CSV
historico = pd.read_csv(data/historico_atendimento.csv)
transacoes = pd.read_csv(data/transacoes.csv)

#json
with open('data/perfil_investidor.json', 'r', encoding='utf-8') as f:
  perfil = json.load(f)

´´´

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

``` text
DADO DOS CLIENTE:

PERFIL DO CLIENTE:

TRANSAÇÕES DO CLIENTE:

´´´

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
