# Analysis of AI model compliance, transparency and completeness based on our proposed framework for model cards.

## 🎯 Scoring System (100 Points Total)

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


# Weighted Framework Compliance Scoring Guide

## Overview

The notebook `model-compliance-framework/analysis.ipynb` now implements your custom **weighted scoring system** where different framework checks have different importance levels based on their real-world significance.

## Scoring System Summary

**Total Framework Score: 100 Points**

| Section               | Weight        | Why This Matters                                                                        |
| --------------------- | ------------- | --------------------------------------------------------------------------------------- |
| **Safety Evaluation** | **25 points** | Critical for AI safety - includes jailbreak resistance, hallucinations, deception, bias |
| **Critical Risk**     | **20 points** | Addresses existential & serious risks - CBRN, cyber threats, manipulation               |
| **Model Details**     | **15 points** | Essential documentation - architecture, version, distribution                           |
| **Model Data**        | **15 points** | Training transparency - dataset info, processing, data sources                          |
| **Intended Use**      | **10 points** | Usage guidance - appropriate uses, users, limitations                                   |
| **Model I/O**         | **6 points**  | Technical specs - inputs, outputs, token limits                                         |
| **Implementation**    | **5 points**  | Infrastructure - hardware, software, sustainability                                     |
| **Risk Mitigations**  | **4 points**  | Safety measures implemented                                                             |

## Individual Check Weights

### Highest-Value Checks (5-7 points)

- **Training Dataset** (7 pts) - Most valuable single check
- **Training Data Processing** (6 pts) - Second highest value
- **CBRN Risks** (5 pts) - Critical safety check
- **Cyber Risk** (5 pts) - Critical security check
- **Primary Intended Uses** (5 pts) - Usage clarity

### High-Value Checks (4 points)

- Model Architecture
- Jailbreak Resistance
- Hallucinations
- Deception Behaviors
- Disallowed Content Handling
- Harmful Manipulation
- Child Safety Evaluations

### Medium-Value Checks (2-3 points)

- Model Version, Distribution, I/O specs
- Knowledge Count, Privacy Risks
- Sycophancy, Adversarial Robustness
- Various metadata fields

### Low-Value Checks (0.5-1 points)

- Model Release Date (0.5 pts)
- Paper Links (0.5 pts)
- Organization Name (1 pt)
- Refusals, Red Teaming Results (1 pt each)

## How to Use the Notebook

1. **Run All Cells** in `model-compliance-framework/analysis.ipynb`

   - Cell 1: Load data with weighted scoring
   - Cell 2: Calculate weighted compliance
   - Cell 3: Generate weighted overview dashboard
   - Cell 4: Create weighted section heatmap
   - Cell 5: Generate detailed weighted matrix
   - Cell 6: Analyze high-impact gaps
   - Cell 7: Print weighted summary statistics

2. **Generated Visualizations** (all with "\_weighted" suffix):

   - `compliance_overview_weighted.png` - Main dashboard
   - `compliance_heatmap_weighted.png` - Section-level view
   - `compliance_detailed_matrix_weighted.png` - Check-level view
   - `check_performance_weighted.png` - Impact analysis

3. **Interpreting Results**:
   - Focus on models with high **weighted** scores
   - Prioritize fixing gaps in high-weight checks
   - Use "impact analysis" to find critical improvements
   - Consider provider rankings by weighted scores

## Strategic Insights

### For Decision Makers

- **Weighted scores reflect true compliance** with your priorities
- High safety/risk compliance matters more than documentation
- Use weighted provider rankings for vendor selection
- Focus resources on high-impact compliance gaps

### For Technical Teams

- **Prioritize improvements by impact**:

  1. Fix gaps in Safety Evaluation checks (25% weight)
  2. Address Critical Risk issues (20% weight)
  3. Improve high-value training data documentation
  4. Fill in remaining checks by weight

- **ROI on compliance work**:
  - Fixing one 7-point check > Fixing seven 1-point checks
  - Safety checks deliver most value
  - Use the impact analysis chart to prioritize

## Data Requirements

The weighted scoring system expects your JSON to have this structure:

```json
{
  "model": "Model Name",
  "sections": [
    {
      "sectionId": "safety-evaluation",
      "subsectionChecks": [
        {
          "name": "Jailbreak",
          "score": 1, // 0 or 1
          "explanation": "..."
        }
      ]
    }
  ]
}
```

The notebook automatically maps check names to weights. If a check name doesn't match exactly, it defaults to 1 point (you can adjust this in Cell 1).

## Customizing Weights

To adjust the scoring system, edit the `check_weights` dictionary in Cell 1 of the notebook:

```python
check_weights = {
    'Your Check Name': points,  # Change points here
    # ...
}
```

And update `section_weights` to reflect your total section allocations.

---
