Дообученная модель DistilBERT в рамках [NLP-соревнования](https://www.kaggle.com/competitions/nlp-getting-started) на kaggle.

Дистиллированный BERT весит на 40% меньше, чем оригинальный BERT, на 60% быстрее ее и сохраняет более 95% функционала на бенчмарке GLUE.
В DistilBERT используется encoder-only архитектура BERT, но с 6 encoder-блоками вместо 12 у BERT-base.

В отличие от BERT, DistilBERT предобучается только через Masked Language Modeling (MLM) без  Next Sentence Prediction (NSP). DistilBERT обучается с использованием тройного лосса:

* Лосс BERT'а;

* Лосс дистилляции измеряющий сходство выходов между DistilBERT и BERT;

* Косинусное расстояние измеряет, насколько похожи скрытые состояния DistilBERT и BERT.

Baseline-решением является TF-IDF, скормленный логистической регрессии
