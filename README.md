---
language:
  - pt
tags:
  - portuguese
  - lgbtqia
  - hate-speech
  - hatespeech
  - ódio
  - transfobia
  - transphobia
license: mit
---

# Base de Dados de Ódio contra Pessoas LGBTQIA+ em Português (PT-BR)

Coleção de bases de dados para detecção de discurso de ódio contra pessoas LGBTQIA+ em português brasileiro.

## 📊 Bases Disponíveis

### 1. **base-geral-odio-lgbt.csv**
- **12.102 textos** de três plataformas (Instagram, TikTok, YouTube)
- **Coluna:** `text` (conteúdo dos comentários)
- **Uso:** Base principal para treinamento de modelos
- **Origem:** Comentários do podcast Entre Amigues

### 2. **base-instagram-separada-odio-lgbt.csv**
- **2.098 textos** do Instagram
- **Coluna:** `text` (conteúdo dos comentários)
- **Uso:** Análise específica do Instagram
- **Origem:** Comentários do podcast Entre Amigues no Instagram

### 3. **base-tiktok-separada-odio-lgbt.csv**
- **6.271 textos** do TikTok
- **Coluna:** `text` (conteúdo dos comentários)
- **Uso:** Análise específica do TikTok
- **Origem:** Comentários do podcast Entre Amigues no TikTok

### 4. **base-youtube-separada-odio-lgbt.csv**
- **3.733 textos** do YouTube
- **Coluna:** `text` (conteúdo dos comentários)
- **Uso:** Análise específica do YouTube
- **Origem:** Comentários do podcast Entre Amigues no YouTube

## 🎯 Objetivo

Fornecer dados de treinamento e validação para sistemas de detecção de discurso de ódio contra pessoas LGBTQIA+ em português brasileiro.

## 📢 Contexto Social

Este dataset foi criado a partir de uma **onda de ódio real** sofrida pelo podcast **Entre Amigues** da equipe **Código Não Binário**. Os dados foram coletados durante ataques coordenados nas redes sociais, especialmente no Instagram, onde comentários transfóbicos e de assédio foram direcionados ao podcast e sua audiência LGBTQIA+.

### Impacto Social

- **Podcast**: Entre Amigues (<https://linktr.ee/entre_amigues>) da Código Não Binário
- **Período**: Coleta durante onda de ódio coordenada
- **Redes Sociais**: Instagram, TikTok, YouTube
- **Anotadores**: Equipe especializada em direitos LGBTQIA+
- **Objetivo**: Documentar e combater discurso de ódio real

## 🚀 Como Usar

### Carregamento Simples

```python
import pandas as pd

# Base geral
df_geral = pd.read_csv('base-geral-odio-lgbt.csv')
print(f"Total de textos: {len(df_geral)}")

# Instagram
df_instagram = pd.read_csv('base-instagram-separada-odio-lgbt.csv')
print(f"Textos Instagram: {len(df_instagram)}")

# TikTok
df_tiktok = pd.read_csv('base-tiktok-separada-odio-lgbt.csv')
print(f"Textos TikTok: {len(df_tiktok)}")

# YouTube
df_youtube = pd.read_csv('base-youtube-separada-odio-lgbt.csv')
print(f"Textos YouTube: {len(df_youtube)}")
```

### Treinamento de Modelo

```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification

# Carregar dados
train_df = pd.read_csv('base-geral-odio-lgbt.csv')

# Preparar para treinamento
tokenizer = AutoTokenizer.from_pretrained("neuralmind/bert-base-portuguese-cased")
# ... código de treinamento
```

## 📈 Estatísticas

### Distribuição por Plataforma

- **Total**: 12.102 textos
- **Instagram**: 2.098 textos (17.3%)
- **TikTok**: 6.271 textos (51.8%)
- **YouTube**: 3.733 textos (30.9%)

### Modelo Treinado

Os dados foram utilizados para treinar o modelo **Veronyka/tupi-bert-lgbtqia-trained** com:
- **Performance**: 98.4% accuracy
- **Base**: Tupi-BERT-Large
- **Método**: Curriculum Learning + RLHF

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

## 📊 Qualidade dos Dados

### Anotações

- **Anotadores**: Especialistas em direitos LGBTQIA+
- **Consenso**: Validação cruzada entre anotadores
- **Origem**: Comentários reais de ódio coordenado

## 🤝 Contribuição

Para contribuir com este dataset:

1. Fork o repositório
2. Adicione novos dados (seguindo padrões de privacidade)
3. Valide anotações existentes
4. Submeta pull request

### Padrões de Qualidade

- Dados pessoais removidos
- Anotações consistentes
- Documentação completa
- Testes de validação

## 📄 Licença

MIT License

## 🔗 Links Relacionados

- **Modelo Treinado**: [Veronyka/tupi-bert-lgbtqia-trained](https://huggingface.co/Veronyka/tupi-bert-lgbtqia-trained)
- **Radar Social LGBTQIA+**: [Veronyka/radar-social-lgbtqia-v2](https://huggingface.co/spaces/Veronyka/radar-social-lgbtqia-v2)
- **Podcast Entre Amigues**: <https://linktr.ee/entre_amigues>

## ⚠️ Aviso Importante

Este dataset contém conteúdo sensível relacionado a discurso de ódio. Use com responsabilidade e sempre considere o impacto ético de suas aplicações.

## 📞 Contato

Para questões sobre o dataset ou colaborações, entre em contato através das issues do repositório.

---

**Desenvolvido por:** Veronyka Gimenes  
**Data:** Outubro 2025  
**License:** MIT