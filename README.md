#Project MedFed Pro: Privacy-Preserving & Secure Medical AI

##📌 The Problem
In healthcare, data silos prevent AI from reaching its full potential.
Privacy: Hospitals cannot share patient data due to HIPAA/GDPR.
Bias: A single hospital might only see specific demographics (Non-IID data), making their local AI inaccurate for the general public.
Security: Decentralized networks are vulnerable to Poisoning Attacks where malicious actors try to sabotage the global model.

##🚀 The Solution: MedFed Pro

MedFed Pro is a Federated Learning system that allows hospitals to train a global diagnostic model without ever sharing raw patient data. This project implements a full lifecycle of Federated Learning: Privacy, Utility, and Adversarial Security.


##🌟 Key Features

Decentralized Training: Implementation of the FedAvg (Federated Averaging) algorithm.
Non-IID Simulation: Simulates "Specialist Hospitals" with biased data distributions.
Differential Privacy: Injects Gaussian noise into weight updates to prevent data reconstruction.
Byzantine Robustness: A secure Coordinate-wise Median Aggregator that defends the global model against malicious hackers.

📊 Experimental Results
1. The Collaboration Advantage (Privacy + Utility)
When hospitals worked alone, they were limited by their local data bias. By collaborating, the accuracy nearly doubled.
Local-Only Accuracy: ~41.2% (Stuck due to data bias)
Federated Accuracy: ~89.8% (Learned from the whole network)
2. The Security Shield (Adversarial Robustness)
## I introduced a Malicious Client performing a "Sign-Flipping" poisoning attack.
Standard FedAvg: Accuracy collapsed from 81.8% to 77.8% under attack.
MedFed Pro (Robust Median): Maintained 87.7% accuracy by mathematically ignoring the hacker's updates.
##⚙️ Technical Architecture

The Three-Pillar Defense
Federated Learning: Only model weights (gradients) are exchanged. Raw images never leave the hospital's local server.
Differential Privacy: We add a NOISE_MULTIPLIER to updates, ensuring that the global model cannot be "reversed" to reveal private patient features.
Median Aggregation: Unlike a simple Mean, the Median is an outlier-resistant statistic. It allows the server to identify and discard "poisoned" updates from malicious nodes.

##🛠️ Installation & Usage

Prerequisites
Python 3.12+
TensorFlow 2.x
NumPy, Matplotlib, Seaborn
