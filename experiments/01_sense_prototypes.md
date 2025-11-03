## Strategy 1 — Sense Prototypes per Time Window (semi‑supervised)

**Intuition (simple).** The target word may have multiple senses. For each time window (e.g., prior vs. peak), cluster the **token‑level contextual embeddings** of the target word to obtain a few **sense prototypes**. Compare the prototype sets across time; a large mismatch suggests a **meaning shift**.

**Minimal recipe.**
1. Use a tweet‑adapted encoder (e.g., **BERTweet** or **TimeLMs**).
2. For each lemma+POS and time window, collect tweets containing the target; extract **token embeddings** (last or pooled layers).
3. Cluster (e.g., k=2–4 via k‑means or HDBSCAN). The cluster centroids are **prototypes**.
4. Compute a **prototype distance** between windows (e.g., Earth‑Mover’s Distance / optimal matching).
5. Train a small classifier that uses this distance (+ a few lexical features) to predict **same** vs **different** sense.

**Why it helps.** It injects **sense structure** instead of relying only on instance‑level similarity. Prototypes are robust to tweet noise and capture **dominant senses** per time.

**Implementation tips.**
- Freeze the encoder first; tune clustering hyper‑params on dev.
- Try **TimeLMs** models closest to your data period.
- Add **POS tags** and **emoji/hashtag features** as auxiliary inputs to the classifier.

**Eval.** Optimize the **decision threshold for macro‑F1** on the dev set (don’t assume 0.5).

**References.**
- [TempoWiC dataset paper (COLING 2022)](https://aclanthology.org/2022.coling-1.296.pdf)
- [TimeLMs: Diachronic Language Models from Twitter](https://arxiv.org/abs/2202.03829), [TimeLMs (ACL Demo)](https://aclanthology.org/2022.acl-demo.25.pdf), [TimeLMs GitHub](https://github.com/cardiffnlp/timelms)
- [BERTweet paper](https://arxiv.org/abs/2005.10200), [BERTweet GitHub](https://github.com/VinAIResearch/BERTweet)
- [TempoWiC starter kit (GitHub)](https://github.com/cardiffnlp/TempoWiC)
