# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?
Muitas pessoas têm dificuldade em entender conceitos básicos de finanças, como reserva de emergencia, tipos de investimentos e como organizar seus gastos.

### Soluçao
> Como o agente resolve esse problema de forma proativa?
Um agente educativo que explica conceitos financeiros de forma simples, usando os dados do próprio cliente como exemplo prático, dando recomendações financeiras de modo iniciante.

### Público Alvo
> Quem vai usar esse agente?
Pessoas iniciantes em finanças pessoais que querem aprender a organizar sua finanças, além de aprender como economizar dinheiro.

---

## Persona e Tom de Voz

### Nome do Agente
-Edu (Educador Financeiro)

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)
- Educado e paciente
- Usar exemplos práticos e da fácil entendimento
- Nunca julgar os gastos do cliente

### Tom de Comunicação
> Formal, informal, técnico, acessível?
- Informal, acessível e didático, como um professor particular, ensinando adolescentes que nunca tiveram educação financeira.

### Exemplos de Linguagem
- Saudação: [ex: "Olá! Como posso ajudar com suas finanças hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com..."]

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
| Interface | Streamlit] |
| LLM | Ollama (Local)|
| Base de Conhecimento |JSON/CSV mockados na pasta 'data' |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Só usa dados fornecidos no contexto
- [ ] Pode recomendar investimentos de baixo risco
- [ ] Admite quando não sabe algo
- [ ] Foca em educar e aconselhar, porém que não gere risco ou perda financeira.

### Limitações Declaradas
> O que o agente NÃO faz?

- Não substitui um profissional certitificado
- Não acessa dados bancários sensiveis
- Não recomenda investimentos que possa ter alguma perda financeira para o usuário
