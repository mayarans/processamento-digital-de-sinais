# Estudo Dirigido 02 – Convolução e Sistemas LTI
## Análise dos Resultados

---

## 1. Atividade 1 – Interpretação Conceitual

### 1) Sistema linear e invariante no tempo

Um sistema é dito linear quando obedece o princípio da superposição, ou seja, a resposta a uma combinação linear de entradas é igual à combinação linear das respostas individuais.

Um sistema é invariante no tempo quando seu comportamento não depende do instante em que a entrada é aplicada. Isso significa que, se a entrada for deslocada no tempo, a saída sofrerá o mesmo deslocamento.

---

### 2) Importância da resposta ao impulso

A resposta ao impulso caracteriza completamente um sistema LTI porque qualquer sinal discreto pode ser representado como uma soma de impulsos deslocados. Assim, conhecendo a resposta do sistema a um impulso, é possível determinar a saída para qualquer entrada por meio da convolução.

---

### 3) Significado físico da convolução

A convolução representa como um sistema acumula e pondera versões deslocadas da sua resposta ao impulso em função da entrada. Em termos físicos, ela descreve como o sistema "filtra" ou modifica o sinal de entrada ao longo do tempo.

---

### 4) Resposta transitória vs regime permanente

A resposta transitória corresponde ao comportamento inicial do sistema após a aplicação de uma entrada. Já o regime permanente ocorre quando o sistema atinge um comportamento estável ao longo do tempo.

---

### 5) Sistema causal

Um sistema é causal quando a saída em um determinado instante depende apenas de valores presentes ou passados da entrada, nunca de valores futuros.

---

### 6) Sistema estável

Um sistema é estável quando toda entrada limitada gera uma saída também limitada.

---

## 2. Atividade 2 – Cálculo Manual da Convolução

Dadas as sequências:

x[n] = {1, 2, 1}  
h[n] = {1, 1}

### 1) Cálculo da convolução

A convolução discreta é dada por:

y[n] = Σ x[k] h[n − k]

Calculando termo a termo:

y[0] = 1×1 = 1  
y[1] = 1×1 + 2×1 = 3  
y[2] = 2×1 + 1×1 = 3  
y[3] = 1×1 = 1  

---

### 2) Resultado

y[n] = {1, 3, 3, 1}

---

### 3) Interpretação

O resultado mostra que o sistema está realizando uma espécie de soma local dos valores da entrada. Isso é típico de um filtro que combina amostras vizinhas, indicando comportamento de suavização.

---

## 3. Atividade 3 – Equação de Diferenças

Sistema:

y[n] = 0.8 y[n − 1] + x[n]  
x[n] = δ[n]

### 1) Cálculo da resposta ao impulso

Condição inicial: y[-1] = 0

h[0] = 1  
h[1] = 0.8  
h[2] = 0.64  
h[3] = 0.512  
h[4] = 0.4096  
h[5] = 0.32768  

---

### 2) Análise de estabilidade

A sequência h[n] é uma exponencial decrescente, tendendo a zero. Como a soma dos valores absolutos é finita, o sistema é estável.

---

### 3) Causalidade

O sistema depende apenas de y[n−1] e x[n], ou seja, de valores presentes e passados. Portanto, é causal.

---

## 4. Atividade 4 – Convolução 

Atividades 4 e 5 desenvolvidas na plataforma colab:
https://colab.research.google.com/drive/1QU7XNS6ML30Qs9zVOUs_vZCfU43mCbWq?authuser=1


### 1) Comparação com cálculo manual

A execução do código com a função produz o mesmo resultado obtido manualmente:

y[n] = {1, 3, 3, 1}

Isso valida o cálculo analítico realizado.

---

### 2) Forma do sinal de saída

O formato do sinal apresenta um crescimento até um pico e depois decresce. Isso ocorre devido à sobreposição progressiva e posterior redução das contribuições da convolução.

---

### 3) Novo sinal: x[n] = {1, 1, 1, 1}

Resultado:

y[n] = {1, 2, 2, 2, 1}

---

### Interpretação

Esse resultado mostra um comportamento típico de soma acumulativa local, indicando que o sistema atua como um filtro de média simples.

---

## 5. Atividade 5 – Suavização de Sinais

---

### 1) Convolução

O resultado da convolução produz um sinal mais suave, com variações menos abruptas.

---

### 2) Análise dos gráficos

O sinal original apresenta variações rápidas, enquanto o sinal filtrado apresenta transições mais suaves.

---

### 3) Interpretação

O filtro atua como suavizador porque realiza uma média entre valores consecutivos, reduzindo variações bruscas e ruídos de alta frequência.

---

## 6. Atividade 6 – Estabilidade e Causalidade

### a) y[n] = x[n] + x[n − 1]

- Causal: sim  
- Estável: sim  

---

### b) y[n] = x[n + 1]

- Causal: não (depende do futuro)  
- Estável: sim  

---

### c) h[n] = (0.5)^n u[n]

- Causal: sim  
- Estável: sim (série convergente)

---

### d) h[n] = 2^n u[n]

- Causal: sim  
- Estável: não (cresce exponencialmente)

---

## 7. Desafio – Suavização de Sinais

A convolução com um filtro de média móvel melhora a qualidade do sinal ao reduzir variações rápidas e ruídos.

---

### Papel da resposta ao impulso

A resposta ao impulso define o comportamento do filtro. No caso da média móvel, ela atribui pesos iguais a amostras vizinhas.

---

### Por que ocorre a suavização

A suavização ocorre porque o filtro realiza uma média local, reduzindo a influência de variações abruptas e ruídos de alta frequência.

---

### Limitações

- perda de detalhes do sinal original  
- atraso no sinal (delay)  
- redução da capacidade de detectar mudanças rápidas  

---

## 8. Conclusão

Os resultados demonstram que a convolução é uma ferramenta fundamental para análise e processamento de sinais discretos.

A relação entre resposta ao impulso, equações de diferenças e comportamento do sistema permite compreender como sistemas reais operam.

Esses conceitos são amplamente aplicados em filtragem de sinais, sistemas embarcados e análise de dados provenientes de sensores.