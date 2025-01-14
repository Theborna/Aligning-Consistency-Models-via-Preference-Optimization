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

The framework models the consistency model as an RL policy, arriving at the following loss objective.

$$
\mathcal{L}_\text{DPO}=-\mathbb{E}_{(c,x_{\tau_{H+1}}^w,x_{\tau_{H+1}}^l)\sim\mathcal{D}, x_{\tau_{0:H}}^w\sim q_\theta(x_{\tau_{0:H}}^w|x_{\tau_{H+1}^w},c), x_{\tau_{0:H}}^l\sim q_\theta(x_{\tau_{0:H}}^l|x_{\tau_{H+1}^l},c)}
\Bigg[\log\sigma\Bigg(\beta\sum_{t=0}^H
        w(t)\Delta d(x_{\tau_t}^w, x_{\tau_t}^l, \tau_t,c;p_\theta,p_\text{ref})\Bigg)\Bigg]\\
        \Delta d(x_{\tau_t}^w, x_{\tau_t}^l, \tau_t,c;p_\theta,p_\text{ref})=d(f_\theta(x^w_{\tau_t},\tau_t,c),f_\text{ref}(x^w_{\tau_t},\tau_t,c))
        -d(f_\theta(x^l_{\tau_t},\tau_t,c),f_\text{ref}(x^l_{\tau_t},\tau_t,c))
$$

Where $w(t)=\frac{1}{\max\left\{\tau_t^2-\tau_H^2, \epsilon^2\right\}}$, with some sufficiently small $\epsilon>0$, and $q$ being an appropriate approximate. The loss can then be appropriately approximated using monte-carlo methods.


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