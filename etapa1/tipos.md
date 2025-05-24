# Tipos de dados: estruturados vs. não estruturados

Diferenciar de forma clara os **tipos de dados: estruturados vs. não estruturados**, que são fundamentais na análise de dados e ciência de dados.


### 📦 **1. Dados Estruturados**

**Definição**:
São dados organizados em um formato fixo e padronizado, geralmente em **linhas e colunas**, como em **tabelas de banco de dados relacionais** (MySQL, PostgreSQL, Excel, etc.).

**Características**:

* Fácil de armazenar e consultar com SQL.
* Dados numéricos ou categóricos (ex: nomes, datas, valores, IDs).
* Alta organização e consistência.

**Exemplos**:

| ID | Nome  | Idade | Data de Compra |
| -- | ----- | ----- | -------------- |
| 1  | João  | 28    | 2025-05-21     |
| 2  | Maria | 34    | 2025-05-22     |

**Onde é usado**:

* Bancos de dados empresariais
* Planilhas de vendas, RH, finanças
* Sistemas de ERP ou CRM

Exemplo: [Arquivo CSV](./arquivo.csv)

---

### 🌐 **2. Dados Não Estruturados**

**Definição**:
São dados que **não seguem um modelo ou estrutura predefinida**. São geralmente mais difíceis de organizar e analisar diretamente, mas representam a **maior parte dos dados no mundo**.

**Características**:

* Não cabem naturalmente em tabelas.
* Precisam de ferramentas avançadas para análise (IA, NLP, etc.).
* Mais ricos em informação subjetiva e contextual.

**Exemplos**:

* Texto livre (e-mails, comentários, reviews)
* Imagens e vídeos
* Áudio e gravações de chamadas
* PDFs, apresentações
* Publicações em redes sociais

**Onde é usado**:

* Análise de sentimento (redes sociais, feedback)
* Reconhecimento de imagem e voz
* Processamento de linguagem natural (NLP)

---

### ⚖️ **Resumo comparativo**

| Aspecto               | Estruturado                | Não Estruturado                        |
| --------------------- | -------------------------- | -------------------------------------- |
| Formato               | Tabelas (linhas e colunas) | Livre (texto, imagem, etc.)            |
| Armazenamento         | SQL, Excel                 | NoSQL, Hadoop, sistemas de arquivos    |
| Facilidade de análise | Alta                       | Baixa (requer processamento)           |
| Exemplo               | Planilha de vendas         | Comentário de cliente em redes sociais |

---

## Ferramentas que lidam com esses tipos de dados

1. ✅ **Exemplo em Python** com análise de sentimentos automatizada usando bibliotecas de NLP (como `TextBlob` ou `NLTK`)
2. 📊 **Análise em Power BI ou Excel**, simulando como fazer isso manualmente ou com recursos de IA
3. 🌐 **Ferramentas online**, como Google Sheets com complementos de IA

## Um exemplo simples de **análise de sentimentos em Python** usando a biblioteca `TextBlob`, que é fácil de usar e ótima para começar com NLP.

### 💡 O que o exemplo faz:

* Recebe uma lista de comentários de clientes
* Limpa e processa os textos
* Usa o `TextBlob` para analisar o **sentimento** de cada comentário
* Classifica como **positivo**, **negativo** ou **neutro**

---

### 🐍 Exemplo em Python

Você pode colar este código em um Jupyter Notebook ou script Python local:

```python
from textblob import TextBlob

# Lista de comentários dos clientes
comentarios = [
    "A qualidade do som é excelente, mas a bateria poderia durar mais.",
    "Produto péssimo. Parou de funcionar em uma semana.",
    "Muito confortável, uso por horas sem incômodo. A bateria dura bem!",
    "Demorou para chegar, mas funciona perfeitamente.",
    "Som muito fraco e não conecta direito com o celular."
]

# Função para classificar sentimento
def classificar_sentimento(texto):
    blob = TextBlob(texto)
    polaridade = blob.sentiment.polarity
    if polaridade > 0:
        return "Positivo"
    elif polaridade < 0:
        return "Negativo"
    else:
        return "Neutro"

# Analisando todos os comentários
for comentario in comentarios:
    sentimento = classificar_sentimento(comentario)
    print(f"Comentário: {comentario}\n→ Sentimento: {sentimento}\n")
```

---

### ✅ Saída esperada:

```
Comentário: A qualidade do som é excelente, mas a bateria poderia durar mais.
→ Sentimento: Neutro

Comentário: Produto péssimo. Parou de funcionar em uma semana.
→ Sentimento: Negativo

Comentário: Muito confortável, uso por horas sem incômodo. A bateria dura bem!
→ Sentimento: Positivo

Comentário: Demorou para chegar, mas funciona perfeitamente.
→ Sentimento: Positivo

Comentário: Som muito fraco e não conecta direito com o celular.
→ Sentimento: Negativo
```

---

### 🛠️ Instalação (se ainda não tiver o TextBlob):

No terminal ou Jupyter:

```bash
pip install textblob
python -m textblob.download_corpora
```

Exemplo: [Comentários](./comentarios.ipynb)