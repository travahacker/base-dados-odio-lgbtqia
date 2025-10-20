---
license: cc-by-nc-sa-4.0
language:
- pt
tags:
- hate-speech-detection
- lgbtqia
- portuguese
- dataset
short_description: Dataset para detecção de hate speech LGBTQIA+ em português
---

# 🏳️‍🌈 Base de Dados de Ódio LGBTQIA+

Dataset para detecção de hate speech contra pessoas LGBTQIA+ em português brasileiro com **regras contextuais** para proteger termos de dissidência de gênero.

## ✨ Funcionalidades

- **Dataset Binário**: Hate vs não-hate (expandido com ToLD-BR)
- **Dataset Especializado**: Transfobia vs Assédio/Insulto
- **Dataset Três Redes Sociais**: Instagram, TikTok e YouTube
- **Regras Contextuais**: Protege termos de gênero
- **Anotações Manuais**: Validadas por especialistas

## 📊 Estatísticas

- **Total de exemplos**: 4.780.095 (dataset binário expandido)
- **Dataset manual**: 2.053 exemplos
- **Dataset especializado**: 385.146 exemplos
- **Dataset ToLD-BR**: 1.942.521 exemplos
- **Dataset três redes sociais**: 12.102 exemplos

## 🎯 Regras Contextuais

### Proteção de Termos de Gênero
- **"boyceta"**: Detecta contexto positivo vs negativo
- **"sapatão"**: Protege identidade lésbica
- **"travesti"**: Respeita identidade trans

### Contextos Detectados
- **Positivo**: orgulho, beleza, identidade, expressão
- **Negativo**: nojo, escroto, desgraçado, arrombado
- **Educativo**: definição, conceito, explicação
- **Ridicularização**: engraçado, hilário, cômico

## 📁 Estrutura

```
datasets/
├── dataset_binary_expanded_with_toldbr.csv    # Dataset binário expandido
├── dataset_manual_final.csv                   # Dataset manual
├── dataset_specialized_final.csv              # Dataset especializado
├── dataset_toldbr_final.csv                  # Dataset ToLD-BR
├── dataset_obvious_hate.csv                  # Casos óbvios de hate
├── dataset_three_platforms_20251020_140406.csv    # Dataset três redes sociais
├── dataset_three_platforms_clean_20251020_140406.csv  # Dataset limpo
└── README_three_platforms_20251020_140406.md         # Documentação
```

## 🚀 Como Usar

```python
import pandas as pd

# Carregar dataset binário
df_binary = pd.read_csv("dataset_binary_expanded_with_toldbr.csv")

# Carregar dataset manual
df_manual = pd.read_csv("dataset_manual_final.csv")

# Carregar dataset especializado
df_specialized = pd.read_csv("dataset_specialized_final.csv")

# Carregar dataset três redes sociais
df_three_platforms = pd.read_csv("dataset_three_platforms_20251020_140406.csv")
```

## 📈 Melhorias Recentes

- ✅ Integração com ToLD-BR
- ✅ Regras contextuais implementadas
- ✅ Proteção de termos de dissidência de gênero
- ✅ Detecção de contexto positivo vs negativo
- ✅ Threshold adaptativo otimizado
- ✅ **NOVO**: Dataset com dados das três redes sociais (Instagram, TikTok, YouTube)

## 🔗 Links

- **Modelo**: [radar-social-lgbtqia](https://huggingface.co/Veronyka/radar-social-lgbtqia)
- **Space**: [radar-social-lgbtqia-space](https://huggingface.co/spaces/Veronyka/radar-social-lgbtqia-space)
- **Dataset HF**: [base-dados-odio-lgbtqia](https://huggingface.co/datasets/Veronyka/base-dados-odio-lgbtqia)

## ⚠️ Importante

Este dataset foi desenvolvido para proteger a comunidade LGBTQIA+ e detectar discurso de ódio. As regras contextuais garantem que termos de identidade de gênero sejam respeitados.

## 📊 Dataset Três Redes Sociais

O novo dataset inclui dados coletados de três redes sociais:
- **Instagram**: 2.098 comentários
- **TikTok**: 6.271 comentários  
- **YouTube**: 3.733 comentários

**Total**: 12.102 comentários consolidados para análise e treinamento de modelos.