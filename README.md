# QRC-Mosaic: Mapping Retro-Futuristic Trajectories via Quantum Reservoir Computing

> **Moth_Hack Quantum Computing Hackathon 2026 Submission**
>
> *Exploring Non-Linear Temporal Permutations in Historical Image Corpora*

Bypassing traditional pixel-level colour sorting, QRC-Mosaic is a hybrid quantum pipeline that processes metadata features of 64 retro-futuristic inventions across a 140-year range through a fading memory reservoir to construct transitioning pattern layers of historical tech-dreaming insight via a dynamic 8 x8 proof-of-concept artwork.

---

# Project Summary

**QRC-Mosaic** explores how Quantum Reservoir Computing (QRC) can be used to transform temporal and metadata-rich historical image corpora into non-linear spatial visual structures.

The project uses a curated corpus of **64 historical images spanning approximately 1880–2020**, centred on human representations and perceptions of future technology.

Rather than arranging the images solely according to perceptual colour similarity, the project uses **MOTH Atlas Quantum Engines** to process temporal metadata as a sequence and generate a quantum-reservoir trajectory. This trajectory is then converted into an **8 × 8 spatial permutation** that determines the placement of the 64 image tiles.

A classical **Hungarian assignment using CIELAB colour distance** provides a baseline against which the QRC-derived arrangement can be compared.

The resulting mosaic is rendered through an eye-shaped target structure, creating a visual representation of how historical visions of technological futures can be reorganised through non-linear temporal dynamics.

---

# Key Results & Metrics

| Metric | Result |
|---|---:|
| Classical Hungarian Baseline Score ($L^*a^*b^*$) | `1.8563` |
| Quantum Reservoir Permutation Score | `2.3747` |
| Visual Optimisation Gap | **`21.8%`** |
| Topological Clustering Validation | **`Z = +2.07`** |

The **Z = +2.07** result indicates statistically significant spatial clustering in the post-hoc analysis across creator lineages, geographical origins, and thematic eras.

The results should be interpreted as a **proof-of-concept comparison between two different spatial-ordering mechanisms**, rather than as evidence that QRC universally outperforms classical optimisation.

---

# Project Structure

```text
QRC-Mosaic/
│
├── 00_qrc_mosaic_mapping_retro_futuristic_trajectories.ipynb
├── 01_feature_extraction_and_tagging.ipynb
├── 02_vlm_semantic_description.ipynb
├── 03_aux_dynamic_dual_eye_animator.ipynb
│
├── images/
│   ├── original/                    # 64 raw historical artworks (FV001–FV064)
│   └── images_cropped/              # Standardised 512 × 512 px cropped tiles
│
├── metadata/
│   ├── image_metadata.csv           # CIELAB profiles & MobileNetV3 embeddings
│   └── semantic_descriptions.json   # Qwen2.5-VL descriptions & semantic tags
│
├── target/
│   └── target_eye.jpg               # Master target mask artwork
│
├── output/
│   ├── qrc_eye_creator_overlay.png
│   ├── qrc_eye_geography_overlay.png
│   ├── qrc_eye_semantic_overlay.png
│   ├── qrc_eye_year_overlay.png
│   ├── qrc_eye_mosaic_soft.png
│   └── animated_pair_of_eyes_natural.gif
│
├── requirements.txt
└── README.md

### Pipeline Architecture

Historical Image Corpus
        │
        ▼
┌───────────────────────────────┐
│ Feature Extraction            │
│                               │
│ CIE Lab + MobileNetV3         │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ VLM Semantic Processing       │
│                               │
│ Qwen2.5-VL-7B-Instruct        │
│ 13 semantic categories        │
└───────────────┬───────────────┘
                │
                ▼
       Temporal & Semantic
           Metadata
        1880 → 2020
                │
                ▼
┌───────────────────────────────┐
│ MOTH Atlas Quantum Engines    │
│                               │
│ qrc-train-v2                  │
│ qrc-gen-v2                    │
└───────────────┬───────────────┘
                │
                ▼
        Quantum Temporal
          Trajectory
                │
                ▼
          8 × 8 Spatial
          Permutation
                │
        ┌───────┴────────┐
        ▼                ▼
 Classical Baseline    QRC Mapping
 Hungarian + Lab       Quantum Trajectory
        │                │
        └───────┬────────┘
                ▼
       Comparative Evaluation
                │
                ▼
       Topological Diagnostics
                │
                ▼
          Eye Overlays
                │
                ▼
       Dual-Eye Animation
```

