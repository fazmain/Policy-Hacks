# Weighted Framework Compliance Scoring Guide

## Overview

The notebook `framework_visual.ipynb` now implements your custom **weighted scoring system** where different framework checks have different importance levels based on their real-world significance.

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

## Key Differences: Weighted vs Unweighted

### Unweighted Scoring (Old Method)

- ✅ All 36 checks count equally
- ✅ Score = % of checks passed
- ❌ Treats "Paper links" same as "Training Dataset"
- ❌ Doesn't reflect real importance
- **Example**: Passing 18/36 checks = 50% (regardless of which checks)

### Weighted Scoring (New Method)

- ✅ Each check worth its importance value
- ✅ Score = Points earned / 100 total points
- ✅ High-impact checks matter more
- ✅ Reflects compliance priorities
- **Example**: Passing low-value checks ≠ passing high-value checks

## Example Scenario

**Model A**: Passes 20 checks (55.6% unweighted)

- Includes all safety checks (25 pts)
- Includes critical risk checks (20 pts)
- Missing some metadata
- **Weighted Score: 72/100 (72%)**

**Model B**: Passes 20 checks (55.6% unweighted)

- Has all metadata and documentation
- Missing most safety checks
- Missing critical risk assessments
- **Weighted Score: 38/100 (38%)**

Both have same unweighted score, but Model A is far more compliant where it matters!

## How to Use the Notebook

1. **Run All Cells** in `framework_visual.ipynb`

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

## Questions?

- **Q: Why is my weighted score different from unweighted?**
  A: Weighted scoring reflects which checks you pass. Passing high-value checks increases your score more than passing low-value ones.

- **Q: Should I use weighted or unweighted for reporting?**
  A: Use **weighted** for strategic decisions and prioritization. Use unweighted only if you need simple "% of checks passed" metrics.

- **Q: Can I change the weights?**
  A: Yes! Edit Cell 1 in the notebook to adjust any check or section weights.

- **Q: What's a "good" weighted score?**
  A:
  - 80-100%: Strong compliance (all critical areas covered)
  - 60-80%: Moderate compliance (some gaps in important areas)
  - <60%: Weak compliance (missing critical checks)

---

**Next Steps**: Open `framework_visual.ipynb` in Jupyter and run all cells to generate your weighted compliance analysis! 🚀
