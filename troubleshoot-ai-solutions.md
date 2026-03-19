# Data Drift

Happens when the distribiition of incoming data changes compared to the data the model was trained on

example if model was traine don 2020 transctions but in 2025 user behavior changes so model accuracy drops

# types of data drift

covartiate drift: input features change(most common)
priot probability drift: label disctribution changes
concept drift(related) relationship betwee input and output changes

# Symptoms

Gradual performance decline
increase in prediction errors
model confidence become sunreliable

how to detect

minitor feature distributions like mean and variance
use stat tests like KS test, psi
compare training vs prod data

how to fix
retrain model with fresh data
add continous data pipelines
use monitoring tools

# Model degradation

refers to performance problems, its when a models accuracy and performance worsens over time

data drift is often the cause and degradation is the result

causes
data drift, concept dift, outdated trainign data, chane in user behavior or enviromnemtn

symptom
lower accuracy / recall
business kpi drop like revenue engagement
increase in user complaints

track model metrics, set aletrts on thresholds, a/b test model versions

how to fix
retrain regularltyt
use online learning or incrementtal updates
maintain a feedback loop with real labels

Data drift refers to changes in input data distribution, model degradation ius the resulting deline in performance and unexpected outputs are the visible sysmptoms when the model produces incorrect rpedictions.
