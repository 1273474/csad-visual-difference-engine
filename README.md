# CSAD: Chrono-Spatial Anomaly Detection System

**TrackShift 2025 Submission for Problem 1: Visual Difference Engine**

**Elevator Pitch:** Our AI doesn't just spot changes; it predicts their impact. We automate F1 quality control & instantly calculate the aerodynamic effect of design tweaks, giving Haas a competitive edge.

-----

## 🎯 The Problem

The "Visual Difference Engine" challenge requires a system to detect changes in time-series images across four distinct and demanding domains:

1.  **Manufacturing Inspections:** High-speed, high-precision quality control.
2.  **F1 Car Design Tracking:** Identifying subtle geometric changes and understanding their performance impact.
3.  **Infrastructure Monitoring:** Detecting slow, long-term degradation in critical assets.
4.  **Brand Compliance:** Ensuring visual brand consistency across all channels.

A simple pixel-comparison tool will fail. A successful solution must understand context, geometry, and physics, and be scalable enough to serve both the immediate needs of the Haas F1 Team and the broader enterprise clients of Mphasis.

## ✨ Our Solution: The CSAD Framework

CSAD is a modular, enterprise-grade AI framework designed to intelligently find, interpret, and quantify visual changes. Instead of a single monolithic model, we use a pipeline of specialized AI "engines," each a state-of-the-art expert in its task.

This architecture is robust, scalable, and adaptable to each of the four problem domains.

### 🧠 The Core Engines

Our system is built on a series of interconnected modules:

1.  **Semantic Engine (`SAM + Grounding DINO`):** A segmentation-first module that finds and precisely isolates the object of interest (a car part, a crack, a logo) before any analysis begins.
2.  **Anomaly Engine (`PatchCore`):** Our expert for manufacturing QC. Trained only on "perfect" CAD data, it creates a memory bank of normal features and flags any real-world deviation, no matter how small or novel.
3.  **Similarity Engine (`DINOv2`):** A powerful Vision Transformer backbone that generates rich geometric and semantic "fingerprints" of objects. It creates a precise heat map showing exactly where two designs differ.
4.  **Temporal Engine (`Change Point Detection`):** Analyzes a time-series of object fingerprints to detect both abrupt events and slow, gradual degradation over months or years.
5.  **CFD Surrogate Engine (`Graph Neural Network`):** Our "wow" feature. Trained on historical CFD simulation data, this GNN takes a geometric change detected by our other engines and predicts its real-world aerodynamic impact (downforce/drag) in seconds.

### 🚀 Applications in Action

- **Manufacturing:** The **Anomaly Engine** provides real-time, sub-millimeter defect detection, solving the Haas F1 Team's 100% inspection bottleneck.
- **F1 Design Tracking:** The **Similarity Engine** creates a difference heat map between two designs, and the **CFD Surrogate Engine** predicts the performance impact, turning visual data into a competitive advantage.
- **Infrastructure:** The **Temporal Engine** tracks the growth of cracks in bridges over time, providing an early warning system for structural health.
- **Brand Compliance:** The **Semantic Engine** finds logos, and the **Similarity Engine** verifies them against a database of approved assets, automating brand governance.

## 🛠️ Built With

This project leverages a state-of-the-art, enterprise-ready technology stack:

- **Languages & Core Libraries:** Python, PyTorch, TensorFlow, Scikit-learn, OpenCV
- **AI Models & Frameworks:** SAM, Grounding DINO, DINOv2, CLIP, PatchCore, Graph Neural Networks (GNNs), PyTorch3D
- **Deployment & MLOps:** Docker, Kubernetes, NVIDIA Triton Inference Server, ONNX, MLflow
- **Cloud & Infrastructure:** AWS/GCP/Azure, NVIDIA Jetson (for edge), Kafka
- **Databases:** TimescaleDB (for time-series data), Milvus/FAISS (for vector similarity search)
- **APIs:** REST, gRPC

## 📂 Project Structure

The repository is organized into a modular, scalable structure that reflects our microservices-based architecture.
