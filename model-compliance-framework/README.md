# Analysis of AI models using our custom weighted Framework

## Scoring System (100 Points Total)

| Section               | Weight  | Key Checks                                                           |
| --------------------- | ------- | -------------------------------------------------------------------- |
| **Safety Evaluation** | **25%** | Jailbreak (4), Hallucinations (4), Deception (4), Bias (3), etc.     |
| **Critical Risk**     | **20%** | CBRN (5), Cyber Risk (5), Harmful Manipulation (4), Child Safety (4) |
| **Model Details**     | **15%** | Architecture (4), Model Overview (3), Version (2), Distribution (2)  |
| **Model Data**        | **15%** | Training Dataset (7), Data Processing (6), Knowledge Count (2)       |
| **Intended Use**      | **10%** | Primary Uses (5), Out-of-scope Cases (3), Primary Users (2)          |
| **Model I/O**         | **6%**  | Inputs (2), Outputs (2), Token Count (2)                             |
| **Implementation**    | **5%**  | Hardware (2), Software (2), Sustainability (1)                       |
| **Risk Mitigations**  | **4%**  | Mitigation Strategies (4)                                            |

**Why Weighted Scoring?**

- Not all checks are equally important
- Safety & risk checks matter more than basic metadata
- Weighted scores reflect real-world compliance priorities
- Better strategic decision-making for improvements

## Generated Visualizations

### 1. **compliance_overview.png** - Main Dashboard

A comprehensive 4-panel overview showing:

- **Top 20 Models**: Bar chart ranking models by compliance percentage
- **Compliance by Provider**: Aggregated scores for each AI provider
- **Compliance by Section**: Performance across the 8 framework sections
- **Distribution**: Histogram showing the spread of compliance scores

### 2. **compliance_heatmap.png** - Section-wise Analysis

A detailed heatmap (48 models × 8 sections) showing:

- Which models excel in which sections
- Patterns of compliance across different framework areas
- Color-coded for easy identification (Green = compliant, Red = non-compliant)

### 3. **compliance_detailed_matrix.png** - Complete Granular View

An ultra-detailed heatmap (48 models × 36 checks) showing:

- Every single compliance check for every model
- 1,728 individual data points visualized
- Ideal for identifying specific areas where models fail

### 4. **check_performance_analysis.png** - Challenge Identification

Two side-by-side analyses showing:

- **15 Most Challenging Checks**: Areas where most models struggle
- **15 Best Performing Checks**: Areas where models generally comply well

## Key Findings

📊 **Overall**: 68% average compliance rate across 48 models and 36 checks

🏆 **Top Performers**:

- Claude 3 Opus (88.9%)
- GPT-4.1 (86.1%)
- Gemini 3 Pro (86.1%)

⚠️ **Areas of Concern**:

- Safety Evaluation section has only 46.3% compliance
- Critical Risk section has 55.0% compliance
- "Sycophancy" check has only 6.2% compliance across all models

🎯 **Best Compliance**: Model Details (84.3%) and Intended Use (81.9%) sections

