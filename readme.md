# Powerful

Powerful is a demo showing how to maintain persistency on Power Platform by installing an automation factory that creates, executes and deletes arbitrary commands.

<a href="https://powerautomate.microsoft.com/en-us/robotic-process-automation/"><img src="https://docs.microsoft.com/en-us/power-pages/media/overview/power-platform.png" alt="Power Pwn" width="500" height="250" /></a>

## Usage

```python
from powerful.cli import FlowFactory, EXAMPLE
POST_URL = ""
factory = FlowFactory(post_url=POST_URL)

flow = factory.create_flow(
    environment_id=EXAMPLE["environment"], 
    flow_display_name=EXAMPLE["flowDisplayName"], 
    flow_definition=EXAMPLE["flowDefinition"], 
    flow_state=EXAMPLE["flowState"], 
    connection_references=EXAMPLE["connectionReferences"]
)

factory.delete_flow(environment_id=EXAMPLE["environment"], flow_id=flow["name"])
```