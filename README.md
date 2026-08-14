# Multi-Agent Pick-and-Drop with Delivery Sequence Specification

This repository contains supplementary data and demonstration videos for the paper on **SOPP: Sequence-Oriented Pickup-and-delivery Planning**.

## Overview

The algorithm addresses the challenge of coordinating multiple autonomous agents graph-based environments to efficiently complete pick-and-drop tasks while respecting specified delivery sequences. Each task includes:
- **Source location**: Where the item is picked up
- **Destination location**: Where the item is delivered
- **Delivery sequence**: Constraint on the order in which items must be delivered
- **Time delays**: Optional task release times for testing with asynchronous task arrival
- agent velocity is assumed 1 unit distance per 1 unit of time

---

## Scenario 1: Large Warehouse (1000 Agents)

### Description
A full-scale warehouse environment (based on warehouse-10-20-10-2-1 available on [https://movingai.com/benchmarks/mapf/index.html](https://movingai.com/benchmarks/mapf/index.html)) with **1000 autonomous agents** coordinating to complete 5000 pick-and-drop tasks.

### Video
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/vAfQ-MqZ4MQ" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/vAfQ-MqZ4MQ)**

### Map Files
- **JSON format**: [warehouse-10-20-10-2-1.json](Warehouse_big/warehouse-10-20-10-2-1.json)
- **Map format**: [warehouse-10-20-10-2-1.map](Warehouse_big/warehouse-10-20-10-2-1.map)

**Safe location** is specified in node 1 (top-left corner).

### Task File
- [warehouse_10_20_10_2_1_tasks.m](Warehouse_big/warehouse_10_20_10_2_1_tasks.m) - Contains 5000 tasks with delivery sequence constraints

### Results

| Metric | Value |
| --- | --- |
| Makespan | 3,022.80 time units |
| Number of Agents | 1000 |
| Number of Tasks | 5000 |
| Total agents time | 1,679,776.80 units |
| Total Travel Distance | 946,098.00 units |
| Number of planning steps | 36,309 |

---

## Scenario 2: Maze Environment

### Description
A complex maze environment (based on maze-32-32-2 available on [https://movingai.com/benchmarks/mapf/index.html](https://movingai.com/benchmarks/mapf/index.html) demonstrating agent coordination in constrained spaces.

### Video
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/dw_x6QX8zU0" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/dw_x6QX8zU0)**

### Map Files
- **JSON format**: [maze-32-32-2.json](Maze/maze-32-32-2.json)
- **Map format**: [maze-32-32-2.map](Maze/maze-32-32-2.map)

**Safe location** is specified in node 186 (dead-end on the right).

### Task File
- [maze_32_32_2_random_1.tasks.m](Maze/maze_32_32_2_random_1.tasks.m) - Random task set for maze scenario

### Results

| Metric | Value |
| --- | --- |
| Makespan | 695.95 time units |
| Number of Agents | 1000 |
| Number of Tasks | 333 |
| Total agents time | 44,919.45 units |
| Total Travel Distance | 38,180.00 units |
| Number of planning steps | 8,608 |

---

## Scenario 3: Small Warehouse (No Delays)

### Description
A customized compact warehouse environment with intentional choke point.

### Map File
- **JSON format**: [grid_map_4_tight.json](Warehouse_small_no_delays/grid_map_4_tight.json)

### Task File
- [Tasks.txt](Warehouse_small_no_delays/Tasks.txt) - 56 tasks with delivery sequences

---

### Video Results by Agent Count

#### Single Agent (1 agent)
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/6Xkvc34yR5M" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/6Xkvc34yR5M)**

#### Two Agents (2 agents)
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/9iOV_qVMCYQ" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/9iOV_qVMCYQ)**

#### Multiple Agents (14 agents)
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/o5B-OuJEE40" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/o5B-OuJEE40)**

---

## Scenario 4: Small Warehouse with Task Delays

### Description
The same compact warehouse environment as Scenario 3, but with **staggered task arrival times** (delays). This demonstrates the algorithm's ability to handle asynchronous task releases and dynamic task assignment.

**Key Feature**: Each task has a release time delay (ranging from 20 to 1120 time units), simulating real-world scenarios where tasks arrive at different times and no prior knowledge of task sequence is known.

### Map File
- **JSON format**: [grid_map_4_tight.json](Warehouse_small_delays/grid_map_4_tight.json)

### Task File
- [Tasks.txt](Warehouse_small_delays/Tasks.txt) - 56 tasks with varying arrival delays and delivery sequences

---

### Video Results by Agent Count

#### Single Agent with Delays (1 agent)
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/OevrdAoUxv8" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/OevrdAoUxv8)**

#### Multiple Agents with Delays (10 agents)
<div style="max-width: 640px;">
  <iframe width="100%" height="360" src="https://www.youtube.com/embed/usv2OP4pHYk" frameborder="0" allowfullscreen></iframe>
</div>

**[Full Video Link](https://youtu.be/usv2OP4pHYk)**
