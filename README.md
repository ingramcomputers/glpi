# GLPI Stuff

Right now all I have is n8n workflows that creates tickets in GLPI.
I am using the Shuffle integration built into Wazuh (/var/ossec/integrations/shuffle) to format and send the webhook.

You will need to assign an integration block to your ossec.conf.

```
# USB Detection, you can use any rule ID.
  <integration>
    <name>shuffle</name>
    <hook_url>https://n8n.yourdomain.com/webhook/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</hook_url>
    <rule_id>111001,111002</rule_id>
    <alert_format>json</alert_format>
  </integration>

# Send Level 12 or Higher
  <integration>
    <name>custom-shuffle</name>
    <hook_url>https://n8n.yourdomain.com/webhook/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</hook_url>
    <level>12</level>
    <alert_format>json</alert_format>
  </integration>
```