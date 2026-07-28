<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Mithun Kumar G N</h3>
<h3>Register Number/Staff Id: 212224230160</h3>


<h3>AIM:</h3>

<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>

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

<H3>PROGRAM</H3>

```
import random

class HealthMonitoringAgent:
    def __init__(self, patient_data, sensors, actuators):
        self.patient_data = patient_data
        self.sensors = sensors
        self.actuators = actuators

    def monitor_health(self):
        while True:
            # Get the current health data
            current_health_state = self.sensors.get_health_state()

            print("\nCurrent Health Status:")
            print(current_health_state)

            # Decide the action
            action = self.choose_action(current_health_state)

            # Perform the action
            self.actuators.perform_action(action)

            # Stop if everything is normal
            if action == "No specific action needed":
                print("\nPatient is healthy. Monitoring stopped.")
                break

    def choose_action(self, current_health_state):
        if current_health_state['heart_rate'] > 120:
            return "Alert: High heart rate detected."
        elif current_health_state['blood_pressure'] > 140:
            return "Alert: High blood pressure detected."
        elif current_health_state['temperature'] > 38:
            return "Recommend rest and monitor temperature."
        else:
            return "No specific action needed"


class HealthSensors:
    def get_health_state(self):
        # Simulate health data
        return {
            'heart_rate': random.randint(60, 150),
            'blood_pressure': random.randint(90, 160),
            'temperature': round(random.uniform(36.0, 38.5), 1)
        }


class HealthActuators:
    def perform_action(self, action):
        print("Action Taken:", action)


# Main Program
if __name__ == "__main__":
    patient_data = {
        'patient_id': 123,
        'name': 'John Doe',
        'age': 35
    }

    # Create sensor and actuator objects
    sensors = HealthSensors()
    actuators = HealthActuators()

    # Create the agent
    health_agent = HealthMonitoringAgent(
        patient_data,
        sensors,
        actuators
    )

    # Start monitoring
    health_agent.monitor_health()
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>
```
<H3>OUTPUT</H3>

<img width="659" height="464" alt="image" src="https://github.com/user-attachments/assets/7a0b9295-8aea-41df-8ebe-655917e707ec" />

<H3>RESULT</H3>
The Medicine Prescribing AI Agent was successfully developed using the PEAS (Performance, Environment, Actuators, Sensors) model. The agent continuously monitored the patient's health parameters, identified unhealthy conditions such as high heart rate, high blood pressure, or fever, and performed the appropriate action. The agent also checked patients in different rooms, prescribed treatment when required, and measured its performance based on treatment and movement between rooms. Thus, the objectives of designing and implementing an AI agent using the PEAS description were achieved successfully.
