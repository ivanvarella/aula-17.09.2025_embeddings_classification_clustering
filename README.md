# Classificação de Textos com Representações Vetoriais

## _Demonstração Prática - PPGEP9002 - 2025.2_

## 📋 Descrição

Notebook Jupyter completo para demonstração de técnicas de classificação de textos utilizando diferentes representações vetoriais (TF-IDF, BERT, Sentence Transformers, OpenAI) aplicadas a classificadores de machine learning.

**🔧 Versão Atualizada 2025.2:**

- Substituição de Gensim por Sentence Transformers para melhor compatibilidade
- Código mais organizado e didático com explicações completas
- Cálculo preciso de custos OpenAI com tiktoken
- Validação automática de integridade dos dados
- Explicações educativas detalhadas para todos os conceitos

## 🚀 Funcionalidades

### ✅ Implementadas

- **Processamento de dados**: Excel → CSV com limpeza automática
- **Pré-processamento**: Específico para português brasileiro com NLTK
- **Representações vetoriais**: TF-IDF, Bag of Words, BERT, Sentence Transformers, OpenAI
- **Classificação**: 5 algoritmos com validação e explicações didáticas
- **Visualizações**: PCA, t-SNE, matrizes de confusão, análise de separabilidade
- **Persistência**: Banco SQLite com validação automática de integridade
- **OpenAI API**: Embeddings com cálculo preciso de custos via tiktoken
- **Análise de custos**: Cálculo detalhado e estratégias de otimização
- **Explicações didáticas**: Conceitos, interpretação de resultados e guias práticos

### 📊 Estrutura do Banco de Dados

- `corpus_data` - Dados originais após limpeza
- `embeddings_tfidf` - Representações TF-IDF
- `embeddings_bow` - Representações Bag of Words
- `embeddings_bert` - Representações BERT
- `embeddings_sentence_transformer` - Representações Sentence Transformers
- `embeddings_openai` - Representações OpenAI
- `classification_results` - Resultados de classificação
- `experiment_metadata` - Metadados dos experimentos

## 🛠️ Instalação

### 1. Instalar dependências com uv (recomendado)

```bash
uv add pandas numpy matplotlib seaborn scikit-learn nltk openpyxl transformers torch sentence-transformers openai langchain langchain-openai python-dotenv scipy tiktoken
```

### 2. Instalar dependências com pip (alternativo)

```bash
pip install pandas numpy matplotlib seaborn scikit-learn nltk openpyxl transformers torch sentence-transformers openai langchain langchain-openai python-dotenv scipy tiktoken
```

### 3. Configurar OpenAI (opcional)

```bash
# Criar arquivo .env
echo "OPENAI_API_KEY=sua_chave_aqui" > .env
```

### 4. Baixar recursos do NLTK

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('rslp')
```

## 📁 Estrutura de Arquivos

```
codes/
├── aula_openai.ipynb              # Notebook principal atualizado
├── requirements.txt               # Dependências básicas
├── README.md                     # Este arquivo
├── database/                     # Banco SQLite
│   └── text_classification.db
└── corpus/                       # Dados de entrada
    ├── Base_dados_textos_6_classes.xlsx
    └── Base_dados_textos_6_classes_limpo.csv
```

## 🎯 Como Usar

### 1. Executar o notebook

```bash
jupyter notebook aula_openai.ipynb
```

### 2. Executar células sequencialmente

- **Célula 0**: Introdução e conceitos fundamentais
- **Célula 1**: Inicialização do sistema e banco de dados
- **Célula 2**: Processamento Excel → CSV com validação
- **Célula 3**: Importação de bibliotecas e configuração
- **Célula 4**: Pré-processamento de textos em português
- **Célula 5**: Geração de representações vetoriais com explicações
- **Célula 6**: Classificação e avaliação com métricas detalhadas
- **Célula 7**: Visualizações avançadas e análise de separabilidade
- **Célula 8**: Integração com OpenAI e análise de custos
- **Célula 9**: Análise de resultados e consultas ao banco
- **Célula 10**: Conclusões e próximos passos

### 3. Consultar banco de dados

```python
# Estatísticas gerais com validação
query_database()

# Melhores resultados
best_results = get_best_results()

