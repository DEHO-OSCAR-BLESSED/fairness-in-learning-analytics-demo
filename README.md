# Bias In, Bias Out: Auditing and Repairing an At-Risk Student Predictor

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DEHO-OSCAR-BLESSED/fairness-in-learning-analytics-demo/blob/main/fairness_demo.ipynb)

Demo for the session *Data Ethics in Education: Consent, Privacy, and the Datafication of Learning* at **The Adelaide School of Learning Sciences, Data & AI** (Adelaide University, 12 November 2026).

## What it does

1. Trains an early-warning model that predicts which students will fail or withdraw, using demographics and assessment performance from the first 60 days.
2. Audits the model's flag rate, false-alarm rate and hit rate for the most socioeconomically deprived students compared with everyone else.
3. Tests "fairness through unawareness", which means deleting the sensitive attribute.
4. Applies **Reweighing** (Kamiran & Calders, 2012), a pre-processing fairness method, and compares all three models.

## Key result (test set, n = 9,751)

| Model | Accuracy | False-alarm rate: most deprived | False-alarm rate: others |
|---|---|---|---|
| Baseline (uses attribute) | 77.3% | 21.3% | 9.9% |
| Attribute removed | 77.1% | 15.1% | 11.4% |
| Reweighing | 77.2% | 12.4% | 11.3% |

## Run it

Click the **Open in Colab** badge and choose *Runtime → Run all*. The data loads directly from this repository, so no setup is needed. To audit disability instead, set `PROTECTED = "disabled"`.

## Data

Open University Learning Analytics Dataset (OULAD), a subset of its tables (`studentInfo`, `assessments`, `studentAssessment`), in `data/`.
Kuzilek, J., Hlosta, M., & Zdrahal, Z. (2017). Open University Learning Analytics dataset. *Scientific Data*, 4, 170171. https://doi.org/10.1038/sdata.2017.171. Licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## References

- Kamiran, F., & Calders, T. (2012). Data preprocessing techniques for classification without discrimination. *Knowledge and Information Systems*, 33(1), 1–33.
