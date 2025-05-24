# Estatística básica (média, mediana, desvio padrão, correlação)

Os conceitos fundamentais da **estatística básica**, muito usados na análise de dados: **média, mediana, desvio padrão e correlação** — com explicações simples e exemplos.

---

## 📊 1. **Média (média aritmética)**

**O que é**:
É a soma dos valores dividida pelo número de elementos. Mostra o valor "central" de um conjunto.

**Fórmula**:

$$
\text{Média} = \frac{\text{soma dos valores}}{\text{número de valores}}
$$

**Exemplo**:

    Idades: 25, 30, 35, 40
    Média = (25 + 30 + 35 + 40) / 4 = **32,5**

---

## 📈 2. **Mediana**

**O que é**:
Valor que está no meio de um conjunto ordenado. Divide os dados ao meio.

**Exemplo 1 (números ímpares)**:

    Dados: 10, 20, 30
    Mediana = **20**

**Exemplo 2 (números pares)**:

    Dados: 10, 20, 30, 40
    Mediana = (20 + 30)/2 = **25**

👉 A **mediana** é menos sensível a valores extremos (outliers) que a média.

---

## 📉 3. **Desvio padrão**

**O que é**:
Mede o quanto os dados variam em relação à média. Quanto maior o desvio, mais espalhados estão os valores.

**Fórmula (simplificada)**:

$$
\sigma = \sqrt{\frac{\sum (x_i - \mu)^2}{n}}
$$

**Exemplo**:
    
    Se todos têm idade 30, o desvio padrão é **0** (sem variação).
    Se idades são 20, 30, 40, há variação, e o desvio é maior.

---

## 🔗 4. **Correlação (coeficiente de correlação de Pearson)**

**O que é**:
Mede a **relação linear** entre duas variáveis (por exemplo, idade e gasto mensal).

    Varia entre -1 e +1:

* **+1**: correlação perfeita positiva (aumenta junto)
* **0**: sem correlação
* **-1**: correlação perfeita negativa (um sobe, o outro desce)

**Exemplo**:

* Idade vs. gasto mensal → correlação = 0,8 → forte relação positiva

---

## 🐍 Exemplo em Python

Vamos calcular essas estatísticas usando `pandas` e `numpy`.

### 📄 Suponha o arquivo `clientes.csv`:

```csv
ID,Nome,Idade,Data de Compra
1,João,28,2025-05-21
2,Maria,34,2025-05-22
3,Carlos,40,2025-05-23
4,Ana,25,2025-05-24
```

### 🧮 Código em Python:

```python
import pandas as pd
import numpy as np

# Carregar os dados
df = pd.read_csv('clientes.csv')

# Estatísticas básicas
media = df['Idade'].mean()
mediana = df['Idade'].median()
desvio = df['Idade'].std()

print(f"Média: {media}")
print(f"Mediana: {mediana}")
print(f"Desvio padrão: {desvio}")
```

### Para calcular correlação (entre colunas numéricas):

```python
# Suponha que temos outra coluna 'Gasto Mensal'
df['Gasto Mensal'] = [200, 350, 400, 180]

# Correlação entre idade e gasto
correlacao = df[['Idade', 'Gasto Mensal']].corr()
print(correlacao)
```

---

