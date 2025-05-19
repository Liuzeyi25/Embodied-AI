具身智能论文阅读
Created on 2025/3/29

# VLAs
- OpenVLA: An Open-Source Vision-Language-Action Model. [arXiv](https://arxiv.org/pdf/2406.09246). [2025/3/22]
- **(OpenVLA-OFT)** Fine-Tuning Vision-Language-Action Models: Optimizing Speed and Success. [arXiv](https://arxiv.org/html/2502.19645v1) [2025/04/11]
- π0: A Vision-Language-Action Flow Model for General Robot Control [paper](https://www.physicalintelligence.company/download/pi0.pdf) [web](https://www.physicalintelligence.company/blog/pi0)
- **[CVPR'25]** CrayonRobo: Object-Centric Prompt-Driven Vision-Language-Action Model for Robotic Manipulation. [arxiv](https://arxiv.org/pdf/2505.02166)
> vision prompt & multi-modal prompt, including contact point, z-direction, y-direction, moving direction, which can be combined as a high-level trajectory.
- Interleave-VLA: Enhancing Robot Manipulation with Interleaved Image-Text Instructions [arXiv](https://arxiv.org/pdf/2505.02152)
> Develop an automatic pipeline that converts text-only instructions from real-world datasets in Open X-Embodiment into interleaved image-text instructions
- UniVLA: Learning to Act Anywhere with Task-centric Latent Actions [arXiv](https://arxiv.org/pdf/2505.06111)
> Train an inverse dynamic model to predict action using o_t and o_t+1, then map the action to the codebook. This paper divides the action into task-irrelevant action and task-centric action. Learning the latent action representation through VQ-VAE

# Reasoning
- Robotic Control via Embodied Chain-of-Thought Reasoning. [arXiv](https://arxiv.org/pdf/2407.08693) [2025/3/25]
- RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control [arXiv](https://arxiv.org/pdf/2307.15818) [2025/3/28]
- Open X-Embodiment: Robotic Learning Datasets and RT-X Models. [paper](https://openreview.net/pdf?id=zraBtFgxT0) [2025/3/31]
- SpatialVLM: Endowing Vision-Language Models with Spatial Reasoning Capabilities. [arXiv](https://arxiv.org/pdf/2401.12168)
- EmbodiedGPT: Vision-Language Pre-Training via Embodied Chain of Thought. [paper](https://proceedings.neurips.cc/paper_files/paper/2023/file/4ec43957eda1126ad4887995d05fae3b-Paper-Conference.pdf) [2025/4/3]
- Any-point Trajectory Modeling for Policy Learning. [arXiv](https://arxiv.org/pdf/2401.00025)
- **[CVPR'25]** CoT-VLA: Visual Chain-of-Thought Reasoning for Vision-Language-Action Models. [arXiv](https://arxiv.org/pdf/2503.22020) [web](https://cot-vla.github.io/) [2025/4/2]
> vision cot，以预测未来视觉观察作为子目标，并生成动作
- Do As I Can, Not As I Say: Grounding Language in Robotic Affordances [arXiv](https://arxiv.org/pdf/2204.01691)
- **[ICLR'24]** TEXT2REWARD: REWARD SHAPING WITH LANGUAGE MODELS FOR REINFORCEMENT LEARNING [arXiv](https://arxiv.org/pdf/2309.11489)
> dense reward

# Reinforcement Learning
- Refined Policy Distillation: From VLA Generalists to RL Experts [arXiv](https://arxiv.org/pdf/2503.05833) [2025/04/14]
> Distilling knowledge from VLAs to RL expert model.
- Towards Autonomous Reinforcement Learning for Real-World Robotic Manipulation with Large Language Models [arXiv](https://arxiv.org/pdf/2503.04280?) [2025/04/17]
- **[RSS'25]** ConRFT: A Reinforced Fine-tuning Method for VLA Models via Consistency Policy. [arXiv](https://arxiv.org/pdf/2502.05450)
- Reward Generation via Large Vision-Language Model in Offline Reinforcement Learning [arXiv](https://arxiv.org/pdf/2504.08772v1)
- **[NIPS'24]** !! Fine-Tuning Large Vision-Language Models as Decision-Making Agents via Reinforcement Learning [arXiv](https://proceedings.neurips.cc/paper_files/paper/2024/file/c848b7d3adc08fcd0bf1df3101ba6728-Paper-Conference.pdf)
> PPO finetune VLM, generate action through structural prompt, optimize with a simple PPO framework. **Reward only from env**.
- Improving Vision-Language-Action Model with Online Reinforcement Learning [arXiv](https://arxiv.org/pdf/2501.16664)
> RL+SFT alternate optimization
- Efficient Online Reinforcement Learning with Offline Data [arXiv](https://proceedings.mlr.press/v202/ball23a/ball23a.pdf)
- IN–RIL: Interleaved Reinforcement and Imitation Learning for Policy Fine-tuning. [arXiv](https://arxiv.org/pdf/2505.10442)


# Foudation Models
- R3M: A Universal Visual Representation for Robot Manipulation [arXiv](https://arxiv.org/pdf/2203.12601) [2025/04/11]
> A vision representation foundation model for robotics manipulation

# Benchmark
- **[NeurIPS'23]** LIBERO: Benchmarking Knowledge Transfer for Lifelong Robot Learning [paper](https://proceedings.neurips.cc/paper_files/paper/2023/file/8c3c666820ea055a77726d66fc7d447f-Paper-Datasets_and_Benchmarks.pdf)
> LIBERO-SPATIAL\LIBERO-OBJECT\LIBERO-GOAL 各包含10个任务，用于测试空间、物体、任务目标的迁移<br>
> LIBERO-SPATIAL -- 同一个碗在不同场景中具有不同的空间关系<br>
> LIBERO-OBJECT -- 拾取并放置一个独特的物体<br>
> LIBERO-GOAL -- <br>
> LIBERO-100 -- 包含100个任务，分为LIBERO-90(90 short horizon tasks)，LIBERO-LONG(10 long-horizon tasks)
