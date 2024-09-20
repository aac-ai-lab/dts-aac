# Processo de Criação do Dataset

### 1. Coleta de Dados
- O dataset é criado a partir de arquivos .cha localizados no diretório BASE_DIR.
- Os arquivos são processados recursivamente, incluindo subdiretórios.

### 2. Extração de Frases
- O código extrai frases das crianças, identificadas pela tag '*CHI:' no início da linha.
- A idade da criança é extraída das linhas que começam com '@ID:' e contêm '|CHI|'.

### 3. Limpeza e Pré-processamento
- Remoção de prefixos identificadores e referências numéricas no final das frases.
- Remoção de caracteres especiais e pontuações, exceto apóstrofos.
- Remoção de palavras sem sentido e stopwords personalizadas.

### 4. Filtragem
- Frases com menos de 3 palavras são descartadas.
- Utiliza-se o spaCy para processamento de linguagem natural.

### 5. Criação de Versão Telegráfica
- Conversão das frases para versão telegráfica, mantendo palavras de conteúdo (substantivos, verbos, adjetivos, advérbios) e palavras funcionais essenciais para AAC.
- Remoção de palavras duplicadas consecutivas.

### 6. Cálculo de Métricas de Complexidade
- Métricas calculadas para a frase original, filtrada e telegráfica:
  - Número de tokens
  - Número de palavras de conteúdo
  - Diversidade lexical
  - Comprimento médio das palavras
  - Comprimento médio das frases
  - Fração de palavras de conteúdo
  - Total de sílabas

### 7. Validação e Filtragem Adicional
- Frases telegráficas com menos de 3 palavras são descartadas.
- Taxa de compressão (número de tokens telegráficos / número de tokens filtrados) deve ser <= 0.8.
- Diversidade lexical da frase telegráfica deve ser > 0.5.

### 8. Armazenamento de Dados
- Os dados processados são salvos em um arquivo JSON (OUTPUT_JSON).
- Cada entrada contém:
  - Nome do arquivo fonte
  - Idade da criança
  - Frase original
  - Métricas de complexidade da frase original
  - Frase filtrada
  - Frase telegráfica
  - Métricas de complexidade da frase telegráfica
  - Taxa de compressão

### 9. Geração de Estatísticas
- Cálculo de estatísticas por grupo etário.
- As estatísticas são salvas em um arquivo de texto (OUTPUT_STATS).