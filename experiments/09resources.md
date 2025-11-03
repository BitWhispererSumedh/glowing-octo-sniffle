# TempoWiC Quick Resources

- Dataset paper: [TempoWiC dataset paper (COLING 2022)](https://aclanthology.org/2022.coling-1.296.pdf)
- Starter kit & splits: [TempoWiC starter kit (GitHub)](https://github.com/cardiffnlp/TempoWiC)
- TimeLMs paper/demo & GitHub: [TimeLMs: Diachronic Language Models from Twitter](https://arxiv.org/abs/2202.03829), [TimeLMs (ACL Demo)](https://aclanthology.org/2022.acl-demo.25.pdf), [TimeLMs GitHub](https://github.com/cardiffnlp/timelms)
- BERTweet: [BERTweet paper](https://arxiv.org/abs/2005.10200), [BERTweet GitHub](https://github.com/VinAIResearch/BERTweet)
- EvoNLP'22 proceedings (dma winner mentioned): [EvoNLP 2022 proceedings (dma winner note)](https://aclanthology.org/2022.evonlp-1.pdf)
- Generative entry example: [MLLabs-LIG TempoWiC generative system](https://aclanthology.org/2022.evonlp-1.1.pdf)
- Imbalance‑aware losses: [Class-Balanced Loss (CVPR 2019)](https://openaccess.thecvf.com/content_CVPR_2019/papers/Cui_Class-Balanced_Loss_Based_on_Effective_Number_of_Samples_CVPR_2019_paper.pdf), [Symmetric Cross Entropy (ICCV 2019)](https://openaccess.thecvf.com/content_ICCV_2019/papers/Wang_Symmetric_Cross_Entropy_for_Robust_Learning_With_Noisy_Labels_ICCV_2019_paper.pdf)

**Plan**
1. Start with Strategy 5 (thresholding) — fast wins.
2. Add Strategy 7 (metadata) — low‑effort features.
3. Choose one of Strategy 1 or 4 (sense or retrieval) — bigger lift.
4. If compute permits, try Strategy 3 (temporal MoE) + Strategy 8 (stack).
5. Use Strategy 2 (LLM distillation) to squeeze extra points without large inference cost.
