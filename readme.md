# Powerful

Powerful is a demo showing how to maintain persistency on Power Platform by installing an automation factory that creates, executes and deletes arbitrary commands.

<a href="https://powerautomate.microsoft.com/en-us/robotic-process-automation/"><img src="https://docs.microsoft.com/en-us/power-pages/media/overview/power-platform.png" alt="Power Pwn" width="500" height="250" /></a>

----

This tool was released as part of DEFCON30. For more details, see [Low Code High Risk: Enterprise Domination via Low Code Abuse](https://github.com/mbrg/defcon30/blob/main/Low_Code_High_Risk/readme.md).

Disclaimer: these materials are presented from an attacker’s perspective with the goal of raising awareness to the risks of underestimating the security impact of No Code/Low Code. No Code/Low Code is awesome.

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