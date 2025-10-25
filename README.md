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
df_tiktok = pd.read_csv('base-tiktok-separada-odio-lgbt.csv')
df_youtube = pd.read_csv('base-youtube-separada-odio-lgbt.csv')

print(f"Total de comentários gerais: {len(df_geral)}")
print(f"Total Instagram: {len(df_instagram)}")
print(f"Total TikTok: {len(df_tiktok)}")
print(f"Total YouTube: {len(df_youtube)}")
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
| TikTok | 6.271 |
| YouTube | 3.733 |

**Total único:** 12.102 comentários (consolidados das 3 plataformas)

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
- **GitHub do Projeto:** Código Não Binário

---

## ⚠️ Aviso Importante

Este dataset contém conteúdo sensível relacionado a discurso de ódio contra pessoas LGBTQIA+. Use com responsabilidade e sempre considere o impacto ético de suas aplicações.

**Objetivo:** Combater ódio, não propagá-lo.

---

**📅 Versão:** 2.0 - Processado em 25/10/2025  
**👤 Autor:** Veronyka Gimenes  
**🏳️‍🌈 Código Não Binário**