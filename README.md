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