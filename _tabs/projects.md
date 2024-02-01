---
# the default layout is 'page'
icon: fa-solid fa-rocket
order: 4
---

In this section you'll find some of the projects I've been working on or that
I'm planning to work on. I'll try to keep it updated, but if you want to see
more, you can check my [GitHub](https://github.com/geduardo).

Each project has a short description, status, if open to collaboration, and a link to the GitHub repository if available.

## RL Environment for Wire EDM Control
- **Description**: This project is about creating a reinforcement learning environment for controlling Wire Electrical Discharge Machining (EDM) processes. It's one of the projects I'm working on as part of my PhD. The goal is to create a stochastic representation of the process that can be used to train learning agents to control real Wire EDM machines. The environment is being developed in Python following the Gymnasium structure. The final goal is to be able to transfer the knowledge acquired by the agents to the real machines. It's still in very early stages, but the GitHub repository is available. The software is under the MIT license, so feel free to contribute if you want.
- **Status**: Ongoing
- **Open to Collaboration**: Yes
- **GitHub Repository**: [WEDM-Learning-Environment](https://github.com/geduardo/WEDM-Learning-Environment)

## Evolutionary Prompts to Solve Tasks

- **Description**: This project is based on the general idea outlined in the post "How Progress Is Made". I believe the most effective method for advancing in complex optimization tasks combines search-based methods executed by agents with a model of the search space and the capacity for learning and inter-agent communication. The project aims to develop a framework for testing this concept in various contexts. I think that current LLMs, especially GPT-4, possess a substantial understanding of diverse domains. The goal is to harness this knowledge to solve tasks using an evolutionary approach. Essentially: 
    - Assign a problem to multiple LLM instances with distinct random seeds.
    - Compile the suggested solutions.
    - Evaluate them.
    - Generate a report detailing the top solutions and their performance
    - Reintegrate this data into a new prompt to feed the batch of LMMs
    - Continue until progress stops. 
    
    The idea essentially is utilizing LLMs to navigate the search space and applying an evolutionary algorithm to optimize it.
    
    EDIT: just days after writing this project description, Google Deepmind published a [similar approach](https://www.nature.com/articles/s41586-023-06924-6). However, they only use PaLM 2 and there are some
    suff that I think could be improved with far less resources.
- **Status**: Ongoing
- **Open to Collaboration**: Yes
- **GitHub Repository**: [Evolutionary-LLM-optimization](https://github.com/geduardo/Evolutionary-LLM-optimization)

## Multimodal LLMs for Game Control
- **Description**: The idea of this project is to test the capabilities of multi-modal LLMs to control simple games. I'm basically going to feed SOTA models with frames of different games and ask them to produce an action. The action will be executed in the game and the result will be fed back to the LLM. The idea is to see what kind of games the LLMs can play and how well it does compared to random actions.
- **Status**: Ongoing
- **Open to Collaboration**: Yes
- **GitHub Repository**: [Game Control with Multimodal LLMs](https://github.com/geduardo/Game-Control-with-Multimodal-LLMs)