<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Nalini P
<h3>Register Number:212223220063


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>


## Programm:

```
import random

class MedicineAgent:

    def __init__(self):
        self.location = "Room A"
        self.performance = 0

    def act(self, environment):

        temperature = environment[self.location]

        # Perceive and act
        if temperature > 98.5:
            print(self.location, "Temperature:", temperature)
            print("Patient is unhealthy. Giving medicine.")
            self.performance += 10
            environment[self.location] = 98.0

        else:
            print(self.location, "Temperature:", temperature)
            print("Patient is healthy.")

        # Move to another room
        if self.location == "Room A":
            self.location = "Room B"
        else:
            self.location = "Room A"

        self.performance -= 1

        print("Moving to:", self.location)
        print("Performance:", self.performance)
        print("-" * 30)


# Environment
environment = {
    "Room A": random.uniform(97, 102),
    "Room B": random.uniform(97, 102)
}

agent = MedicineAgent()

print("AI Medicine Agent")
print("-" * 30)

for i in range(5):
    print("Step", i + 1)
    agent.act(environment)
```

## Output:
<img width="618" height="382" alt="image" src="https://github.com/user-attachments/assets/1221a7c9-4707-400f-aa1b-da811dab2616" />

## Result:
The Medicine Prescribing AI Agent was successfully developed and tested using the PEAS description.

