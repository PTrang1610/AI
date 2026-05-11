# \# Vacuum Robot - Model Based Reflex Agent

# 

# A simple Artificial Intelligence simulation of a smart vacuum-cleaning robot operating inside a \*\*3x3 grid environment\*\* using a \*\*Model-Based Reflex Agent\*\* architecture.

# 

# \---

# 

# \## Overview

# 

# This project demonstrates how an intelligent agent can:

# 

# \- perceive its environment

# \- maintain an internal state (memory)

# \- apply rule-based decision making

# \- perform actions autonomously

# 

# \---

# 

# \## Agent Decision Cycle

# 

# ```text

# Perceive → Update Memory → Choose Rule → Execute Action

# ```

# 

# At every step, the agent:

# 

# 1\. Observes the current environment

# 2\. Updates its internal memory

# 3\. Matches the best rule

# 4\. Executes an action

# 

# \---

# 

# \## Agent Architecture

# 

# ```text

# Environment (3x3 Grid)

# &#x20;       │

# &#x20;       ▼

# ┌────────────────────────────┐

# │        VacuumAgent         │

# │                            │

# │  update\_state()            │

# │  rule\_match()              │

# │  get\_action\_target()       │

# └────────────────────────────┘

# &#x20;       │

# &#x20;       ▼

# &#x20;  Execute Action

# ```

# 

# \---

# 

# \## Internal Memory Features

# 

# The agent maintains an internal representation of the environment to:

# 

# \- remember visited cells

# \- track dirty locations

# \- reduce unnecessary movement

# \- improve cleaning efficiency

# \- stop automatically when all cells are clean

# 

# \---

# 

# \## Rule Priority System

# 

# The robot selects actions using prioritized IF-THEN rules.

# 

# | Priority | Condition                 | Action           |

# |----------|---------------------------|------------------|

# | 1        | All known cells are clean | `STOP`           |

# | 2        | Current cell is dirty     | `SUCK`           |

# | 3        | Unvisited neighbor exists | `MOVE\_UNVISITED` |

# | 4        | Known dirty cell exists   | `MOVE\_TO\_DIRTY`  |

# | 5        | Otherwise                 | `MOVE\_RANDOM`    |

# 

# \---

# 

# \## Run the Simulation

# 

# ```bash

# python vacuum\_agent.py

# ```

