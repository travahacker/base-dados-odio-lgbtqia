---
license: mit
language:
- pt
tags:
- hate-speech-detection
- lgbtqia
- portuguese
- cyberbullying
- social-media
size_categories:
- 10K<n<100K
task_categories:
- text-classification
- text-retrieval
---

# Base de Dados de Ódio contra Pessoas LGBTQIA+ em Português (PT-BR)

Coleção de datasets para detecção de discurso de ódio contra pessoas LGBTQIA+ em português brasileiro.

## 🎯 Objetivo

Fornecer dados de treinamento e validação para sistemas de detecção de discurso de ódio contra pessoas LGBTQIA+ em português brasileiro.

## 📢 Contexto Social

Este dataset foi criado a partir de uma **onda de ódio real** sofrida pelo podcast **Entre Amigues** da equipe **Código Não Binário**. Os dados foram coletados durante ataques coordenados nas redes sociais, especialmente no Instagram, onde comentários transfóbicos e de assédio foram direcionados ao podcast e sua audiência LGBTQIA+.

### Impacto Social
- **Podcast**: Entre Amigues (Código Não Binário)
- **Período**: Coleta durante onda de ódio coordenada
- **Rede Social**: Instagram (principal fonte)
- **Anotadores**: Equipe especializada em direitos LGBTQIA+
- **Objetivo**: Documentar e combater discurso de ódio real

## 📊 Datasets Incluídos

### Datasets Processados (Conforme Modelo Leu)

#### `datasets/dataset_binary_final.csv`
- **27.145 exemplos** de classificação binária (hate/não-hate)
- **Colunas**: `id`, `text`, `is_hate`
- **Uso**: Treinamento de modelo binário

#### `datasets/dataset_specialized_final.csv`
- **3.609 exemplos** de classificação especializada
- **Colunas**: `text`, `class`
- **Classes**: `transfobia`, `assedio_insulto`
- **Uso**: Treinamento de modelo especializado
- **Origem**: Anotações manuais da equipe da Código Não Binário sobre ódio sofrido com o podcast Entre Amigues

#### `datasets/dataset_manual_final.csv`
- **2.053 exemplos** de anotações manuais
- **Colunas**: `id`, `text`, `is_hate`
- **Uso**: Validação e fine-tuning

#### `datasets/dataset_toldbr_final.csv`
- **21.000 exemplos** do ToLD-BR processado
- **Colunas**: `text`, `is_hate`
- **Uso**: Dados de treinamento

#### `datasets/dataset_anti_lgbt_final.csv`
- **4.299 exemplos** traduzidos do inglês
- **Colunas**: `id`, `text`, `is_hate`
- **Uso**: Dados de treinamento

### Datasets das Fontes Originais

#### `datasets/dataset_manual_source.csv`
- **Anotações manuais** processadas
- **Colunas**: `id`, `text`, `is_hate`
- **Origem**: `Scrapping_insta_annotated_GLOBAL_REVISADO.csv`
- **Contexto**: Dados do Instagram coletados durante onda de ódio sofrida pelo podcast Entre Amigues

#### `datasets_originais/anti-lgbt-cyberbullying.csv`
- Dataset original em inglês (4.300 exemplos)
- Traduzido para português brasileiro

#### `datasets_originais/told-br.csv`
- Dataset ToLD-BR original (21.000 exemplos)
- Anotações em português brasileiro

## 🔒 Privacidade e Ética

### Medidas de Privacidade
- **Dados pessoais removidos**: Nomes de usuário, IDs, URLs
- **Anonimização**: IDs substituídos por hashes
- **Normalização**: Menções (@usuario) → [MENTION]
- **Conformidade**: LGPD/GDPR compliant

### Processamento Aplicado
- URLs → `[URL]`
- @usuario → `[MENTION]`
- #hashtag → `[HASHTAG]`
- Remoção de textos < 3 caracteres
- Preservação apenas do conteúdo linguístico

## 📈 Estatísticas

### Distribuição por Dataset
- **Total de exemplos**: ~60.000
- **Hate speech**: ~15.000 (25%)
- **Não-hate**: ~45.000 (75%)

### Distribuição por Classe Especializada
- **Transfobia**: ~400 exemplos
- **Assédio/Insulto**: ~3.400 exemplos

## 🚀 Uso

### Carregamento Simples
```python
import pandas as pd

# Dataset binário
df_binary = pd.read_csv('datasets/dataset_binary_final.csv')

# Dataset especializado
df_specialized = pd.read_csv('datasets/dataset_specialized_final.csv')

print(f"Exemplos binários: {len(df_binary)}")
print(f"Exemplos especializados: {len(df_specialized)}")
```

### Treinamento de Modelo
```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification

# Carregar dados
train_df = pd.read_csv('datasets/dataset_binary_final.csv')

# Preparar para treinamento
tokenizer = AutoTokenizer.from_pretrained("neuralmind/bert-base-portuguese-cased")
# ... código de treinamento
```

## 📊 Qualidade dos Dados

### Anotações Manuais
- **Anotadores**: Especialistas em direitos LGBTQIA+
- **Consenso**: Validação cruzada entre anotadores
- **Cobertura**: 10+ classes especializadas

### Validação
- **Consistência**: Verificação de padrões
- **Bias**: Análise de viés e estereótipos
- **Diversidade**: Representação de diferentes contextos

## 📊 Fontes dos Datasets Utilizados

### Modelos Base
- **BERTimbau**: https://hf.co/neuralmind/bert-base-portuguese-cased
- **Helsinki-NLP Translation**: https://hf.co/Helsinki-NLP/opus-mt-tc-big-en-pt

### Datasets Externos
- **ToLD-BR**: https://github.com/joaoaleite/ToLD-Br/
- **Anti-LGBT Cyberbullying**: https://www.kaggle.com/datasets/kw5454331/anti-lgbt-cyberbullying-texts/data

### Dataset de Treinamento do BERTimbau
- **HateBR**: https://hf.co/datasets/ruanchaves/hatebr (excluído por data leakage)

### Contexto Social
- **Dados manuais**: Anotações da equipe Código Não Binário sobre o podcast Entre Amigues
- **ToLD-BR**: Dataset brasileiro de toxicidade (GitHub)
- **Anti-LGBT**: Dataset inglês traduzido para PT-BR (Kaggle)

## 🤝 Contribuição

### Como Contribuir
1. Fork o repositório
2. Adicione novos datasets (seguindo padrões de privacidade)
3. Valide anotações existentes
4. Submeta pull request

### Padrões de Qualidade
- Dados pessoais removidos
- Anotações consistentes
- Documentação completa
- Testes de validação

## 📄 Licença

MIT License - Veja LICENSE para detalhes.

## 🔗 Links Relacionados

- [Radar Social LGBTQIA+](https://github.com/travahacker/radar-social-lgbtqia)
- [Hugging Face Model](https://hf.co/Veronyka/radar-social-lgbtqia)

## ⚠️ Aviso Importante

Este dataset contém conteúdo sensível relacionado a discurso de ódio. Use com responsabilidade e sempre considere o impacto ético de suas aplicações.

## 📞 Contato

Para questões sobre o dataset ou colaborações, entre em contato através das issues do repositório.