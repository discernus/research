# Moral Foundations Theory Framework v6.0

**Version**: 6.0  
**Status**: Active  
**Major Change**: Return to JSON Architecture with Enhanced Synthesis Integration

A Discernus framework for analyzing moral reasoning patterns in political discourse using Moral Foundations Theory. This framework evaluates six moral foundation pairs with advanced tension analysis capabilities, providing comprehensive insights into moral strategic contradictions and rhetorical coherence patterns.

## Moral Foundations Theory Core Analysis

### **Six Foundation Pairs: Independent Scoring with Tension Analysis**

**Individualizing Foundations (Foundation Pairs 1-2)**:
1. **Care** (0.0-1.0): Compassion, protection, suffering prevention
2. **Harm** (0.0-1.0): Cruelty concern, violence prevention, victim advocacy

3. **Fairness** (0.0-1.0): Justice, equality, proportional treatment  
4. **Cheating** (0.0-1.0): Unfairness concern, exploitation prevention, corruption focus

**Binding Foundations (Foundation Pairs 3-5)**:
5. **Loyalty** (0.0-1.0): Group cohesion, fidelity, solidarity
6. **Betrayal** (0.0-1.0): Group abandonment concern, treachery prevention

7. **Authority** (0.0-1.0): Hierarchy respect, tradition, legitimate order
8. **Subversion** (0.0-1.0): Rebellion concern, tradition undermining, hierarchy disruption

9. **Sanctity** (0.0-1.0): Sacred preservation, purity, transcendence  
10. **Degradation** (0.0-1.0): Contamination concern, profane prevention, sacred violation

**Liberty Foundation (Foundation Pair 6)**:
11. **Liberty** (0.0-1.0): Freedom, autonomy, self-determination
12. **Oppression** (0.0-1.0): Control concern, domination prevention, freedom protection

### **Moral Tension Analysis Enhancement**

**Moral Strategic Contradiction Index (MSCI)**: Quantifies overall moral tension across all foundation pairs, revealing patterns of moral rhetorical coherence or contradiction.

**Foundation Pair Tensions**: Each pair generates a tension score measuring the degree of simultaneous emphasis on opposing moral concerns.

### **Scoring Protocol**

For each foundation:
- **Score** (0.0-1.0): Intensity of moral foundation emphasis
- **Salience** (0.0-1.0): Rhetorical prominence and emphasis weight
- **Confidence** (0.0-1.0): Analytical confidence in the assessment

**Evidence Requirements**: 1-2 strongest supporting quotes per foundation with context classification.

## Framework Implementation

This framework employs the THIN philosophy: LLMs provide moral reasoning intelligence, while synthesis code handles mathematical calculations. The analysis focuses on raw dimensional scoring and evidence extraction, with all tension calculations performed by explicit code execution.

<details><summary>Machine-Readable Configuration</summary>

