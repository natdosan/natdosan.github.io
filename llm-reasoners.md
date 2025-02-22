# MULTI-MODAL LLM REASONING AND AGENT MODELING

Aaryan Agrawal, Nathaniel del Rosario, So Hirota, Zihan Liu, Trevan Nguyen, Samual Zhang

## Overview

Web-based agents using LLMs show promise in automating browser tasks, but scaling inference efficiently remains a challenge. This work explores the question of how best to structure search: implicit (greedy, depth-limited) or explicit (structured exploration like MCTS). Implicit search is potentially computationally cheaper but struggles with backtracking, while explicit search enables efficient exploration but relies on resettable states, which may be impractical in real-world web environments. Experiments on 106 WebArena tasks show explicit search achieves higher task completion rates and better environment interaction efficiency. While explicit search excels in controlled settings, implicit search remains more applicable to real-world tasks. Another aspect to consider is conducting an explicit search on an LLM world model, where the search occurs over predicted next states as opposed to the environment itself, which can potentially gain the benefits of both implicit and explicit search. These techniques extend beyond web environments, and should theoretically be applicable to OS automation (OsWorld) and dynamic game environments (MineDojo).

## Motivation
- Expanding LLM-Reasoners into new environments
- BrowserGym & WebArena
- OSWorld

## Methods
- Adding support for External, Explicit Search (MCTS, BFS, DFS)
- Experiments utilizing Internal World Model (RAP)

## Results
- Inference/Compute Scaling Plots

## Future Directions
