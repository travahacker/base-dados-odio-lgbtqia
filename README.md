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

Dataset para detecção de hate speech contra pessoas LGBTQIA+ em português brasileiro, contendo comentários coletados de três redes sociais.

## 🎯 Objetivo

Fornecer bases de dados limpas e organizadas de comentários de ódio contra pessoas LGBTQIA+ em português brasileiro, prontas para uso por pesquisadores e desenvolvedores.

## 📊 Datasets Incluídos

### 📱 **base-geral-odio-lgbt.csv**
- **Total:** 12.102 registros
- **Plataformas:** Instagram, TikTok, YouTube
- **Conteúdo:** Comentários coletados durante onda de ódio contra o podcast Entre Amigues
- **Estrutura:** Apenas coluna `text` (comentários limpos)
- **Formato:** CSV com delimitador vírgula, encoding UTF-8

### 📸 **base-instagram-separada-odio-lgbt.csv**
- **Total:** 2.098 registros
- **Fonte:** Comentários do Instagram coletados durante ataques ao podcast
- **Estrutura:** Apenas coluna `text`
- **Formato:** CSV com delimitador vírgula, encoding UTF-8

### 📸 **base-instagram-separada-odio-lgbt-anotada.csv** ⭐ NOVO - COMPLETA
- **Total:** 1.891 registros (962 positivo, 703 ódio, 226 neutro)
- **Fonte:** Comentários do Instagram com anotações manuais detalhadas
- **Formato:** CSV com delimitador ponto-e-vírgula (;), encoding UTF-8
- **Diferencial:** Única base com classificação manual e categorização detalhada

**Colunas de Metadados:**
- `id`: ID do comentário
- `Comment Text`: Texto do comentário
- `Comment Date`: Data do comentário
- `Comment Likes`: Número de curtidas
- `Has Replies`: Possui respostas (Sim/Não)
- `Reply Count`: Número de respostas
- `avaliacao`: Classificação geral (positivo/neutro/odio)
- `has_emoji`: Possui emoji (0/1)

**Colunas de Categorização de Ódio (0/1):**
- `assedio_insulto`: Assédio e insulto
- `ameaca_incitacao`: Ameaça e incitação
- `patologizacao_pseudociencia`: Patologização e pseudociência
- `transfobia`: Transfobia
- `homofobia`: Homofobia
- `lesbofobia`: Lesbofobia
- `bifobia`: Bifobia
- `intersexofobia`: Intersexofobia
- `lgbtfobia`: LGBTfobia geral
- `racismo`: Racismo
- `gordofobia`: Gordofobia
- `intolerancia_religiosa`: Intolerância religiosa
- `misgendering_deadnaming`: Misgendering e deadnaming
- `desumanizacao_animalizacao`: Desumanização e animalização
- `sexualizacao_assedio_sexual`: Sexualização e assédio sexual
- `panico_moral_criancas`: Pânico moral sobre crianças
- `desinformacao_genero`: Desinformação sobre gênero

**Colunas de Análise de Emoji (0/1):**
- `emoji_negacao_identidade`: Emoji de negação de identidade
- `emoji_violencia`: Emoji de violência
- `emoji_desumanizacao`: Emoji de desumanização
- `emoji_morte`: Emoji de morte
- `emoji_zombaria`: Emoji de zombaria
- `emoji_positivo`: Emoji positivo

**Colunas Adicionais:**
- `dm_link`: Link para mensagem direta
- `severidade_global`: Nível de severidade (0-2)

Esta é a **única base com categorização detalhada manual**, permitindo análise granular dos tipos de discurso de ódio.

### 📸 **base-instagram-separada-odio-lgbt-aumentada.csv** 🤖 EXPANDIDA
- **Total:** 5.133 registros (variáveis por rastreamento)
- **Fonte:** Base Instagram expandida via Self-Instruct para treinamento de modelo
- **Formato:** CSV com delimitador vírgula, encoding UTF-8
- **Diferencial:** Base expandida usando técnicas de data augmentation

**Colunas:**
- `text`: Texto do comentário
- `is_hate`: Classificação binária (0=não-hate, 1=hate)
- `source`: Origem do registro (original/augmented)

**Técnicas de Expansão Aplicadas (Self-Instruct):**
- **Paráfrases:** Variações de pontuação, maiúsculas/minúsculas, espaçamento
- **Substituição de emojis:** 😂→😆, 🤣→😂, ❤️→💕, etc.
- **Variações de termos LGBTQIA+:** 'gay'→'homossexual', 'lésbica'→'sapatão', 'trans'→'transgênero'
- **Substituição de termos ofensivos:** Variações ortográficas (ex: 'viado'→'veado')
- **Geração de sinônimos:** Sinônimos contextuais para intensificar/atenuar
- **Variações de contexto:** Adição de intensificadores (hate) ou contexto positivo (não-hate)

**Objetivo:** Esta base foi criada especificamente para o **treinamento do modelo Tupi-BERT-Large** (fine-tuning), expandindo a base original de ~2.098 para ~5.133 exemplos para melhor performance em classificação binária (hate/não-hate).

**Uso:** Ideal para treinamento de modelos de classificação binária de hate speech.

### 🎵 **base-tiktok-separada-odio-lgbt.csv**
- **Total:** 6.271 registros
- **Fonte:** Comentários do TikTok relacionados a conteúdo LGBTQIA+
- **Estrutura:** Apenas coluna `text`
- **Formato:** CSV com delimitador vírgula, encoding UTF-8

