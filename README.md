pyrouge
=======

A Python interface to the ROUGE package.

Right now, only the basic functionality is in place. You can score one summary at a time with respect to multiple reference summaries.
Down the road, the plan is to reimplement (parts of) ROUGE in pure Python.
The motivation is that the ROUGE package, while standard in evaluation of extractive summaries,
can be a challenge to obtain and install, and also does not fit well in a Python workflow.

Contributions and suggestions are very welcome.

## Usage example

```
from pyrouge import Rouge155
from pprint import pprint

ref_texts = {'A': "Poor nations pressurise developed countries into granting trade subsidies.",
             'B': "Developed countries should be pressurized. Business exemptions to poor nations.",
             'C': "World's poor decide to urge developed nations for business concessions."}
summary_text = "Poor nations demand trade subsidies from developed nations."


rouge = Rouge155(n_words=100)
score = rouge.score_summary(summary_text, ref_texts)
pprint(score)
```

The output will be this:

```
{'rouge_1_f_score': 0.76879,
 'rouge_1_f_score_cb': 0.76879,
 'rouge_1_f_score_ce': 0.76879,
 'rouge_1_precision': 0.86928,
 'rouge_1_precision_cb': 0.86928,
 'rouge_1_precision_ce': 0.86928,
 'rouge_1_recall': 0.68912,
 'rouge_1_recall_cb': 0.68912,
 'rouge_1_recall_ce': 0.68912,
 'rouge_2_f_score': 0.52941,
 'rouge_2_f_score_cb': 0.52941,
 'rouge_2_f_score_ce': 0.52941,
 'rouge_2_precision': 0.6,
 'rouge_2_precision_cb': 0.6,
 'rouge_2_precision_ce': 0.6,
 'rouge_2_recall': 0.47368,
 'rouge_2_recall_cb': 0.47368,
 'rouge_2_recall_ce': 0.47368,
 'rouge_3_f_score': 0.39521,
 'rouge_3_f_score_cb': 0.39521,
 'rouge_3_f_score_ce': 0.39521,
 'rouge_3_precision': 0.44898,
 'rouge_3_precision_cb': 0.44898,
 'rouge_3_precision_ce': 0.44898,
 'rouge_3_recall': 0.35294,
 'rouge_3_recall_cb': 0.35294,
 'rouge_3_recall_ce': 0.35294,
 'rouge_4_f_score': 0.34147,
 'rouge_4_f_score_cb': 0.34147,
 'rouge_4_f_score_ce': 0.34147,
 'rouge_4_precision': 0.38889,
 'rouge_4_precision_cb': 0.38889,
 'rouge_4_precision_ce': 0.38889,
 'rouge_4_recall': 0.30435,
 'rouge_4_recall_cb': 0.30435,
 'rouge_4_recall_ce': 0.30435,
 'rouge_su4_f_score': 0.61313,
 'rouge_su4_f_score_cb': 0.61313,
 'rouge_su4_f_score_ce': 0.61313,
 'rouge_su4_precision': 0.6977,
 'rouge_su4_precision_cb': 0.6977,
 'rouge_su4_precision_ce': 0.6977,
 'rouge_su4_recall': 0.54685,
 'rouge_su4_recall_cb': 0.54685,
 'rouge_su4_recall_ce': 0.54685}
```
## Run tests

The unit tests can be run be issuing ``nosetests´´ from the root directory of the package.
