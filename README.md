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
- **Regras Contextuais**: Protege termos de gênero
- **Anotações Manuais**: Validadas por especialistas

## 📊 Estatísticas

- **Total de exemplos**: 4.780.095 (dataset binário expandido)
- **Dataset manual**: 2.053 exemplos
- **Dataset especializado**: 385.146 exemplos
- **Dataset ToLD-BR**: 1.942.521 exemplos

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
└── dataset_obvious_hate.csv                  # Casos óbvios de hate
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
```

## 📈 Melhorias Recentes

- ✅ Integração com ToLD-BR
- ✅ Regras contextuais implementadas
- ✅ Proteção de termos de dissidência de gênero
- ✅ Detecção de contexto positivo vs negativo
- ✅ Threshold adaptativo otimizado

## 🔗 Links

- **Modelo**: [radar-social-lgbtqia](https://huggingface.co/Veronyka/radar-social-lgbtqia)
- **Space**: [radar-social-lgbtqia-space](https://huggingface.co/spaces/Veronyka/radar-social-lgbtqia-space)

## ⚠️ Importante

Este dataset foi desenvolvido para proteger a comunidade LGBTQIA+ e detectar discurso de ódio. As regras contextuais garantem que termos de identidade de gênero sejam respeitados.
