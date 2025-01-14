# RofuncRL ASE (Adversarial Skill Embeddings)

## Algorithm 

![](../../../img/ASE2.png)

## Demos

### Pre-trained latent space model

![](../../../img/ASE3.gif)

```shell
python examples/learning_rl/example_HumanoidASE_RofuncRL.py --task HumanoidASEGetupSwordShield --motion_file reallusion_sword_shield/dataset_reallusion_sword_shield.yaml --inference
```

### Pre-trained latent space model with perturbation

You can test the robustness of the latent space model by changing to `HumanoidASEPerturbSwordShield` task (throwing boxes to the humanoid robot). It will use **the same pre-trained latent space model as previous demo**, but set the `reset` function to reset by the maximum length of the episode, rather than resetting immediately when robots fall on the ground.

![](../../../img/ASE1.gif)

```shell
python examples/learning_rl/example_HumanoidASE_RofuncRL.py --task HumanoidASEPerturbSwordShield --motion_file reallusion_sword_shield/dataset_reallusion_sword_shield.yaml --inference
```

> **Note**
> By using the pre-trained latent space model, we can train some high-level policies for complex tasks with simple task-specific reward functions.

### High-level policy learning with pre-trained latent space model (Heading)

`HumanoidASEHeadingSwordShield` task: the humanoid robot should face to the blue line and walk towards the red line.

![](../../../img/ASE5.gif)

```shell
python examples/learning_rl/example_HumanoidASE_RofuncRL.py --task HumanoidASEHeadingSwordShield --motion_file reallusion_sword_shield/RL_Avatar_Idle_Ready_Motion.npy --inference
```

### High-level policy learning with pre-trained latent space model (Location)

`HumanoidASELocationSwordShield` task: the humanoid robot should walk to the red location.

```shell
python examples/learning_rl/example_HumanoidASE_RofuncRL.py --task HumanoidASELocationSwordShield --motion_file reallusion_sword_shield/RL_Avatar_Idle_Ready_Motion.npy --inference
```

### High-level policy learning with pre-trained latent space model (Reach)

`HumanoidASEReachSwordShield` task: the humanoid robot should let the sword reach the red point.

```shell
python examples/learning_rl/example_HumanoidASE_RofuncRL.py --task HumanoidASEReachSwordShield --motion_file reallusion_sword_shield/RL_Avatar_Idle_Ready_Motion.npy --inference
```

### High-level policy learning with pre-trained latent space model (Strike)

`HumanoidASEStrikeSwordShield` task: the humanoid robot should strike the sword to the block.

![](../../../img/ASE4.gif)

```shell
python examples/learning_rl/example_HumanoidASE_RofuncRL.py --task HumanoidASEStrikeSwordShield --motion_file reallusion_sword_shield/RL_Avatar_Idle_Ready_Motion.npy --inference
```

## Baseline comparison

## Tricks

## Network update function

```{literalinclude} ../../../../rofunc/learning/RofuncRL/agents/mixline/ase_agent.py
:pyobject: ASEAgent.update_net
```