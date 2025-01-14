# Aligning Consistency Models by Preference Optimization

This repository presents a novel approach to aligning consistency models using preference optimization techniques. We extend the Direct Preference Optimization (DPO) framework to consistency models, addressing unique challenges in their alignment process.

## Overview

This project introduces a novel framework for aligning consistency models with human preferences through an extension of Direct Preference Optimization (DPO). We tackle the unique challenges posed by consistency models' deterministic nature and develop efficient approximation methods for handling intractable distributions. Our approach maintains model consistency while effectively incorporating human feedback, bridging the gap between powerful generative capabilities and desired behavioral alignment.

Consistency models represent a powerful class of generative models that can be viewed as RL policies. Our work provides a framework for aligning these models with human preferences while maintaining their consistency properties.

### Key Features

- Formulation of consistency models as RL policies
- Extension of DPO framework to consistency models
- Novel solutions for handling deterministic mappings
- Efficient approximation methods for intractable distributions
- Combined loss function balancing preference optimization and consistency

## Technical Details

### Model Architecture

The framework models the consistency model as an RL policy, details explained in `CMDPO.pdf`.

### Key Innovations

1. **Handling Deterministic Mappings**: We propose multiple approaches to address the challenges of deterministic mappings in the final step:
   - Smoothing techniques
   - Alternative f-Divergence regularization
   - Primal-dual methods
   - Constraint-based solutions

2. **Distribution Approximation**: Novel methods for approximating intractable distributions p(xτt|xτH+1, c)

3. **Combined Loss Function**: 
   ```
   L = LDPO + λLcon
   ```



## Citation

If you use this work in your research, please cite:

```
[Citation to be added after publication]
```

## Authors

- Amirabbas Afzali
- Borna Khodabandeh
- Ashkan Majidi
- Zahra Maleki
- Asemaneh Nafe

## Contact

Email: [borna710kh@gmail.com](mailto:borna710kh@gmail.com)