# Technical Setup & Installation
Requirements:
- Python 3.10+
- PyTorch
- CUDA-capable GPU recommended for VLM inference
- OpenCV
- MediaPipe
- Pillow
- ImageIO
- SciPy
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

The quantum component additionally requires access to the MOTH Atlas platform and its available QRC engines.

## Environment Installation

### Clone the repository
```
git clone https://github.com/your-username/QRC-Mosaic.git
cd QRC-Mosaic
```
### Create a virtual environment
```
python -m venv .venv
```
### macOS / Linux
```
source .venv/bin/activate
```
### Windows
```
.venv\Scripts\activate
```

### Install dependencies
```
pip install -r requirements.txt
```

## Quick Start & Running the Notebooks

To run the pipeline locally, activate the project virtual environment and launch Jupyter.

Activate the virtual environment:

```
source .venv/bin/activate
```

Launch Jupyter Notebook:
```
jupyter notebook
```
The notebooks should be executed in the following order:

```
01_feature_extraction_and_tagging.ipynb
        ↓
02_vlm_semantic_description.ipynb
        ↓
00_qrc_mosaic_mapping_retro_futuristic_trajectories.ipynb
        ↓
03_aux_dynamic_dual_eye_animator.ipynb
```

### The Main Orchestration Notebook is:

**`00_qrc_mosaic_mapping_retro_futuristic_trajectories.ipynb`**

- The auxiliary animation notebook should be run after the static visual outputs have been generated by the main notebook.
- Note: The QRC notebooks require access to the MOTH Atlas quantum engines and any required API authentication/configuration. The exact Atlas configuration is not reproduced here because it is platform-specific.

# Notebook Execution Sequence

## 1. Feature Extraction & Tagging

**`01_feature_extraction_and_tagging.ipynb`**

*Data Ingestion & Feature Extraction*

This notebook prepares the historical image corpus for downstream processing. It:
- Loads the historical artwork corpus
- Standardises the images to 512 × 512 px
- Extracts CIE Lab colour features
- Generates MobileNetV3 visual embeddings
- Associates the extracted features with the project image identifiers

The resulting metadata is exported to:

**metadata/image_metadata.csv**

This provides the classical visual-feature layer used for baseline analysis and downstream evaluation.

## 2. Vision-Language Semantic Description

**`02_vlm_semantic_description.ipynb`**  

*Vision-Language Semantic Processing*

This notebook uses **Qwen2.5-VL-7B-Instruct** to inspect each image tile individually, identifying and analysing specific visual objects, structures, and environments.

For every artwork in the corpus, the VLM generates:
- **`visible_elements`**: Detailed list of identified physical objects, structures, vehicles, and figures
- **`description`**: Objective 30–60 word description of visible features
- **`primary_topic` & `secondary_topics`**: Controlled thematic tagging based on the identified visual contents

**Output Registry:** `metadata/semantic_descriptions.json`

*Role in Pipeline:* While the VLM analyzes and catalogs the physical objects in each image, this semantic data is used for post-hoc spatial clustering validation (\(Z = +2.07\)) rather than serving as the direct sorting metric for the Quantum Reservoir Computer.

## 3. QRC Mosaic Mapping & Evaluation

**`00_qrc_mosaic_mapping_retro_futuristic_trajectories.ipynb`**

