## Paper Title 
On Integrating Resilience and Human Oversight into LLM-Assisted Modeling Workflows for Digital Twins

---

## Authors

| Role | Name | Contact |
|------|------|---------|
| Author | Lekshmi P | lekshmi20231101@iitgoa.ac.in |
| Author | Neha Karanjkar | nehak@iitgoa.ac.in |

**Corresponding author for artifact evaluation:** Lekshmi P


---

## Installation

**Step 1 — Clone or copy the repository**

**Step 2 — Install dependencies**
```bash
pip install -r requirements.txt
```

**Step 3 — Configure the Gemini API key**

Create a `.env` file inside the `app/IM/` folder with the following content:
```
GEMINI_API_KEY=your_api_key_here
```

**Step 4 — Run the application**
```bash
cd app
streamlit run Description_to_model_generator.py
```

---

## Verifying Installation

After running the Streamlit command, the app should open in your browser at:
```
http://localhost:8501
```

If it loads without errors, the installation is complete.

---

## Dependencies

| Dependency | How to Obtain |
|------------|---------------|
| FactorySimPy | Included in `src/` — no separate install needed |
| All others | Listed in `requirements.txt` |

---

## Expected Duration

| Phase | Duration |
|-------|----------|
| Model generation (single run) | 2–3 minutes |
| Manual evaluation (model comparison + error counting) | 8–10 minutes per experiment |
| Full experimental phase (all experiments) | ~70–75 hours |

---

## Hardware Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| RAM | 8 GB | 16 GB |
| CPU | 4 cores | Intel i5/i7 or AMD Ryzen 5/7 (6–8 cores) |
| Storage | 20 GB free | 256–512 GB SSD |
| GPU | Not required | Not required |
| OS | Windows 10 / Ubuntu 20.04 or later | Windows 11 / Ubuntu 22.04 |
| Internet | Required (Gemini API) | Required |

---

## Experimental Environment

**Software**

| Component | Details |
|-----------|---------|
| Operating System | Windows 11 Home Single Language (64-bit) |
| Python | 3.12 |

**Hardware**

| Component | Details |
|-----------|---------|
| CPU | AMD Ryzen 5 5500U with Radeon Graphics |
| Cores | 6 cores / 12 logical processors |
| RAM | 8 GB |
| Storage | Kingston 512 GB NVMe SSD |
| GPU | None |

---
## Methodology

The experiment consisted of 35 factory system scenarios, each described at two levels of granularity — a coarse description and a detailed description — resulting in 70 runs in total. The two description types were evaluated independently to assess how the level of input detail affects model quality.

For each run, the description was provided to the tool via the app interface, which used the Gemini API to generate a simulation model along with its assumptions and a block diagram. The generated model was then manually compared against the corresponding ground truth model from `error-characterisation/groundtruth_models/`.

Errors were identified and counted across the following categories:

| Error Type | Description |
|---|---|
| Type Mismatch Error | A model element is assigned the wrong type |
| Naming Error | Incorrect or inconsistent naming of nodes or edges |
| Parameter Error | Wrong values assigned to model parameters |
| Hallucinating: Nodes | Nodes present in the generated model but absent from the ground truth |
| Hallucinating: Edges | Edges present in the generated model but absent from the ground truth |
| Hallucinating: Parameters | Parameters introduced by the model with no basis in the description |
| Hierarchy Mismatch Error | Incorrect nesting or structural hierarchy of components |
| Syntax Error | General syntactic incorrectness in the generated model |
| FactorySimPy Syntax Violation | Violations specific to the FactorySimPy modelling framework |

Where the generated model did not match the ground truth, the assumptions or the input description were revised and the model was regenerated. This refinement was repeated iteratively — some experiments converged in a single run, while others required up to three iterations. All comparisons and error classifications were performed manually by the authors.

---

## Running the Experiment

This section describes how to run the experiments and evaluate the generated models against the ground truth.

**Step 1 — Open `error-characterisation/experiments.csv`**

Each row in the CSV corresponds to one experiment and contains a coarse description and a detailed description of the factory system to be modelled.

**Step 2 — Paste a description into the app**

In the running Streamlit app, paste either the coarse or detailed description from the `Description` column into the input field and click **"Generate Model"**.

The tool will produce:
- A simulation model along with the assumptions it made during generation
- A block diagram visualising the model structure

**Step 3 — Save the outputs**

Save both the generated model and the block diagram locally for comparison.

**Step 4 — Compare against the ground truth**

Open the corresponding ground truth model from `error-characterisation/groundtruth_models/` and compare it with the generated model. The reference block diagram in `error-characterisation/Diagrams/` can help with visual comparison.

**Step 5 — Refine and iterate**

If the generated model does not match the ground truth, adjust either the assumptions directly in the app or revise the description and regenerate. Repeat until the model converges to the ground truth.

> **Tip:** The generated models from our own experimental runs are available in `error-characterisation/generated_models/` and can be used as a reference to gauge expected output quality.

---


## Results and Artifacts

The `error-characterisation/` directory contains all files needed to reproduce the experiments reported in the paper:

| Path | Contents |
|------|----------|
| `error-characterisation/experiments.csv` | Coarse and detailed descriptions used for each experiment |
| `error-characterisation/groundtruth_models/` | Ground truth models for each experiment |
| `error-characterisation/Diagrams/` | Block diagrams of the corresponding models |
| `error-characterisation/generated_models/` | Results produced during our experiments (as reported in the paper) |

---

## License

The license file is included in the GitHub repository.

## DOI
P, L., & Karanjkar, N. (2026). InferaFactorySim/FactoryFlow_v2_artifacts_eval: artifacts (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.19380593
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19380593.svg)](https://doi.org/10.5281/zenodo.19380593)
