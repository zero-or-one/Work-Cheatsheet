## Recommendations from my experience

1. Document and log everything. Even document summaries of your documents once in a while. The project is too big, I found myself repeating unsuccessful experiments in years just because I forgot we did it before.
2. Be careful if training parameters, record them in the beginning of the training and check everything twice. The common source of the bugs if when you change someting, forget it, and realize 10 training later.
3. Keep all the slightly useful trained models and the result tables. They benefit a lot during report submission period.
4. Change a single thing at a time for each new training. The moment you change a few things, you will get disastrous results (Murphy's law) and you would not know why exactly.
5. Wait long enough, sometimes loss needs large amount of time to converge.
6. Stick to a single metrics (CER in my case) to avoid confusison and tedious decision process.
7. Choose best model by validation loss, even if you use uncorrelated metrics for evaluation.
