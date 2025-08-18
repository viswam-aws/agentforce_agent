## 1. Setup an Agentforce Service Agent

    Create the AI agent inside Salesforce Agentforce.

    Define its purpose (e.g., answer KB article queries, handle tickets).

    Assign it the right Permission Set License (e.g., Agentforce Service Agent User).

2. Setup a Routing Configuration

    Routing config decides how chats are directed to your agents/queues.

    Configure capacity model (e.g., number of chats per agent).

    Decide if routing will be based on skills, priority, or load balancing.
        
        Note: using default "ESA Routing Configuration" 

3. Establish a Queue

    A queue holds conversations until an agent picks them up.

    Example: Support_Queue, Billing_Queue, Technical_Queue.

    Assign users or groups to the queue.

        Note: using default "Messaging Queue" and already atached to "ESA Routing Configuration"

4. Develop an Omni Flow

    Omni-Channel Flows define conversation handling logic.

    Example:

    If user asks about "password reset" → Route to Knowledge Article.

    If unresolved → Route to Support Agent.

    Built in Salesforce Flow Builder.

5. Define a Messaging Setting

    Configures how messaging works for your Agentforce agent.

    Includes:

    Entry Points (Web, WhatsApp, Telegram, etc.).

    Variables like Customer Name, Email, Case Number.

6. Define an Embedded Service Deployment

Creates the deployment package (JS script + config) to embed on websites.

Similar to how Salesforce LiveChat/OmniChat widgets are embedded.

7. Integrate code into an external website to launch the agent

Copy the deployment JavaScript snippet from Salesforce.

Paste it into your customer website’s <head> or <body>.

8. Configure CORS and Trust URLs

Add your external site’s URL to CORS (Cross-Origin Resource Sharing).

Ensures Salesforce only accepts connections from trusted domains.

9. Add the domain to Sites

Register your website domain in Salesforce Sites & Domains.

Prevents errors like cross-domain cookies blocked.

10. Create new variables within the Messaging Setting

Define custom variables (e.g., customerID, ticketID, accountType).

Useful for personalizing responses and passing metadata into flows.

11. Activate and configure Parameters (Hidden & Visible)

Visible Parameters: Customer sees them (e.g., case ID displayed in chat).

Hidden Parameters: Passed behind the scenes (e.g., accountId for routing).

12. Test the Agent in External Website

Open your external website → Start chat → Verify:

Agent launches correctly.

KB articles are returned.

Cases are created when escalated.

Routing flows behave as expected.