*Main Notebook — Master Orchestration & Evaluation Workbench*

This is the central notebook of the project.

It integrates:

- Historical temporal metadata
- Image-level metadata
- CIE Lab visual features
- MOTH Atlas QRC engines
- Classical Hungarian matching
- QRC spatial permutation
- Topological clustering analysis
- Visual rendering and diagnostics

The quantum processing uses:

- qrc-train-v2
- qrc-gen-v2

Temporal metadata spanning approximately 1880–2020 is processed as a sequence. The resulting reservoir dynamics are used to derive an 8 × 8 spatial permutation of the 64 image tiles. 

The notebook then compares this arrangement against the classical CIELAB/Hungarian baseline. It also produces the static eye overlays used by the final animation stage.

## 4. Dynamic Dual-Eye Animation

**`03_aux_dynamic_dual_eye_animator.ipynb`**

*Auxiliary Animation Tool*

This notebook operates on the static outputs generated by the Main Notebook. It applies an additional visualisation layer incorporating:

- Crossfading
- Eyelid gating
- Pupil tracking
- Transitions between metadata views

The final output is:

**output/animated_pair_of_eyes_natural.gif**

The animation is a post-processing and presentation layer. It does not alter the underlying QRC-derived spatial permutation.

# Quantum Reservoir Computing

### Why QRC?

The project explores QRC as a mechanism for transforming sequential metadata into a high-dimensional dynamical representation The quantum system is not asked to directly optimise the visual appearance of the final artwork.

Instead, the architecture separates temporal dynamics from visual rendering.

```
Historical metadata
       ↓
Temporal sequence
       ↓
Quantum reservoir
       ↓
High-dimensional trajectory
       ↓
Spatial permutation
       ↓
Historical mosaic
       ↓
Visual diagnostics
```

This allows the quantum component to act primarily as an ordering mechanism, while the visualisation layer remains independently inspectable.

## Classical Baseline vs. QRC Mapping

The project deliberately compares two different approaches to arranging the image tiles.

### Classical Hungarian Baseline

A classical Hungarian assignment algorithm is used to minimise the CIELAB colour-distance between image tiles and target positions. This establishes a conventional perceptual optimisation baseline.

```
Colour features
      ↓
CIELAB distance
      ↓
Hungarian assignment
      ↓
Spatial arrangement
```

The resulting baseline score is:

L*a*b* score = 1.8563

### QRC Spatial Mapping

The QRC pathway instead processes temporal metadata as a sequence.
```
Temporal metadata
      ↓
QRC processing
      ↓
Reservoir dynamics
      ↓
Quantum trajectory
      ↓
Spatial permutation
```

The resulting permutation score is:

- QRC permutation score = 2.3747

The reported difference between the two arrangements is:

- Visual Optimisation Gap = 21.8%

This difference is treated as a measure of how the QRC-derived ordering diverges from the classical colour-optimised solution. It is not presented as a conventional quantum advantage metric.

## Topological Clustering Validation

The project also investigates whether the resulting spatial arrangement contains non-random structure beyond the visual optimisation objective.

A post-hoc analysis examines spatial relationships across metadata dimensions including:

- Creator lineage.
- Geographical origin.
- Historical era.
- Semantic/thematic categories.

The overall clustering validation produced:

Z = +2.07

This indicates statistically significant spatial clustering under the analysis performed.

The VLM-generated semantic descriptions are used to interpret the resulting spatial patterns after the QRC permutation has been generated.

This separation is important:
```
QRC
 ↓
Spatial permutation
 ↓
Post-hoc semantic analysis
```
rather than:
```
Semantic labels
 ↓
Optimisation target
 ↓
Forced clustering
```
# The Visual Concept

## Macro Form vs. Micro Narrative

The project operates at two visual scales.

### Macro Visual Form

- The 64 historical tiles are composed into an eye-shaped visual structure using a soft target mask.

