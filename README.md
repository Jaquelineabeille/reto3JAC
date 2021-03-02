  
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "botserviceName": {
           "type": "string",
           "metadata": {
                "description": "Name of the Bot Service"
            }
        },
        "botserviceDisplayName": {
           "type": "string",
           "metadata": {
                "description": "Display Name of the Bot"
            }
        },
        "botlogicEndpoint": {
           "type": "string",
           "metadata": {
                "description": "Endpoint to call the bot logic"
            }
        },
        "botMsaAppId": {
           "type": "string",
           "metadata": {
                "description": "Microsoft Application ID for the bot"
            }
        },
        "botAppInsightKey": {
           "type": "string",
           "metadata": {
                "description": "Microsoft Application ID for the bot"
            }
        }
    },
    "variables": {},
    "resources": [
        {
            "name": "[parameters('botserviceName')]",
            "type": "Microsoft.BotService/botServices",
            "apiVersion": "2018-07-12",
            "location": "global",
            "sku": {
                "name": "F0"
            },
            "kind": "bot",
            "properties": {
                "displayName": "[parameters('botserviceDisplayName')]",
                "endpoint": "[parameters('botlogicEndpoint')]",
                "msaAppId": "[parameters('botMsaAppId')]",
                "developerAppInsightKey": "[parameters('botAppInsightKey')]"
            }
        }
    ],
    "outputs": {}
}
