<div align="center">
  <img src=images/MoveToBeacon2.gif width="270px"/>
  <img src=images/CollectMineralShards2.gif width="270px">
  <img src=images/DefeatRoaches2.gif width="270px">
</div>


# PySC2 agents
This is a simple implementation of DeepMind's PySC2 RL agents. In this project, the agents are defined according to the original [paper](https://deepmind.com/documents/110/sc2le.pdf), which use all feature maps and structured information to predict both actions and arguments via an A3C algorithm.


## Requirements
- PySC2 is a learning environment of StarCraft II provided by DeepMind. It provides an interface for RL agents to interact with StarCraft II, getting observations and sending actions. You can follow the tutorial in [PySC2 repo](https://github.com/deepmind/pysc2) to install it.

- Python packages might miss: tensorflow. If `pip` is set up on your system, it can be easily installed by running
```shell
pip install tensorflow-gpu
```


## Getting Started
Clone this repo:
```shell
git clone https://github.com/xhujoy/pysc2-agents
cd pysc2-agents
```


### Testing
- Download the pretrained model from [here](https://github.com/deepmind/pysc2) and extract them to `./snapshot/`.

- Test the pretrained model:
```shell
python -m runRL --map=MoveToBeacon --training=False
```

- You will get the following results for different maps.

<table align="center">
  <tr>
    <td align="center"></td>
    <td align="center">MoveToBeacon</td>
    <td align="center">CollectMineralShards</td>
    <td align="center">DefeatRoaches</td>
  </tr>
  <tr>
    <td align="center">Mean Score</td>
    <td align="center">~25</td>
    <td align="center">~57</td>
    <td align="center">~56</td>
  </tr>
  <tr>
    <td align="center">Max Score</td>
    <td align="center">31</td>
    <td align="center">88</td>
    <td align="center">314</td>
  </tr>
</table>


### Training
Train a model by yourself:
```shell
python -m runRL --map=MoveToBeacon
```


### Notations
- Different from the original A3C algorithm, we replace the policy penalty term with epsilon greedy exploration.
- When train a model by yourself, you'd better to run several times and choose the best one. If you get better results than ours, it's grateful to share with us.


## Future Releases
- Support full game.
- Support supervised learning.