- The paired-eye presentation represents dual human foresight: the recurring human impulse to imagine, anticipate, and visualise technological futures.

- The target mask provides a coherent macro-form while the placement of the individual tiles remains determined by the computational mapping.

### Micro Historical Narrative

At the tile level, each historical image retains its original visual characteristics and provenance.

The system does not rely on artificial colour warping to force images into the target.

Instead:
```
Individual image
       +
Spatial position
       ↓
Emergent macro-form
```
This creates a distinction between:

- What each historical image represents
- Where that image appears within the generated structure

# Proof of Concept vs. Production Scale

The current implementation uses a 64-tile proof-of-concept arranged on an 8 × 8 grid. At this scale, the target mask acts as visual scaffolding, helping the viewer recognise the intended macro-form despite the relatively low spatial density.

The longer-term hypothesis is that increasing the corpus size could reduce the need for explicit visual scaffolding.

With substantially larger archival corpora, potentially containing 1,000+ images, the system could explore whether high-dimensional temporal and semantic trajectories produce more naturally distributed relationships with:

- Luminance.
- Structural similarity.
- Visual gradients.
- Semantic categories.
- Historical periods.
- Geographical distributions.

The current 64-image implementation should therefore be understood as a proof-of-concept for the mapping mechanism, rather than a production-scale demonstration.

# Evaluation Framework

The project evaluates the generated arrangement through three complementary perspectives.

## 1. Perceptual Baseline

The classical Hungarian assignment establishes a reference point based on CIELAB colour distance.

Classical Hungarian Baseline:

**L*a*b* score = 1.8563**

## 2. QRC Spatial Mapping

The QRC-derived permutation produces:

QRC Reservoir Permutation:

**score = 2.3747**

The relative difference is reported as:

**Visual Optimisation Gap = 21.8%**

This quantifies the divergence between the QRC-derived spatial arrangement and the classical colour-optimised arrangement.

## 3. Spatial/Topological Diagnostics

Post-hoc analysis tests whether related metadata categories exhibit spatial relationships that differ from a randomised arrangement. The reported overall validation statistic is:

**Z = +2.07**

The analysis provides an additional perspective on whether the QRC-derived permutation produces interpretable spatial structure.

# Data & Metadata

The corpus contains 64 historical images spanning approximately 1880–2020, selected around the theme of human visions of future technology.

Each image is assigned a project identifier:

- FV001 – FV064

The processing pipeline separates several information layers:

| Layer | Purpose |
|---|---|
| Image | Historical visual source |
| CIE Lab | Perceptual colour representation |
| MobileNetV3 | Visual feature representation |
| Temporal metadata | Historical sequence |
| Geographic metadata | Spatial provenance |
| Creator metadata | Author/lineage analysis |
| VLM descriptions | Visual and semantic interpretation |
| Thematic tags | Post-hoc semantic diagnostics |
| QRC trajectory | Non-linear temporal representation |
| Spatial permutation | Final tile placement |

---

# Outputs

The principal generated outputs are:

| File | Description |
|---|---|
| `qrc_eye_creator_overlay.png` | Eye overlay highlighting creator-lineage structure |
| `qrc_eye_geography_overlay.png` | Eye overlay highlighting geographical structure |
| `qrc_eye_semantic_overlay.png` | Eye overlay highlighting semantic structure |
| `qrc_eye_year_overlay.png` | Eye overlay highlighting chronological structure |
| `qrc_eye_mosaic_soft.png` | Static QRC-derived mosaic |
| `animated_pair_of_eyes_natural.gif` | Final animated dual-eye artwork |

---

# Interpretation

QRC-Mosaic is not intended to demonstrate that quantum computation universally outperforms classical optimisation for image mosaics.

Instead, it investigates a more specific question:

>Can quantum reservoir dynamics provide a non-linear organisational mechanism for transforming temporal >and metadata-rich historical corpora into spatial visual structures?

