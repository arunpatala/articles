## Reward Modeling Phase
- Uses SFT model to generate answer pairs to prompts.
- Human labelers provide preferences for one answer over the other.
- Preferences assumed to derive from a latent reward model, often modeled using the Bradley-Terry (BT) model.
- The BT model formula: 
  $$
  P(x_1 \succ x_2 | p) = \frac{\exp(R^*(p, x_1))}{\exp(R^*(p, x_1)) + \exp(R^*(p, x_2))}
  $$
- Preference data used to estimate a reward model’s parameters through maximum likelihood, with the loss function: 
  $$
  L(R', \mathcal{D}) = -\mathbb{E}_{(p, x', x'') \sim \mathcal{D}}[\log \sigma(R'(p, x') - R'(p, x''))]
  $$
