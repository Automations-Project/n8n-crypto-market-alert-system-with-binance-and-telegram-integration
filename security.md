For Security Reasons we will summuray the n8n template code into text as follow:
**Workflow Summary:**
**Additional Processing:**
- **Sticky Note** (n8n-nodes-base.stickyNote)
  Details:
    - **Content**:
```plaintext
### Workflow Setup Steps:
1. Ensure the **_Schedule Trigger_** is active to desired cron time (Default 5 minutes).
2. [_Optional_] Configure the **_Binance 24h Price Change_** node with your API details (Default one is Free Public API Call - Free).
3. Set up your **Telegram bot** token in the **Telegram node credentials**.
4. Update the **_Chat ID_** in the **_Send Telegram Message_** node.
5. Test the workflow to ensure everything is set up correctly.
* **Notes**: Detailed telegram bot setup instructions are available in the [workflow's n8n page](https://n8n.io/workflows/2043-crypto-market-alert-system-with-binance-and-telegram-integration).







‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ ‌ ‌ ‌ ‌‌ [![N8N Creator Profile - Nskha](https://cdn.statically.io/gh/Automations-Project/n8n-templates/main/stats.min.svg)](https://n8n.io/creators/nskha)
``` 
- **Schedule Trigger** (n8n-nodes-base.scheduleTrigger)
**Data Fetching and Processing:**
- **Binance 24h Price Change** (n8n-nodes-base.httpRequest)
  Details:
    - **Notes**: ```plaintext
Get data of changed price coins in last 24h``` 

**Additional Processing:**
- **Filter by 10% Change rate** (n8n-nodes-base.function)
  Details:
    - **Notes**: ```plaintext
Filter by 10% Up & Down``` 
- **Aggregate** (n8n-nodes-base.aggregate)
  Details:
    - **Notes**: ```plaintext
Combine all items``` 
- **Split By 1K chars** (n8n-nodes-base.code)
  Details:
    - **Notes**: ```plaintext
Split them for telegram message limit``` 
- **Send Telegram Message** (n8n-nodes-base.telegram)
