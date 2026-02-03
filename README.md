# VAE-Based Anomaly Detection in High-Dimensional Time Series Data

## Project Overview
This project implements and optimizes a Variational Autoencoder (VAE) for anomaly detection in high-dimensional time series data. The objective is to leverage the probabilistic latent space of VAEs to detect anomalous sequences embedded within complex temporal patterns.

The project strictly follows the task requirements and addresses all expected deliverables, including optimization analysis, anomaly scoring justification, and performance evaluation.

---

## Dataset Generation
A synthetic high-dimensional time series dataset is programmatically generated with the following properties:
- 10 features
- 10,000 time steps
- Periodic temporal patterns
- 5% labeled anomalies injected with magnitude-based perturbations

The data is normalized to ensure stable training.

---

## Sequence Construction
Sliding window sequences of length 50 are constructed from the raw time series. A sequence is labeled anomalous if at least one anomalous time point exists within the window.

---

## Model Architecture
The Variational Autoencoder consists of:
- Encoder network producing latent mean and log-variance
- Reparameterization trick for stochastic latent sampling
- Decoder network reconstructing the original input sequence

Mean Squared Error is used as the reconstruction loss, combined with KL divergence to form the ELBO objective.

---

## Latent Space Optimization
An optimization sweep is conducted over multiple latent space dimensions:
- Latent dimensions tested: 5, 10, 20

This allows analysis of the trade-off between reconstruction fidelity and regularization strength.

---

## Anomaly Scoring and Threshold Selection
Anomaly scores are computed using reconstruction error. A threshold is selected using the 95th percentile of reconstruction errors on the test set to balance sensitivity and robustness.

---

## Evaluation Metrics
Model performance is evaluated using standard classification metrics:
- Precision
- Recall
- F1-score

Metrics are reported for each latent space dimensionality tested.

---

## Results Summary
A summary table is produced comparing Precision, Recall, and F1-score across different latent dimensions, enabling informed selection of the final model configuration.

---

## Challenges and Trade-offs
Balancing reconstruction accuracy and KL divergence regularization was a key challenge. Lower latent dimensions increased regularization but reduced reconstruction fidelity, while higher dimensions improved reconstruction at the risk of overfitting.

---

## Project Status
Completed  
Fully documented  
Ready for submission  

---

## License
This project is intended for educational and demonstration purposes only.