### 📹 **base-youtube-separada-odio-lgbt.csv**
- **Total:** 3.733 registros
- **Fonte:** Comentários do YouTube em vídeos LGBTQIA+
- **Estrutura:** Apenas coluna `text`
- **Formato:** CSV com delimitador vírgula, encoding UTF-8

---

## 📢 Contexto Social

Estes dados foram coletados durante uma **onda de ódio coordenada** contra o podcast **Entre Amigues** da equipe **Código Não Binário**. Os comentários representam discurso real de ódio dirigido à comunidade LGBTQIA+.

**Podcast:** Entre Amigues - https://linktr.ee/entre_amigues  
**Equipe:** Código Não Binário  
**Período:** Coleta realizada durante ataques coordenados  
**Anotação:** Manual por especialistas em direitos LGBTQIA+

---

## 📁 Estrutura dos Arquivos

Todos os CSVs seguem o formato:

```csv
text
"Comentário de ódio exemplo..."
"Outro comentário..."
```

- **Delimitador:** Vírgula (,)
- **Encoding:** UTF-8
- **Aspas:** Textos entre aspas duplas para evitar problemas com vírgulas
- **Sem índices:** Coluna de ID removida para focar apenas no texto

---

## 🚀 Como Usar

### Python (Pandas)

```python
import pandas as pd

# Carregar base geral
df_geral = pd.read_csv('base-geral-odio-lgbt.csv')

# Carregar base por plataforma
df_instagram = pd.read_csv('base-instagram-separada-odio-lgbt.csv')
df_instagram_anotada = pd.read_csv('base-instagram-separada-odio-lgbt-anotada.csv', sep=';')  # ⭐ COMPLETA
df_instagram_aumentada = pd.read_csv('base-instagram-separada-odio-lgbt-aumentada.csv')  # 🤖 EXPANDIDA
df_tiktok = pd.read_csv('base-tiktok-separada-odio-lgbt.csv')
df_youtube = pd.read_csv('base-youtube-separada-odio-lgbt.csv')

print(f"Total de comentários gerais: {len(df_geral)}")
print(f"Total Instagram: {len(df_instagram)}")
print(f"Total Instagram ANOTADA: {len(df_instagram_anotada)} (com labels e categorização detalhada)")
print(f"Total Instagram AUMENTADA: {len(df_instagram_aumentada)} (para treinamento)")
print(f"Total TikTok: {len(df_tiktok)}")
print(f"Total YouTube: {len(df_youtube)}")

# Análise da base anotada
print(f"\nDistribuição na base anotada:")
print(df_instagram_anotada['avaliacao'].value_counts())

# Análise detalhada de categorias de ódio
print(f"\nCategorias de ódio mais frequentes:")
categorias = ['transfobia', 'homofobia', 'lesbofobia', 'lgbtfobia', 'assedio_insulto']
for cat in categorias:
    if cat in df_instagram_anotada.columns:
        count = df_instagram_anotada[cat].sum()
        print(f"  {cat}: {count} ocorrências")
```

### Python (Hugging Face Datasets)

```python
from datasets import load_dataset

# Carregar do Hugging Face
dataset = load_dataset("Veronyka/base-dados-odio-lgbtqia")
```

---

## 📈 Estatísticas

| Dataset | Total de Registros |
|---------|-------------------|
| Geral (3 plataformas) | 12.102 |
| Instagram | 2.098 |
| Instagram Anotada ⭐ | 1.891 |
| Instagram Aumentada 🤖 | 5.133 |
| TikTok | 6.271 |
| YouTube | 3.733 |

**Total único:** 12.102 comentários (consolidados das 3 plataformas)  
**Base anotada:** 1.891 comentários com classificação manual validada  
**Base aumentada:** 5.133 comentários para treinamento (Self-Instruct)

---

## 🔒 Privacidade e Ética

- ✅ **Dados pessoais removidos**: IDs, nomes de usuários, URLs
- ✅ **Anonimização**: Identificadores substituídos
- ✅ **Conformidade LGPD**: Dados processados conforme legislação brasileira
- ✅ **Uso responsável**: Apenas para pesquisa e combate ao ódio

### Processamento Aplicado

- URLs → `[URL]`
- @usuario → `[MENTION]`
- #hashtag → `[HASHTAG]`
- Remoção de textos < 3 caracteres
- Normalização de espaços em branco

---

## 🤝 Contribuição

Para contribuir com novos dados ou melhorias:

1. Faça um fork do repositório
2. Adicione seus dados seguindo o padrão (apenas coluna `text`)
3. Valide que não contém dados pessoais
4. Submeta um pull request

---

## 📄 Licença

cc-by-nc-sa-4.0 - Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International

---

## 🔗 Links Relacionados

- **Modelo treinado:** [tupi-bert-lgbtqia-trained](https://huggingface.co/Veronyka/tupi-bert-lgbtqia-trained)
- **Space de análise:** [radar-social-lgbtqia-v2](https://huggingface.co/spaces/Veronyka/radar-social-lgbtqia-v2)

---

## ⚠️ Aviso Importante

Este dataset contém conteúdo sensível relacionado a discurso de ódio contra pessoas LGBTQIA+. Use com responsabilidade e sempre considere o impacto ético de suas aplicações.

**Objetivo:** Combater ódio, não propagá-lo.

---

**📅 Versão:** 2.0 - Processado em 25/10/2025  
**👤 Autor:** Veronyka Gimenes  
**🏳️‍🌈 Código Não Binário**