{
  "name": "moral_foundations_theory_v6",
  "version": "v6.0",
  "display_name": "Moral Foundations Theory Framework v6.0",
  "analysis_variants": {
    "default": {
      "description": "Complete salience-weighted moral foundation analysis with tension pattern quantification.",
      "analysis_prompt": "You are an expert moral psychology analyst with deep knowledge of Moral Foundations Theory. Your task is to analyze the text using the Moral Foundations Theory Framework v6.0, which provides comprehensive moral reasoning pattern analysis. The framework evaluates 6 foundation pairs (12 total foundations): Care/Harm, Fairness/Cheating, Loyalty/Betrayal, Authority/Subversion, Sanctity/Degradation, and Liberty/Oppression. For each of the 12 foundations, provide: (1) score (0.0-1.0) representing intensity of moral foundation emphasis, (2) salience (0.0-1.0) representing rhetorical prominence, (3) confidence (0.0-1.0) representing analytical confidence. Include the strongest 1-2 quotes as evidence for each foundation with context classification. Your response must be a single, valid JSON object containing all required nested structures. Provide ONLY raw dimensional scores, salience, confidence, and evidence - NO calculations or derived metrics. The synthesis pipeline will calculate all tension scores and the Moral Strategic Contradiction Index using explicit mathematical formulas."
    },
    "descriptive_only": {
      "description": "Simplified moral foundation analysis focusing on core moral patterns without tension calculations.",
      "analysis_prompt": "You are an expert moral psychology analyst. Analyze the text using simplified Moral Foundations Theory, focusing on the 6 foundation pairs: Care/Harm, Fairness/Cheating, Loyalty/Betrayal, Authority/Subversion, Sanctity/Degradation, Liberty/Oppression. For each foundation, provide score (0.0-1.0), salience (0.0-1.0), and confidence (0.0-1.0). Include 1-2 supporting quotes. Return a single JSON object with the required nested structures. Provide only raw scores - no calculations."
    }
  },
  "dimension_groups": {
    "individualizing_foundations": ["care", "harm", "fairness", "cheating"],
    "binding_foundations": ["loyalty", "betrayal", "authority", "subversion", "sanctity", "degradation"],
    "liberty_foundation": ["liberty", "oppression"],
    "foundation_pairs": ["care_harm", "fairness_cheating", "loyalty_betrayal", "authority_subversion", "sanctity_degradation", "liberty_oppression"]
  },
  "calculation_spec": {
    "moral_foundation_tensions": {
      "care_harm_tension": "min(care_score, harm_score) * abs(care_salience - harm_salience)",
      "fairness_cheating_tension": "min(fairness_score, cheating_score) * abs(fairness_salience - cheating_salience)",
      "loyalty_betrayal_tension": "min(loyalty_score, betrayal_score) * abs(loyalty_salience - betrayal_salience)",
      "authority_subversion_tension": "min(authority_score, subversion_score) * abs(authority_salience - subversion_salience)",
      "sanctity_degradation_tension": "min(sanctity_score, degradation_score) * abs(sanctity_salience - degradation_salience)",
      "liberty_oppression_tension": "min(liberty_score, oppression_score) * abs(liberty_salience - oppression_salience)"
    },
    "moral_strategic_contradiction_index": "(care_harm_tension + fairness_cheating_tension + loyalty_betrayal_tension + authority_subversion_tension + sanctity_degradation_tension + liberty_oppression_tension) / 6",
    "salience_weighting_explanation": "All tension calculations use salience-weighted formulas to capture rhetorical emphasis patterns."
  },
  "reliability_rubric": {
    "cronbachs_alpha": {
      "excellent": [0.80, 1.0],
      "good": [0.70, 0.79],
      "acceptable": [0.60, 0.69],
      "poor": [0.0, 0.59]
    },
    "notes": "Defines quality thresholds for framework reliability. The Synthesis Agent uses this for automated fit assessment."
  },
  "output_contract": {
    "schema": {
      "worldview": "string",
      "scores": "object",
      "evidence": "object", 
      "reasoning": "object",
      "salience_ranking": "array",
      "moral_foundation_summary": "object"
    },
    "structured_data_requirements": {
      "scores": {
        "description": "Nested object containing ONLY raw dimensional scores (NO calculated metrics)",
        "structure": {
          "dimensions": {
            "care": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "harm": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "fairness": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "cheating": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "loyalty": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "betrayal": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "authority": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "subversion": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "sanctity": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "degradation": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "liberty": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"},
            "oppression": {"score": "number (0.0-1.0)", "salience": "number (0.0-1.0)", "confidence": "number (0.0-1.0)"} 
          },
          "metadata": {
            "total_dimensions": "number",
            "analysis_completeness": "number (0.0-1.0)"
          }
        }
      },
      "evidence": {
        "description": "Nested object containing structured evidence data for audit and replication",
        "structure": {
          "by_dimension": {
            "care": [{"quote_id": "string", "quote_text": "string", "confidence": "number (0.0-1.0)", "context_type": "string", "salience_justification": "string"}],
            "harm": ["array of evidence objects"],
            "fairness": ["array of evidence objects"],
            "cheating": ["array of evidence objects"],
            "loyalty": ["array of evidence objects"],
            "betrayal": ["array of evidence objects"],
            "authority": ["array of evidence objects"],
            "subversion": ["array of evidence objects"],
            "sanctity": ["array of evidence objects"],
            "degradation": ["array of evidence objects"],
            "liberty": ["array of evidence objects"],
            "oppression": ["array of evidence objects"]
          },
          "metadata": {
            "total_quotes": "number",
            "average_confidence": "number"
          }
        }
      }
    },
    "instructions": "IMPORTANT: Your response MUST be a single, valid JSON object containing all required fields with the nested structures specified above. The salience_ranking should be an ordered array of objects, each containing 'foundation', 'salience_score', and 'rank'. All numerical scores must be between 0.0 and 1.0. DO NOT perform any mathematical calculations or compute derived metrics - provide ONLY raw dimensional scores, salience, confidence, and evidence. Tension calculations and MSCI will be computed by the synthesis pipeline using explicit mathematical formulas."
  }
}
```

</details>