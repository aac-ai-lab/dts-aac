# Dataset Fields

1. **`utterance`**
   - **Description**: The child's original sentence.
   - **Type**: text
   - **Example**: "I want to play with the red ball"

2. **`telegraphic`**
   - **Description**: The telegraphic version of the original sentence.
   - **Type**: text
   - **Example**: "want play red ball"

3. **`age`**
   - **Description**: The child's age at the time of speech.
   - **Type**: numeric (years and months, e.g., 3;6 for 3 years and 6 months)
   - **Example**: "3;6"

4. **`file`**
   - **Description**: The name of the CHAT file from which the sentence was extracted.
   - **Type**: text
   - **Example**: "adam15.cha"

5. **`utterance_complexity`**
   - **Description**: A dictionary containing complexity metrics of the original sentence.
   - **Type**: dictionary with the following subfields:
     - **`num_tokens`**: Total number of words (tokens).
     - **`num_content_words`**: Number of content words (nouns, verbs, adjectives, adverbs).
     - **`lexical_diversity`**: Lexical diversity (ratio of unique words).
     - **`avg_word_length`**: Average word length (in characters).
     - **`avg_sentence_length`**: Average sentence length (in words).
     - **`content_fraction`**: Fraction of the sentence composed of content words (content words / total words).
     - **`total_syllables`**: Total number of syllables in the sentence.


6. **`telegraphic_complexity`**
   - **Description**: A dictionary containing complexity metrics of the telegraphic sentence.
   - **Type**: dictionary with the same subfields as `utterance_complexity`

7. **`compression_rate`**
   - **Description**: The compression rate, calculated as the ratio of the number of tokens in the telegraphic sentence to the number of tokens in the original sentence.
   - **Type**: numeric (float)
   - **Example**: 0.5 (indicating that the telegraphic sentence is half the length of the original)

**Note**: The final dataset will only include entries where:
- The telegraphic sentence has at least 3 words.
- The compression rate is less than 1 (indicating an effective reduction in sentence length).

```json
[
    {
      "file": "011000.cha",
      "age": 1,
      "utterance": "oh no no no no no no dʌ [: the] dwægænz [: dragons] xxx (.) &~gorps in dɛr [: there] [/] dɛr [: there] .",
      "utterance_complexity": {
         "num_tokens": 17,
         "num_content_words": 5,
         "lexical_diversity": 0.5882352941176471,
         "avg_word_length": 3.176470588235294,
         "avg_sentence_length": 17,
         "content_fraction": 0.29411764705882354,
         "total_syllables": 18
      },
      "utterance_filtered": "oh no no no no no no the dragons gorps in there there",
      "telegraphic": "dragon gorps there",
      "telegraphic_complexity": {
         "num_tokens": 3,
         "num_content_words": 2,
         "lexical_diversity": 1.0,
         "avg_word_length": 5.333333333333333,
         "avg_sentence_length": 3,
         "content_fraction": 0.6666666666666666,
         "total_syllables": 4
      },
      "compression_rate": 0.23076923076923078
   },
   ...
]
```

Essa estrutura do dataset oferece várias vantagens:

1. **Comparação direta**: Permite comparar facilmente as frases originais com suas versões telegráficas.
2. **Análise de complexidade**: Fornece métricas de complexidade tanto para as frases originais quanto para as telegráficas, permitindo análises comparativas.
3. **Contexto**: Inclui informações sobre a idade da criança e a fonte do arquivo, possibilitando análises baseadas em desenvolvimento e fonte dos dados.
4. **Eficácia da conversão**: A taxa de compressão permite avaliar a eficácia da conversão telegráfica para cada frase.

[< Dataset Statistics](/dts-aac/docs/statistics)