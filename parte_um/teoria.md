## 1. Sinais Contínuos e Discretos

Um sinal é uma função que representa a variação de uma grandeza física ao longo do tempo.

- **Sinal contínuo:** definido para todos os instantes de tempo.
  
  Exemplo:
  x(t)

- **Sinal discreto:** definido apenas em instantes discretos, geralmente obtidos por amostragem.
  
  Exemplo:
  x[n]

### Aplicação em Engenharia

Sensores reais (temperatura, vibração, pressão) geram sinais contínuos, mas sistemas digitais processam versões discretizadas desses sinais.

---

## 2. Sequências Elementares

### 2.1 Impulso Unitário

O impulso unitário (delta de Kronecker) é definido como:

δ[n] = 1, se n = 0  
δ[n] = 0, se n ≠ 0  

É utilizado para analisar sistemas, pois qualquer sinal pode ser representado como uma combinação de impulsos.

---

### 2.2 Degrau Unitário

O degrau unitário é definido como:

u[n] = 1, se n ≥ 0  
u[n] = 0, se n < 0  

É utilizado para modelar a ativação de sistemas.

---

### 2.3 Exponenciais Complexas

As exponenciais complexas são dadas por:

x[n] = A * e^(jωn)

Essas funções são fundamentais na análise em frequência e no processamento digital de sinais.

---

## 3. Operações com Sinais

### 3.1 Deslocamento no tempo

x[n - n₀]

Representa atraso (n₀ > 0) ou avanço (n₀ < 0).

---

### 3.2 Inversão no tempo

x[-n]

Reflete o sinal em torno da origem.

---

### 3.3 Escalonamento de amplitude

a * x[n]

Altera a amplitude do sinal.

---

### Aplicações

- Atrasos em sensores → deslocamento
- Inversão de fase → inversão temporal
- Amplificação → escalonamento

---

## 4. Energia e Potência de Sinais

### 4.1 Energia

E = Σ |x[n]|², para n de -∞ até +∞

Um sinal é de energia se E for finita.

---

### 4.2 Potência

P = lim (N→∞) [1/(2N+1)] Σ |x[n]|², para n de -N até N

Um sinal é de potência se P for finita.

---

### Interpretação

- Sinais de energia: transitórios (ex: pulso)
- Sinais de potência: periódicos (ex: senoide contínua)

---

## 5. Classificação de Sistemas Discretos

### 5.1 Sistemas com e sem memória

- Sem memória: saída depende apenas da entrada atual.
- Com memória: depende de valores passados ou futuros.

---

### 5.2 Sistemas lineares

Um sistema é linear se satisfaz o princípio da superposição:

T{a·x₁[n] + b·x₂[n]} = a·T{x₁[n]} + b·T{x₂[n]}

---

### 5.3 Sistemas causais

- Causal: depende apenas do presente e passado.
- Não causal: depende do futuro.

---

### 5.4 Invariância no tempo

Um sistema é invariante no tempo se um deslocamento na entrada provoca o mesmo deslocamento na saída.

---

### 5.5 Estabilidade (BIBO)

Um sistema é estável se toda entrada limitada produz uma saída limitada.

---

### 5.6 Invertibilidade

Um sistema é invertível se é possível recuperar a entrada a partir da saída.

---

## 6. Relação com Sistemas Reais

Os conceitos estudados são fundamentais para modelar sinais provenientes de sistemas reais:

### Vibração em máquinas rotativas
Utilizada para diagnóstico de falhas mecânicas.

---

### Sensores térmicos
Aplicados no controle de processos industriais.

---

### Sinais elétricos digitais
Presentes em circuitos e sistemas computacionais.

---

### Velocidade e rotação de eixos
Importantes em sistemas de controle e automação.

---

### Sistemas embarcados
Responsáveis pela aquisição e processamento de sinais em tempo real.

---

## Conclusão

A representação de sinais no domínio discreto permite o processamento digital de informações provenientes de sensores reais.

A análise das propriedades dos sistemas — como linearidade, causalidade, estabilidade e invariância no tempo — é essencial para garantir que o processamento seja correto, confiável e implementável em sistemas reais.

Esses conceitos formam a base para aplicações em engenharia, incluindo controle de sistemas, processamento de sinais biomédicos, telecomunicações e sistemas embarcados.