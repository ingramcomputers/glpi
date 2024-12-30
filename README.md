# GLPI Stuff

Right now all I have is n8n workflow that create tickets in GLPI.
I am using the Shuffle integration built into Wazuh (/var/ossec/integrations/shuffle) to format and send the webhook.

You will need to ass an integration block to your ossec.conf.

```
# USB Detection
  <integration>
    <name>shuffle</name>
    <hook_url>https://n8n.tfb098.com/webhook/53d6144c-c75e-4599-ab47-c13a41754610</hook_url>
    <rule_id>111001,111002</rule_id>
    <alert_format>json</alert_format>
  </integration>

# Send Level 12 or Higher
  <integration>
    <name>custom-shuffle</name>
    <hook_url>https://n8n.tfb098.com/webhook/05938e9a-f666-4cee-a1b1-3fef468f73e0</hook_url>
    <level>12</level>
    <alert_format>json</alert_format>
  </integration>
```