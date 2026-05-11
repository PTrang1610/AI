# Vacuum Robot - Model Based Reflex Agent



A simple AI simulation of a smart vacuum-cleaning robot operating in a 3×3 grid environment using a \*\*Model-Based Reflex Agent\*\* architecture.



Instead of reacting blindly, the robot keeps an internal memory of explored cells and previously observed dirt locations to make smarter decisions while cleaning the environment.



\---



The AI cycle:



```text

Perceive → Update Memory → Choose Rule → Execute Action

```



At every step, the robot:



1\. Observes its current position

2\. Updates its internal map

3\. Selects the most appropriate rule

4\. Performs an action



The robot does \*\*not\*\* know the whole environment initially — it only learns through exploration



\---



\# Agent Architecture



```text

Environment (3×3 Grid)

&#x20;       │

&#x20;       ▼

┌────────────────────────────┐

│        VacuumAgent         │

│                            │

│  update\_state()            │

│  rule\_match()              │

│  get\_action\_target()       │

└────────────────────────────┘

&#x20;       │

&#x20;       ▼

&#x20;Execute Action

```



The internal memory allows the agent to:

\- remember visited cells

\- track dirty locations

\- avoid unnecessary movement

\- stop automatically when everything is clean



\---



\# Rule Priority System



The agent chooses actions using prioritized IF-THEN rules.



| Priority | Condition | Action |

|----------|------------|---------|

| 1 | All known cells are clean | `STOP` |

| 2 | Current cell is dirty | `SUCK` |

| 3 | Unvisited neighbor exists | `MOVE\_UNVISITED` |

| 4 | Known dirty cell exists | `MOVE\_TO\_DIRTY` |

| 5 | Otherwise | `MOVE\_RANDOM` |



This priority system ensures the robot behaves efficiently and avoids random movement whenever possible.



\---





\# Project Structure



```text

vacuum-agent/

├── vacuum\_agent.py

└── README.md

```



\---



\# Run the Simulation



\## Requirements

\- Python 3.8+

\- No external libraries required



\## Run



```bash

python vacuum\_agent.py

```



\---



\# AI Concepts Used



This project demonstrates several introductory Artificial Intelligence concepts:



\- Intelligent Agents

\- Model-Based Reflex Agents

\- Rule-Based Systems

\- State Representation

\- Environment Perception



\---



