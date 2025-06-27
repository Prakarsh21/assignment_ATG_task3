# Multi-Agent Debate System using LangGraph

## Overview
This system simulates a structured debate between two AI agents (Scientist and Philosopher) on a user-provided topic. The debate follows 8 rounds of arguments, with an automated judge determining the winner based on logical analysis. Built with LangGraph and Hugging Face models optimized for Google Colab.

[![Open In Colab IF preview not available here](https://colab.research.google.com/drive/1_lqvW1jg1kZVLkAPqwndJW2xwB43_1s8?usp=sharing)

## Features
- 8-round structured debate with alternating agents
- Profession-specific personas (Scientist vs Philosopher)
- Memory management with contextual argument tracking
- Automated judging with logical justification
- CLI interface for topic input
- Complete state transition logging
- DAG visualization of workflow
- Google Drive integration for output persistence

## System Architecture
```mermaid
graph LR
    A[UserInputNode] --> B[ScientistNode]
    B --> C[Memory Update]
    C --> D[PhilosopherNode]
    D --> C
    C --> E{8 Rounds?}
    E -- No --> B
    E -- Yes --> F[JudgeNode]
    F --> G[End]
