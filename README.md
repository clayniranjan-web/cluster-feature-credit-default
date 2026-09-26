# Problem Statement

Credit card issuers need to predict which customers are likely to default on their payments the following month, in order to manage risk and make informed credit decisions. This is typically framed as a supervised classification problem using demographic and payment-history features.

This project tests a specific, industry-used technique on top of that baseline: using unsupervised clustering to discover latent customer segments, then injecting the discovered segment (cluster ID) as an additional input feature into the supervised classifier — rather than using clustering as an end in itself.

The underlying question: do the behavioral archetypes that clustering surfaces (e.g. chronic late payers, consistent payers, high-utilization revolvers) carry predictive signal that the classifier can't already extract on its own from the raw features?

### Specifically, this project investigates:

Can meaningful, interpretable customer segments be discovered from payment-history and behavioral features using K-Means, DBSCAN, and Hierarchical clustering?

Does adding the discovered cluster ID as a feature measurably improve classification performance (precision, recall, F1, ROC-AUC) across Logistic Regression, Random Forest, and XGBoost?

Does the improvement (if any) differ by model type — specifically, does a linear model (Logistic Regression) benefit more from the cluster feature than tree-based models (Random Forest, XGBoost), which can already learn nonlinear decision boundaries on their own?

The project does not assume the answer is yes. If cluster-based feature engineering provides no measurable lift — or even hurts performance — that is treated as a valid and reportable finding, not a failure of the pipeline.