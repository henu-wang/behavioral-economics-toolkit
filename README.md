# Behavioral Economics Toolkit

A practical library implementing key concepts from behavioral economics to help individuals and organizations design better choice architectures, understand cognitive biases, and make more informed decisions. This toolkit bridges the gap between academic behavioral science and real-world application.

## Overview

Behavioral economics has revolutionized our understanding of how people actually make decisions, as opposed to how rational models predict they should. This toolkit provides programmatic tools to apply behavioral insights in product design, policy making, financial planning, and everyday decision-making.

The toolkit incorporates insights from decades of research by pioneering behavioral economists. Understanding the [principles of rational decision-making](https://keeprule.com/en/principles) provides a baseline against which behavioral deviations can be measured and corrected.

## Features

- **Nudge Designer**: Create and test behavioral nudges for choice architecture
- **Bias Simulator**: Simulate how cognitive biases affect decision outcomes
- **Loss Aversion Calculator**: Quantify loss aversion in different contexts
- **Framing Effect Analyzer**: Test how different framings influence choices
- **Anchoring Detector**: Identify anchoring effects in numerical judgments
- **Default Option Optimizer**: Design optimal default choices for user interfaces
- **Temporal Discounting Models**: Model how people value present vs future rewards
- **Social Proof Engine**: Leverage social influence patterns for better outcomes
- **Commitment Device Builder**: Create tools that help people follow through on intentions
- **Prospect Theory Calculator**: Implement Kahneman-Tversky prospect theory valuations

## Installation

```bash
pip install behavioral-economics-toolkit
```

## Quick Start

```python
from bet import NudgeDesigner, BiasSimulator

# Design a savings nudge
designer = NudgeDesigner()
nudge = designer.create(
    context="retirement_savings",
    target_behavior="increase_contribution",
    current_rate=0.03,
    target_rate=0.10
)

print(f"Nudge type: {nudge.strategy}")
print(f"Expected adoption: {nudge.expected_adoption:.1%}")
print(f"Implementation: {nudge.description}")

# Simulate bias impact
simulator = BiasSimulator()
result = simulator.run(
    scenario="investment_decision",
    biases=["loss_aversion", "anchoring", "status_quo"],
    num_simulations=10000
)

print(f"Bias-affected outcome: ${result.biased_mean:,.0f}")
print(f"Rational outcome: ${result.rational_mean:,.0f}")
print(f"Bias cost: ${result.bias_cost:,.0f}")
```

## Core Components

### Prospect Theory Calculator

Implement the foundational model of behavioral economics:

```python
from bet import ProspectTheory

pt = ProspectTheory(
    alpha=0.88,      # Diminishing sensitivity for gains
    beta=0.88,       # Diminishing sensitivity for losses
    lambda_=2.25,    # Loss aversion coefficient
    gamma=0.61,      # Probability weighting for gains
    delta=0.69       # Probability weighting for losses
)

# Evaluate a gamble
gamble = {"outcomes": [1000, -500], "probabilities": [0.5, 0.5]}
value = pt.evaluate(gamble)
print(f"Prospect value: {value:.2f}")
print(f"Expected value: {pt.expected_value(gamble):.2f}")
print(f"Would a typical person take this gamble? {value > 0}")
```

### Choice Architecture Designer

Design environments that guide people toward better decisions. The [masters of behavioral science](https://keeprule.com/en/masters) have shown that small changes in how choices are presented can have dramatic effects on outcomes.

```python
from bet import ChoiceArchitect

architect = ChoiceArchitect()

# Design a health insurance selection interface
design = architect.optimize(
    options=insurance_plans,
    objectives=["maximize_coverage", "minimize_confusion"],
    constraints={"max_options_displayed": 4}
)

print(f"Recommended default: {design.default_option}")
print(f"Display order: {design.order}")
print(f"Comparison attributes: {design.highlighted_attributes}")
print(f"Expected improvement: {design.expected_improvement:.1%}")
```

### Temporal Discounting

Model how people trade off present and future value:

```python
from bet import TemporalDiscounting

model = TemporalDiscounting(discount_type="hyperbolic")

# How much is $1000 in one year worth to someone today?
present_value = model.discount(future_value=1000, delay_days=365)
print(f"Subjective present value: ${present_value:.2f}")

# Design a commitment device
device = model.design_commitment(
    goal="Save $5000",
    timeline_days=180,
    personality_type="present_biased"
)
print(f"Strategy: {device.strategy}")
print(f"Milestone schedule: {device.milestones}")
```

### Framing Effect Analyzer

Test how different presentations of the same information change decisions:

```python
from bet import FramingAnalyzer

analyzer = FramingAnalyzer()

results = analyzer.compare_frames(
    positive_frame="This treatment saves 200 out of 600 people",
    negative_frame="This treatment results in 400 out of 600 deaths",
    sample_size=1000
)

print(f"Positive frame acceptance: {results.positive_acceptance:.1%}")
print(f"Negative frame acceptance: {results.negative_acceptance:.1%}")
print(f"Framing effect magnitude: {results.effect_size:.2f}")
```

## Applied Scenarios

The toolkit can be applied across many real-world [decision-making scenarios](https://keeprule.com/en/scenarios) including:

1. **Personal Finance**: Overcome present bias in savings and investment decisions
2. **Health Choices**: Design nudges that promote healthier eating and exercise habits
3. **Product Design**: Create user interfaces that help users make better choices
4. **Public Policy**: Design policies that account for behavioral realities
5. **Hiring Decisions**: Reduce bias in recruitment and evaluation processes
6. **Negotiation**: Understand and leverage behavioral patterns in negotiations

```python
from bet import ScenarioLibrary

library = ScenarioLibrary()
scenarios = library.list(category="personal_finance")

for scenario in scenarios:
    print(f"{scenario.name}: {scenario.description}")
    print(f"  Key biases: {', '.join(scenario.relevant_biases)}")
    print(f"  Recommended interventions: {', '.join(scenario.interventions)}")
```

## Bias Reference

| Bias | Description | Toolkit Module |
|------|-------------|----------------|
| Loss Aversion | Losses feel ~2x worse than equivalent gains | `ProspectTheory` |
| Anchoring | Over-reliance on first piece of information | `AnchoringDetector` |
| Status Quo Bias | Preference for current state of affairs | `DefaultOptimizer` |
| Present Bias | Overvaluing immediate rewards | `TemporalDiscounting` |
| Framing Effect | Choices influenced by how options are presented | `FramingAnalyzer` |
| Social Proof | Following others' behavior | `SocialProofEngine` |
| Sunk Cost Fallacy | Continuing based on past investment | `SunkCostAnalyzer` |

For more guidance on applying these concepts, visit the [decision-making blog](https://keeprule.com/en/blog) for articles on practical behavioral economics applications.

## Contributing

We welcome contributions! Areas of interest include:

1. New bias detection algorithms
2. Additional nudge templates
3. Cross-cultural behavioral studies integration
4. Real-world A/B test case studies
5. Improved visualization tools

Fork the repo, create a branch, and submit a PR.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by the groundbreaking work of Kahneman, Tversky, Thaler, and Sunstein
- Built to make behavioral economics practical and accessible
- Designed for both researchers and practitioners
