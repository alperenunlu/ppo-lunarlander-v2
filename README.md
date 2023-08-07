---
library_name: stable-baselines3
tags:
- LunarLander-v2
- deep-reinforcement-learning
- reinforcement-learning
- stable-baselines3
model-index:
- name: PPO
  results:
  - task:
      type: reinforcement-learning
      name: reinforcement-learning
    dataset:
      name: LunarLander-v2
      type: LunarLander-v2
    metrics:
    - type: mean_reward
      value: 244.16 +/- 18.09
      name: mean_reward
      verified: false
---

# **PPO** Agent playing **LunarLander-v2**
This is a trained model of a **PPO** agent playing **LunarLander-v2**
using the [stable-baselines3 library](https://github.com/DLR-RM/stable-baselines3).

## Usage (with Stable-baselines3)

```python
from stable_baselines3 import PPO
from stable_baselines3.common.monitor import Monitor
from huggingface_sb3 import load_from_hub

repo_id = "alperenunlu/PPO-LunarLander-v2"
filename = "PPO-LunarLander-v2.zip"

checkpoint = load_from_hub(repo_id, filename)
model = PPO.load(checkpoint, print_system_info=True)

eval_env = Monitor(gym.make("LunarLander-v2", render_mode="human"))

mean_rwd, std_rwd = evaluate_policy(model, eval_env, n_eval_episodes=10)
print(f"mean_reward: {mean_rwd}±{std_rwd}")
```


https://github.com/alperenunlu/ppo-lunarlander-v2/assets/97191996/a0acb446-95d5-43e1-8641-63e1df9e980e


