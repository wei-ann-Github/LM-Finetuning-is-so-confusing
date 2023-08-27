# finetuning_is_so_confusing

Ever find that you do not know what finetuning hyperparameters to use when you are training or finetuning a Language Model?

This is a collection of finetuning settings used in some of the leading Language Model Research papers!
(For details, please refer to the paper instead.)

| Purpose of finetuning | Base Model/Foundation Model | Dataset | Dev metric | FT Steps | Batch Size | Optimizer | Optimizer Parameters     | Model/Method Specific Hyperparams | Paper |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Prompt Tuning | LM-adapted T5.1.1<br>- small ~77M<br>- base ~250M<br>- large ~800M<br>- xl ~3B<br>- xxl ~11B | Each task in SuperGlue | T5's stanadrd cross entropy loss | max 30K steps | 32 | Adafactor | LR 0.3<br>Wt decay 1e-5<br>$\beta_2$ decay 0.8<br>parameter scaling = off | 100 tokens Prompt length<br>(abaliation finds that 20 is adequate for all T5.1.1 sizes) | Lester, B., Al-Rfou, R., & Constant, N. (2021). The power of scale for parameter-efficient prompt tuning. In Proceedings of the 2021 Conference on Empirical Methods in Natural Language Processing (pp. 3020-3032). Association for Computational Linguistics. |
