# Classificação de Textos com Representações Vetoriais

## 📋 Descrição

Notebook Jupyter completo para demonstração de técnicas de classificação de textos utilizando diferentes representações vetoriais (TF-IDF, BERT, Word2Vec, OpenAI) aplicadas a classificadores de machine learning.

**Baseado nos exercícios de 2024.2 com melhorias e atualizações para 2025.2**

## 🚀 Funcionalidades

### ✅ Implementadas

- **Processamento de dados**: Excel → CSV com limpeza automática
- **Pré-processamento**: Específico para português brasileiro
- **Representações vetoriais**: TF-IDF, Bag of Words, BERT, Word2Vec
- **Classificação**: Múltiplos algoritmos com validação cruzada
- **Visualizações**: PCA, t-SNE, matrizes de confusão
- **Persistência**: Banco SQLite com tabelas organizadas
- **OpenAI API**: Embeddings com LangChain e cache local
- **Comparações**: Análise detalhada de performance

### 📊 Estrutura do Banco de Dados

- `corpus_data` - Dados originais após limpeza
- `embeddings_tfidf` - Representações TF-IDF
- `embeddings_bow` - Representações Bag of Words
- `embeddings_bert` - Representações BERT
- `embeddings_word2vec` - Representações Word2Vec
- `embeddings_openai` - Representações OpenAI
- `classification_results` - Resultados de classificação
- `experiment_metadata` - Metadados dos experimentos

## 🛠️ Instalação

### 1. Instalar dependências

```bash
pip install -r requirements_complete.txt
```

### 2. Configurar OpenAI (opcional)

```bash
# Copiar arquivo de exemplo
cp env_example.txt .env

# Editar .env com sua chave da OpenAI
OPENAI_API_KEY=sua_chave_aqui
```

### 3. Baixar recursos do NLTK

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('rslp')
```

## 📁 Estrutura de Arquivos

```
codes/
├── aula.ipynb                    # Notebook principal
├── requirements_complete.txt     # Dependências
├── env_example.txt              # Exemplo de configuração
├── README.md                    # Este arquivo
├── database/                    # Banco SQLite
│   └── text_classification.db
└── corpus/                      # Dados de entrada
    ├── Base_dados_textos_6_classes.xlsx
    └── Base_dados_textos_6_classes_limpo.csv
```

## 🎯 Como Usar

### 1. Executar o notebook

```bash
jupyter notebook aula.ipynb
```

### 2. Executar células sequencialmente

- **Célula 0**: Introdução e conceitos fundamentais
- **Célula 1**: Inicialização do sistema e banco de dados
- **Célula 2**: Processamento Excel → CSV
- **Célula 3**: Importação de bibliotecas
- **Célula 4**: Pré-processamento de textos
- **Célula 5**: Geração de representações vetoriais
- **Célula 6**: Classificação e avaliação
- **Célula 7**: Visualizações avançadas
- **Célula 8**: Integração com OpenAI (opcional)
- **Célula 9**: Análise de resultados e consultas
- **Célula 10**: Conclusões e próximos passos

### 3. Consultar banco de dados

```python
# Estatísticas gerais
query_database()

# Melhores resultados
best_results = db_manager.get_best_results()
```

## 📊 Resultados Esperados

### Performance Típica

- **TF-IDF + SVM**: ~84% acurácia
- **BERT + SVM**: ~94% acurácia
- **OpenAI + SVM**: ~95% acurácia (estimado)

### Visualizações

- Gráficos de performance por embedding
- Heatmaps de acurácia
- Visualizações 2D (PCA, t-SNE)
- Análise de importância de palavras

## 🔧 Configurações

### Parâmetros Ajustáveis

- **TF-IDF**: `max_features`, `ngram_range`
- **BERT**: `model_name` (português)
- **OpenAI**: `model_name`, `batch_size`
- **Classificadores**: hiperparâmetros

### Cache e Persistência

- **SQLite**: Cache automático de embeddings
- **OpenAI**: Evita chamadas desnecessárias à API
- **Reutilização**: Dados salvos para experimentos futuros

## 📈 Interpretação dos Resultados

### Métricas Importantes

- **Acurácia**: % de predições corretas
- **F1-Score**: Balanceamento entre precision e recall
- **Separabilidade**: Distância entre classes (visualização 2D)

### Análise de Embeddings

- **TF-IDF**: Palavras mais discriminativas
- **BERT**: Captura contexto semântico
- **OpenAI**: Embeddings de última geração

## 🚨 Troubleshooting

### Problemas Comuns

1. **OpenAI não funciona**: Verificar chave API no .env
2. **BERT lento**: Usar GPU se disponível
3. **Memória insuficiente**: Reduzir batch_size
4. **Erro de encoding**: Verificar arquivo Excel

### Logs e Debug

- Verificar mensagens de erro nas células
- Consultar banco de dados para estatísticas
- Verificar arquivos de log (se habilitado)

## 📚 Conceitos Explicados

### Markdown Educativo

- Processamento de dados
- Pré-processamento de textos
- Representações vetoriais
- Classificação e avaliação
- Visualizações avançadas

### Interpretação de Resultados

- Explicações detalhadas nas saídas
- Análise de performance
- Comparações entre métodos
- Sugestões de melhorias

## 🔮 Próximos Passos

### Melhorias Sugeridas

1. **Fine-tuning** de BERT para domínio específico
2. **Ensemble methods** para melhor performance
3. **Otimização** de hiperparâmetros
4. **Integração** com mais APIs (Claude, Gemini)
5. **Pipeline** de produção com FastAPI

### Extensões

- Análise de sentimento
- Detecção de tópicos
- Classificação hierárquica
- Análise de bias e fairness

## 📞 Suporte

Para dúvidas ou problemas:

1. Verificar logs de erro
2. Consultar documentação das bibliotecas
3. Verificar configurações do ambiente
4. Testar com dataset menor

## 📄 Licença

Este projeto é para fins educacionais e de pesquisa.
