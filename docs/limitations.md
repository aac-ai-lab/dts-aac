# Limitações

Limitações e Possíveis Vieses do Dataset Sintético

1. **Representatividade Limitada**:
   - O dataset é baseado apenas nos arquivos .cha disponíveis no diretório especificado, o que pode não representar uma amostra diversificada de crianças.

2. **Viés Linguístico**:
   - O código usa o modelo de linguagem 'en_core_web_sm' do spaCy, indicando um foco em inglês. Isso pode não ser adequado para dados multilíngues ou outras línguas.

3. **Simplificação Excessiva**:
   - A conversão para frases telegráficas pode resultar em perda de nuances e contexto importantes.

4. **Viés de Idade**:
   - A extração da idade da criança pode não ser precisa ou consistente em todos os arquivos, levando a possíveis erros na categorização por idade.

5. **Filtragem Rígida**:
   - Os critérios de filtragem (como o número mínimo de palavras e a taxa de compressão) podem excluir frases importantes ou atípicas.

6. **Dependência de Ferramentas de NLP**:
   - O uso do spaCy para análise linguística pode introduzir erros ou vieses inerentes ao modelo utilizado.

7. **Foco em Conteúdo**:
   - A ênfase em palavras de conteúdo pode não capturar adequadamente a importância de certas palavras funcionais no desenvolvimento da linguagem.

8. **Perda de Contexto Conversacional**:
   - A extração de frases individuais perde o contexto da conversa completa, o que pode ser crucial para entender o desenvolvimento da linguagem.

9. **Viés de Seleção de Palavras Funcionais**:
   - A lista predefinida de palavras funcionais essenciais pode não ser apropriada para todos os contextos ou estágios de desenvolvimento.

10. **Limitações na Análise de Complexidade**:
    - As métricas de complexidade utilizadas podem não capturar todos os aspectos relevantes do desenvolvimento da linguagem infantil.

11. **Possível Subrepresentação de Frases Complexas**:
    - O processo de filtragem e telegrafação pode favorecer frases mais simples, potencialmente subrepresentando a complexidade real da fala infantil.

12. **Falta de Consideração de Fatores Socioculturais**:
    - O dataset não leva em conta fatores socioculturais que podem influenciar o desenvolvimento da linguagem.

13. **Viés de Transcrição**:
    - A qualidade e consistência das transcrições nos arquivos .cha podem variar, afetando a precisão dos dados extraídos.

14. **Limitações na Detecção de Erros de Fala**:
    - O processo de limpeza e normalização pode inadvertidamente corrigir erros de fala que são naturais e importantes no desenvolvimento infantil.
