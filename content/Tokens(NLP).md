- **Date of Entry:** 2026-02-04
- **Tags:** #nlp

## Understanding :
Any unit of text ranging from a single character to a whole paragraph which can be fed as an input to an NLP model is called Token.
- Based on the problem, We have to choose the scale of a token.
- This token will be converted into a vector later.

| **Scale**     | **Example Token**  | **When to use it?**                                                         |
| ------------- | ------------------ | --------------------------------------------------------------------------- |
| **Character** | `a`, `b`, `7`, `!` | For code, math, or languages without spaces (Chinese). Language is limited. |
| **Sub-word**  | `play`, `##ing`    | **Standard for LLMs (GPT/BERT).** Balances speed and meaning.               |
| **Word**      | `playing`          | For simple tasks like Spam detection or Sentiment analysis.                 |
| **Sentence**  | `The cat sat.`     | For **Semantic Search** or finding similar documents.                       |
## Visual Aid :
![[nlp tokens and dollar bills.png]]

## Note :
- A token is further converted into a vector form.
- Sub-word Tokenization is the pro-method as it consists of tokens for common words in the language at the same time it further breaks the larger words into maneagable chunks.