# Validação de integridade
db_manager.validate_data_integrity()
```

## 📊 Resultados Esperados

### Performance Típica

- **TF-IDF + Logistic Regression**: ~89% acurácia
- **Bag of Words + Naive Bayes**: ~89% acurácia
- **BERT + SVM**: ~81% acurácia
- **Sentence Transformers + SVM**: ~85% acurácia (estimado)
- **OpenAI + Logistic Regression**: ~95% acurácia

### Visualizações e Análises

- Gráficos de performance por embedding e classificador
- Visualizações 2D (PCA, t-SNE) para cada tipo de embedding
- Análise de separabilidade das classes
- Análise de importância de palavras (TF-IDF)
- Matrizes de confusão para diferentes modelos
- Análise de custos OpenAI detalhada

## 🔧 Configurações

### Parâmetros Ajustáveis

- **TF-IDF**: `max_features=5000`, `ngram_range=(1,2)`
- **Bag of Words**: `max_features=5000`, `ngram_range=(1,2)`
- **BERT**: `model_name='neuralmind/bert-base-portuguese-cased'`
- **Sentence Transformers**: `model_name='sentence-transformers/paraphrase-multilingual-mpnet-base-v2'`
- **OpenAI**: `model="text-embedding-3-small"`, `batch_size=100`
- **Classificadores**: hiperparâmetros otimizados

### Cache e Persistência

- **SQLite**: Cache automático de embeddings com validação
- **OpenAI**: Evita chamadas desnecessárias à API
- **Validação**: Verificação automática de integridade dos dados
- **Reutilização**: Dados salvos para experimentos futuros

## 📈 Interpretação dos Resultados

### Métricas Explicadas

- **Acurácia**: Proporção de predições corretas

  - > 90%: Excelente para classificação de texto
  - 80-90%: Muito bom, adequado para produção
  - 70-80%: Bom, mas pode ser melhorado
  - <70%: Precisa de melhorias significativas

- **F1-Score**: Balanceamento entre precisão e recall

  - Fórmula: 2 × (Precisão × Recall) / (Precisão + Recall)
  - Valores próximos indicam modelo equilibrado

- **Separabilidade**: Distância entre centroides das classes
  - <1.0: Baixa separabilidade (classes próximas)
  - 1.0-3.0: Separação moderada
  - > 3.0: Alta separabilidade (classes bem separadas)

### Análise de Embeddings

- **TF-IDF**: Interpretável, rápido, ideal para baseline
- **Bag of Words**: Simples, funciona bem com Naive Bayes
- **BERT**: Captura contexto semântico, estado da arte
- **Sentence Transformers**: Balanceia qualidade e eficiência
- **OpenAI**: Embeddings de última geração, custo controlado

### Análise de Custos OpenAI

- **Cálculo preciso**: Usando tiktoken para contagem exata de tokens
- **Preços atuais**: $0.00002 por 1.000 tokens (dez/2024)
- **Estratégias de otimização**: Cache, processamento em lotes, modelos locais

## 🚨 Troubleshooting

### Problemas Comuns

1. **Tabela não existe**: Executar células de inicialização do banco
2. **OpenAI não funciona**: Verificar chave API no .env
3. **Naive Bayes com valores negativos**: Aplicação automática de transformação
4. **Warning tokenizers**: Configuração automática de paralelismo
5. **Memória insuficiente**: Reduzir batch_size ou usar embeddings menores

### Logs e Debug

- Verificar mensagens de erro nas células
- Consultar banco de dados para estatísticas
- Usar validação de integridade: `db_manager.validate_data_integrity()`
- Verificar configurações de ambiente

## 📚 Conceitos Explicados

### Explicações Didáticas Incluídas

- **O que são embeddings**: Representações numéricas de textos
- **Tipos de embeddings**: TF-IDF, BoW, BERT, Sentence Transformers, OpenAI
- **Algoritmos de classificação**: Naive Bayes, SVM, Random Forest, Logistic Regression, KNN
- **Métricas de avaliação**: Acurácia, precisão, recall, F1-score
- **Análise de separabilidade**: Como medir distância entre classes
- **Cálculo de custos**: Tokens, preços, estratégias de otimização
- **Interpretação de resultados**: O que cada métrica significa na prática

### Guias Práticos

- **Escolha de embeddings**: Quando usar cada tipo
- **Seleção de classificadores**: Vantagens e desvantagens
- **Otimização de custos**: Estratégias para reduzir gastos
- **Próximos passos**: Sugestões baseadas nos resultados

## 🔮 Próximos Passos

### Melhorias Sugeridas

1. **Fine-tuning** de BERT para domínio específico
2. **Ensemble methods** para melhor performance
3. **Otimização** de hiperparâmetros com GridSearch
4. **Integração** com mais APIs (Claude, Gemini)
5. **Pipeline** de produção com FastAPI
6. **Teste** com outros modelos de Sentence Transformers

### Extensões

- Análise de sentimento
- Detecção de tópicos
- Classificação hierárquica
- Análise de bias e fairness
- Implementação de técnicas de balanceamento de classes

## 🆕 Atualizações da Versão 2025.2

### Principais Mudanças

- **Gensim → Sentence Transformers**: Melhor compatibilidade com Python 3.12+
- **Cálculo preciso de custos**: Implementação com tiktoken
- **Validação de dados**: Verificação automática de integridade
- **Explicações didáticas**: Conceitos explicados de forma educativa
- **Tratamento de erros**: Correção de problemas comuns
- **Interface melhorada**: Saídas mais claras e informativas

### Bibliotecas Atualizadas

- `sentence-transformers`: Substitui gensim
- `tiktoken`: Para cálculo preciso de tokens OpenAI
- `transformers`: Versão atualizada
- `torch`: Backend para transformers
- `langchain`: Framework para LLMs

## 📞 Suporte

Para dúvidas ou problemas:

1. Verificar logs de erro nas células
2. Consultar explicações didáticas no notebook
3. Usar validação de integridade do banco
4. Verificar configurações do ambiente
5. Testar com dataset menor se necessário

## 📄 Licença

Este projeto é para fins educacionais e de pesquisa.

---

_Notebook desenvolvido para demonstração em aula - PPGEP9002 - Inteligência Computacional para Engenharia de Produção - 2025.2_

**🔧 Versão Atualizada:** Substituição de Gensim por Sentence Transformers para melhor compatibilidade e performance.
