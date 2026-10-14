# Experiment No. 1: Developing an AI Agent with PEAS Description

**Name:** DHANALAKSHMI C

## AIM

To identify the PEAS description for a given AI problem and develop an AI agent using Python.

## THEORY

### Vacuum Cleaner Agent

A vacuum cleaner agent is an intelligent agent that operates in an environment containing two rooms, A and B. Each room may be dirty or clean. The agent can move between rooms and suck dirt from its current location.

The agent receives a positive performance score for cleaning a dirty room and a penalty for movement. The objective is to clean the rooms while tracking the agent's performance.

## PEAS DESCRIPTION

| Component | Description |
|---|---|
| Performance Measure | Cleaning rooms and maximizing the performance score |
| Environment | Two rooms, A and B |
| Actuators | Move left, move right, suck dirt |
| Sensors | Current location and dirt status |

## DESIGN STEPS

**Step 1: Identifying the Input**

The agent's current location and the dirt status of rooms A and B.

**Step 2: Identifying the Output**

The agent displays its current location, dirt status, and performance measure.

**Step 3: Developing the PEAS Description**

The PEAS description identifies the performance measure, environment, actuators, and sensors of the vacuum cleaner agent.

**Step 4: Implementing the AI Agent**

The agent is implemented using Python classes and methods. It can move between rooms, clean dirt, and perform no action.

**Step 5: Measuring Performance**

- Cleaning a dirty room increases the performance score by 10.
- Moving left or right decreases the performance score by 1.
- Performing no action does not change the score.

## PROGRAM

```python
class VacuumCleanerAgent:
    def __init__(self):
        self.location = "A"
        self.dirt_status = {"A": True, "B": True}
        self.performance = 0

    def move_left(self):
        if self.location == "B":
            self.location = "A"

    def move_right(self):
        if self.location == "A":
            self.location = "B"

    def suck_dirt(self):
        if self.dirt_status[self.location]:
            self.dirt_status[self.location] = False
            print(f"Sucked dirt in location {self.location}")

    def do_nothing(self):
        pass

    def perform_action(self, action):
        if action == "left":
            self.performance -= 1
            self.move_left()
        elif action == "right":
            self.performance -= 1
            self.move_right()
        elif action == "suck":
            self.performance += 10
            self.suck_dirt()
        elif action == "nothing":
            self.do_nothing()
        else:
            print("Invalid action")

    def print_status(self):
        print(
            f"Location: {self.location}, "
            f"Dirt Status: {self.dirt_status}, "
            f"Performance Measure: {self.performance}"
        )


agent = VacuumCleanerAgent()

agent.perform_action("left")
agent.print_status()

agent.perform_action("suck")
agent.print_status()

agent.perform_action("right")
agent.print_status()

agent.perform_action("suck")
agent.print_status()

agent.perform_action("nothing")
agent.print_status()
```

## OUTPUT

```text
Location: A, Dirt Status: {'A': True, 'B': True}, Performance Measure: -1
Sucked dirt in location A
Location: A, Dirt Status: {'A': False, 'B': True}, Performance Measure: 9
Location: B, Dirt Status: {'A': False, 'B': True}, Performance Measure: 8
Sucked dirt in location B
Location: B, Dirt Status: {'A': False, 'B': False}, Performance Measure: 18
Location: B, Dirt Status: {'A': False, 'B': False}, Performance Measure: 18
```

## RESULT

Thus, the vacuum cleaner agent was implemented successfully using Python. The agent performed movement and cleaning actions, and its performance measure was calculated for each action.
