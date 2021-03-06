# Promoting Coordination Through Policy Regularization in Multi-Agent Deep Reinforcement Learning

[Link to the paper](https://papers.nips.cc/paper/2020/hash/b628386c9b92481fab68fbf284bd6a64-Abstract.html)

## To cite
```
@article{roy2020promoting,
  title={Promoting Coordination through Policy Regularization in Multi-Agent Deep Reinforcement Learning},
  author={Roy, Julien and Barde, Paul and Harvey, F{\'e}lix and Nowrouzezahrai, Derek and Pal, Chris},
  journal={Advances in Neural Information Processing Systems},
  volume={33},
  year={2020}
}
```

## Online vsualisations

Visualisations of rollouts using MADDPG + CoachReg are available online:
[https://sites.google.com/view/marl-coordination/](https://sites.google.com/view/marl-coordination/)
 
## Requirements

Open a terminal inside `PromotingCoordination_NeurIPS2020_supplementaryMaterials`, then:
* Install a conda environment with Python 3.7: `conda create --name test_env python=3.7`
* Install the regular dependencies: `pip install -r requirements.txt`
* Install the external dependencies: `pip install -e external_dependencies/multiagent_particle_environment_fork`

## Toy-experiment

To reproduce Figure 1. of Section 3 (coordinated vs non-coordinated policy space on toy experiment) run:
```
cd code/toy_experiment && python toy_main.py
```

## Main experiments

#### To visualize trained_models

1. Go in the code folder of the desired algorithm:
    * example1: `cd code/continuous_control/coach`
    * example2: `cd code/discrete_control/coach`

2. Run `evaluate.py` with the desired arguments:
    * example1: `python evaluate.py --root ../../../trained_models/continuous_control/chase --storage_name PB6_2bc3c27_5f7a15b_CoachMADDPG_chase_retrainBestPB3_review`
    * example2: `python evaluate.py --root ../../../trained_models/discrete_control/3v2football --storage_name Ju25_2667341_5e972b5_CoachMADDPG_3v2football_retrainBestJu24_benchmarkv3`

**Note:** For `discrete_control/3v2football` you might need to define the following environment variables for the rendering to work properly: `export PYTHONUNBUFFERED=1 && export MESA_GL_VERSION_OVERRIDE=3.2 && export MESA_GLSL_VERSION_OVERRIDE=150`

#### To train new models

1. Go in the code folder of the desired algorithm:
    * example1: `cd code/continuous_control/coach`
    * example2: `cd code/discrete_control/baselines`

2. Run `main.py` with the desired arguments:
    * example1: `python main.py --env_name spread --agent_alg CoachMADDPG`
    * example2: `python main.py --env_name 3v2football --agent_alg MADDPG`

Run `python main.py --help` for all options.
