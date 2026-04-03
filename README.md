# LLM Divergent Scribes

## The Idea

A simple method to detect **behavioral anomalies** in a large language model using two observer models called **scribes**.

- **Subject** – the LLM being tested (e.g., Llama 3.2 3B)
- **Scribe A** – a smaller model from the **same** architectural family (e.g., TinyLlama)
- **Scribe B** – a model from a **different** architectural family (e.g., Phi‑3.5‑mini)

Both scribes **record** what the subject outputs. They do **not** judge correctness. The key signal is **disagreement** between the two scribes.

A sudden or sustained rise in disagreement suggests the subject is behaving in an unusual or unstable way.

## Why Two Different Families?

If both scribes came from the same family, they might share blind spots. Using a different family helps cancel out architectural biases. If both scribes agree something changed, it is more likely to be real.

## How to Use

1. Run the subject with a prompt (normal or stress).
2. Ask each scribe to describe the subject's output in plain text.
3. Compare the two descriptions (e.g., using cosine distance on sentence embeddings).
4. Track disagreement over many trials. Look for patterns or abrupt changes.

## Status

**Concept published.** Implementation planned. Contributions welcome.

*Initial concept developed in dialogue with an AI language model.*
## License

MIT License – use freely, keep copyright notice.

## Priority

This method was first publicly described on 2026-04-02 in this repository.