The classical Hungarian solution provides a perceptual baseline. The QRC pathway provides an alternative ordering mechanism based on temporal reservoir dynamics. The resulting artwork therefore functions simultaneously as:

- A quantum-computing proof of concept.
- A computational media experiment.
- A visualisation of historical technological imagination.
- An investigation into non-linear metadata-to-space mapping.
Reproducibility

The repository separates the pipeline into distinct processing stages so that intermediate artefacts can be inspected independently.

The principal reproducibility chain is:
```
Raw historical images
        ↓
Feature extraction
        ↓
image_metadata.csv
        ↓
VLM semantic processing
        ↓
semantic_descriptions.json
        ↓
QRC temporal processing
        ↓
8 × 8 spatial permutation
        ↓
Static visual outputs
        ↓
Animated final artwork
```

This structure allows the feature-extraction, semantic, quantum-mapping, and visualisation stages to be inspected separately.

# Requirements & External Services

The project combines local machine-learning and image-processing components with the [MOTH Atlas](https://platform.mothquantum.com/) quantum infrastructure. 

- Local Components
- Python
- PyTorch
- OpenCV
- MediaPipe
- Pillow
- ImageIO
- SciPy
- Pandas
- NumPy
- Matplotlib
- Jupyter
- Quantum Infrastructure

### API Key Configuration

To run the quantum reservoir computing pipeline, you will need a MOTH Atlas API key:
1. Generate your personal API key on the [MOTH Quantum Platform](https://platform.mothquantum.com/keys).
2. Set your environment variable or create a `.env` file in the root directory:

```bash
export MOTH_API_KEY="your_api_key_here"
```

## MOTH Atlas Quantum Engines

- [**qrc-train-v2**](https://docs.mothquantum.com/docs/engines/qrc-train-v2) — MOTH Atlas Quantum Reservoir Training Engine API Documentation
- [**qrc-gen-v2**](https://docs.mothquantum.com/docs/engines/qrc-gen-v2) — MOTH Atlas Quantum Reservoir Generation Engine API Documentation

Access to these engines is required to reproduce the quantum-processing stage.

- Vision-Language Model
- Qwen2.5-VL-7B-Instruct

The VLM stage requires sufficient local compute/GPU resources for inference.

## Hackathon Context

Event: Moth_Hack Quantum Computing Hackathon 2026

Submission: QRC-Mosaic: Mapping Retro-Futuristic Trajectories via Quantum Reservoir Computing 
*Exploring Non-Linear Temporal Permutations in Historical Image Corpora*

Track/Concept: Quantum-native 2 notebook / Quantum Reservoir Computing

The project explores how a quantum-native computational mechanism can be embedded within a broader multimodal machine-learning and visualisation pipeline.

The emphasis is not simply on replacing a classical component with a quantum component, but on exploring whether quantum temporal dynamics can produce a different form of spatial organisation.

## License & Acknowledgements
- Hackathon: [MOTH_Hack Quantum Computing Hackathon 2026](https://hack.mothquantum.com/)
- Quantum Infrastructure: [MOTH Atlas](https://platform.mothquantum.com/) Quantum Engines ([qrc-train-v2](https://docs.mothquantum.com/docs/engines/qrc-train-v2) / [qrc-gen-v2](https://docs.mothquantum.com/docs/engines/qrc-gen-v2))
- Vision-Language Model: Qwen2.5-VL-7B-Instruct
- Visual Embeddings: MobileNetV3
- Image Processing: CIE Lab / OpenCV / Pillow
- Image Corpus: NASA/JPL archival artwork and public-domain retro-futuristic collections

### Project Concept

```
Quantum Reservoir Computing
            +
Historical Metadata
            +
Vision-Language Models
            +
Computational Mosaic Art
            +
Temporal Dynamics
            │
            ▼
Non-Linear Historical Visualisation
```

From timelines to trajectories: using quantum dynamics to explore how humanity has imagined the future.

