# Introduction

Amazon Connect is a powerful contact center solution by AWS. It provides web-based softphone for agents. The default softphone is generic and simple. With e-Arta, the softphone has been rewritten specific to Freshsales.

The custom contact control panel (CCP) offers interesting features such as:

- Setting up call logs, customer identification
- Visibility for agents into caller history, previous ticket information
- Agents are enabled to take notes while talking to the customer
- Agents are enabled to add manual log while talking to the customer

  Given below is a list of key features available (new features are being added continuously).

  On-Call (on receipt of an incoming call)
- Known Caller
  - If a caller is already in the Freshsales contacts, then the Caller's Name will be displayed to the agent.
  - All open tickets for that caller will be displayed to the agents. If there’s more than one open ticket available for that user, then the ticket list will be displayed to the agent.
  - The agent will have the option to create a new ticket if the caller is calling for a new issue.
  - The Lead score, Email ID, Last contacted, etc details will be displayed.
  
- Unknown Caller
  - If a caller is not in the Freshsales contacts, then the Caller's Name will be displayed to the agent as “Unknown Caller”.
  - If the caller is Unknown, then a ticket will not be created automatically. But the agent will have the option to create a ticket if required.
- Post Call
- Show call history specific to agent – last 25 calls.
- Make outbound calls by clicking call history.
- Create contact by selecting a number from the call history.
- Call-related information will be added to the respective ticket as a comment automatically.
- Ticket updated with Amazon Connect log reference.
  Contact Page
- Once the contact number is clicked on the contact page it will trigger an outgoing call
  Ticket Page
- From the ticket page, the agent can make an outbound call to the caller.
  Common Features
- The agent could search for contacts from the dial pad.
- The agent could change their availability status.
- The agent could send call logs to support.
- The incoming and outgoing call duration will be displayed.
- The incoming and outgoing queue name will be displayed.
