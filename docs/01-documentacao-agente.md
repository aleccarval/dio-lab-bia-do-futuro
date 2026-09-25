# Documentação do Agente

> [!TIP]
> **Prompt Sugerido para esta etapa:**
> ```
> Me ajude a documentar um agente de IA financeiro. O caso de uso é [descreva seu caso de uso].
> Preciso definir: problema que resolve, público-alvo, personalidade do agente, tom de voz
> e estratégias anti-alucinação. Use o template abaixo como base:
> [cole o template 01-documentacao-agente.md]


## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Elimina o medo de faltar dinheiro no futuro e a dependência do INSS, garantindo uma renda previsível para você manter seu padrão de vida sem precisar trabalhar por obrigação.

### Solução
> Como o agente resolve esse problema de forma proativa?

Ele monitora continuamente os hábitos e investimentos do usuário para corrigir desvios no orçamento, otimizar impostos e rebalancear a carteira antes que o futuro financeiro dele seja prejudicado.

### Público-Alvo
> Quem vai usar esse agente?

Profissionais, autônomos e empreendedores digitais de 30 a 50 anos que possuem capacidade de poupança, mas carecem de tempo ou conhecimento especializado para planejar o próprio futuro financeiro

---

## Persona e Tom de Voz

### Nome do Agente
EDI (Assistente da EDIT)

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Educado e paciente
- Usa exemplos práticos
- Nunca julga os gastos do cliente

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal, acessível e didático, como um professor particular.

### Exemplos de Linguagem
- Saudação: "Olá! Tudo bem? Estou pronto para ajudar com seu futuro. Vamos começar?"
- Confirmação: "Entendido! Só um instante enquanto verifico."
- Erro/Limitação: "Não consigo te ajudar com essa informação agora, vamos experimentar algo mais focado no seu futuro..."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] -->|Mensagem| B[Chat]
    B --> C[IA]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
    F[Resposta]--> |Mensagem| A[Usuário]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [Streamlit](http://streamlit.io/)|
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV com dados do cliente |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [x] Só usa dados fornecidos no contexto
- [x] Não recomenda investimentos específicos
- [x] Admite quando não sabe algo
- [x] Foca apenas em instruir

### Limitações Declaradas
> O que o agente NÃO faz?

- NÂO faz recomendação de investimentos
- NÂO acessa contas pessoais (E-mails, Bancos etc)
- Não substitui profissionais da área
