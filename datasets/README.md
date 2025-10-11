# Dataset Final - Bases Conforme Modelo Leu (CORRIGIDO)

Esta pasta contém **APENAS** as bases utilizadas no treinamento final, processadas exatamente como o modelo as leu.

## ⚠️ CORREÇÃO IMPORTANTE

**O dataset `lgbt_data.csv` NÃO foi utilizado no treinamento final** e foi removido desta pasta.

## Datasets Utilizados no Treinamento Final

### dataset_binary_final.csv
- **27.145 exemplos** de classificação binária (hate/não-hate)
- **Colunas**: `id`, `text`, `is_hate`
- **Uso**: Treinamento do modelo binário
- **Origem**: Combinação de anotações manuais + ToLD-BR + Anti-LGBT traduzido

### dataset_specialized_final.csv
- **3.609 exemplos** de classificação especializada
- **Colunas**: `text`, `class`
- **Classes**: `transfobia`, `assedio_insulto`
- **Uso**: Treinamento do modelo especializado
- **Origem**: Anotações manuais da equipe da Código Não Binário sobre ódio sofrido com o podcast Entre Amigues

## Datasets das Fontes Originais

### dataset_manual_source.csv
- **Anotações manuais** processadas
- **Colunas**: `id`, `text`, `is_hate`
- **Origem**: `Scrapping_insta_annotated_GLOBAL_REVISADO.csv`
- **Contexto**: Dados do Instagram coletados durante onda de ódio sofrida pelo podcast Entre Amigues

### dataset_toldbr_source.csv
- **ToLD-BR** processado
- **Colunas**: `text`, `is_hate`
- **Origem**: `ToLD-BR.csv`

### dataset_anti_lgbt_source.csv
- **Anti-LGBT traduzido** processado
- **Colunas**: `id`, `text`, `is_hate`
- **Origem**: `data/anti_lgbt_translated_pt_br_correct.csv`

## Processamento Aplicado

Todos os datasets foram processados com:
- Normalização de texto (URLs → [URL], @usuario → [MENTION], #hashtag → [HASHTAG])
- Remoção de textos muito curtos (< 3 caracteres)
- Remoção de dados pessoais identificáveis
- Preservação apenas do conteúdo linguístico

## Uso

Estes datasets representam **exatamente** o que o modelo 'vê' durante o treinamento, garantindo transparência e reprodutibilidade.

## ⚠️ Datasets NÃO Utilizados

- `lgbt_data.csv` - Dataset em inglês não integrado
- `export_1757023553205_limpa.csv` - Base limpa para aplicação, não treinamento

## 🔒 Privacidade

- Dados pessoais removidos durante processamento
- Apenas conteúdo linguístico preservado
- Conformidade com LGPD/GDPR
