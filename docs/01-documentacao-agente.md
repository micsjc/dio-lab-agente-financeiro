# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Não temos uma  cultura financeira no Brasil. Uma pesquisa mostrou que em torno de 70% das pessoas estão endividadas. Essas pessoas precisam de conhecimento finanaceiro e um incentivo para mudarem essa situação

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente irá guiar o usuário pelo mundo financeiro, sendo um tutor rumo a sua estabilização financeira

### Público-Alvo
> Quem vai usar esse agente?

Pessoas leigas no mundo financeiro, mesmo as que tenham certa resistência

---

## Persona e Tom de Voz

### Nome do Agente
Gui

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Incentivador, educativo, paciente

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal, 

### Exemplos de Linguagem
- Saudação: Olá, sou o Gui. Me conte como posso te guiar hoje.
- Confirmação: Legal, Deixa eu ver o que podemos fazer.
- Erro/Limitação: Isso não sei, mas posso te ajudar com...

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Chatbot em Streamlit |
| LLM | Ollama |
| Base de Conhecimento | JSON/CSV com dados do cliente |
| Validação | Checagem de inconsistências |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Não sugere investimento
- [ ] Quando não sabe, admite e redireciona
- [ ] Não acessa dados sensíveis do cliente

### Limitações Declaradas
> O que o agente NÃO faz?
Não sugere investimentos
Não fala do que não sabe
Não substitui um profissional 

[Liste aqui as limitações explícitas do agente]
