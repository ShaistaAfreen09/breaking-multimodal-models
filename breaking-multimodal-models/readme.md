#  Breaking Multimodal Models: Adversarial Attack Analysis

## Overview
This project investigates the robustness of **Large Multimodal Models (LMMs)** by applying adversarial attacks and analyzing their failure behavior.

The goal is to identify conditions under which vision-language models produce degraded or incorrect outputs.



##  Objectives
- Evaluate how multimodal models respond to adversarial inputs  
- Implement multiple attack strategies  
- Measure changes in model outputs using similarity metrics  
- Analyze patterns in model failure  



##  Model Used
- **Primary Model**: BLIP (Bootstrapped Language Image Pretraining)
- **Reference Model**: Qwen2-VL-7B-Instruct  

> Note: BLIP was used for experimentation due to hardware constraints (Google Colab environment)


##  Attack Methods

### Perturbation-Based Attacks
- Gaussian Noise  
- Brightness & Contrast Adjustment  
- Color Shift  
- Blur  

### Patch-Based Attacks
- Random Patch  
- White Patch  



## 📊 Results

| Attack Type           | Success |
|----------------------|--------|
| Gaussian Noise       | ✅ True |
| Brightness/Contrast  | ❌ False |
| Color Shift          | ❌ False |
| Blur                 | ❌ False |
| Random Patch         | ❌ False |
| White Patch          | ❌ False |

### Key Metrics
- Total Attacks: **6**  
- Successful Attacks: **1**  
- Success Rate: **16.7%**



##  Key Findings
- Pixel-level perturbations significantly impact model output quality  
- Gaussian noise was the most effective attack  
- Structural attacks (blur, patches) had limited impact  
- The model preserved object identity but lost descriptive accuracy  



##  Case Analysis

### Successful Attack (Gaussian Noise)
- Output changed significantly  
- Semantic details degraded  
- Similarity Score: ~0.22  

### Failed Attack (Blur / Patch)
- Output remained consistent  
- Similarity Score: ~0.9  



##  Project Structure
- breaking-multimodal-models/
│
- ├── notebook/
│ └── LMM_RESEARCH.ipynb
- ├── results/
│ ├── attack_results.csv
│ ├── attack_results.json
│
- └── README.md
## Conclusion

This study demonstrates that multimodal models, despite strong performance, are vulnerable to adversarial perturbations. Understanding these vulnerabilities is essential for building robust AI systems.
