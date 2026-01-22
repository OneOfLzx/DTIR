<div align="center">

# Reasoning Text-to-Image Retrieval with Large Language Models and Digital Twin Representations

### 📄 Published in **Knowledge-Based Systems (KBS)**, 2026: [Paper Link (Elsevier)](https://authors.elsevier.com/a/1mUOn3OAb9KaUy)

---

</div>

<div align="center">
  <img src="figures/architecture.jpg" alt="Architecture Diagram" width="80%">
</div>

## RT2I Dataset

The **RT2I** dataset is located in the `data/RT2I` directory, which contains both image data and reasoning-based queries.

```
data/
└── RT2I/
    ├── image.zip
    └── query_info.json
```


## Setup

1. Create a Python environment:
```bash
conda create -n dtir python=3.10.16
conda activate dtir
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download required codes and checkpoints:
- OWL-ViT 2
- Depth-Anything 2
- SAM 2

## Usage

### Generate DT Representations

```bash
./script/digital_twins_generation.sh
```

Required parameters:
- `query_info`: Text query for image retrieval
- `image_dir`: Directory containing input images
- `output_digital_twins_dir`: Output directory for digital twin representations
- `owlvit_checkpoint_path`: Path to OWL-ViT checkpoint
- `depth_anything_checkpoint_path`: Path to Depth-Anything checkpoint
- `sam_config_path`: Path to SAM config
- `sam_checkpoint_path`: Path to SAM checkpoint
- `gpu_id`: GPU device ID (default: 0)

### Text-to-Image Retrieval

```bash
./script/text_to_image_retrieval.sh
```

Required parameters:
- `query_info`: Text query for image retrieval
- `image_dir`: Directory containing images to search
- `digital_twins_dir`: Directory containing digital twin representations
- `result_output_dir`: Output directory for results
- `gpu_id`: GPU device ID (default: 0)

Optional parameters:
- `scoring_llm_provider`: LLM provider for scoring (default: doubao)
- `scoring_llm_model`: Model for scoring (default: lite)
- `ranking_llm_provider`: LLM provider for ranking (default: deepseek)
- `ranking_llm_model`: Model for ranking (default: v3)
- `object_retrieval_llm_provider`: LLM provider for object retrieval (default: deepseek)
- `object_retrieval_llm_model`: Model for object retrieval (default: v3)

API Key:
- Set API Key for LLMs in `llm_api.py`

## Citation

If you find this work useful in your research, please consider citing:

> **Reasoning Text-to-Image Retrieval with Large Language Models and Digital Twin Representations** > Zexu Lin, Dell Zhang, Yiqing Shen, and Xuelong Li  
> *Knowledge-Based Systems*, Volume 336, 2026.  
> [[Paper Link]](https://authors.elsevier.com/a/1mUOn3OAb9KaUy) [[DOI]](https://doi.org/10.1016/j.knosys.2026.115313)

```bibtex
@article{LIN2026115313,
  title = {Reasoning text-to-image retrieval with large language models and digital twin representations},
  journal = {Knowledge-Based Systems},
  volume = {336},
  pages = {115313},
  year = {2026},
  doi = {10.1016/j.knosys.2026.115313},
  author = {Zexu Lin and Dell Zhang and Yiqing Shen and Xuelong Li}
}
