# Baserun demo

This is a small app that uses LangChain to demonstrate Baserun.

## Walkthrough

### Setup

Install dependencies
```bash
npm install
```

Create a .env file with at least two environment variables: `BASERUN_API_KEY` and `OPENAI_API_KEY`

### Execute the main.ts script

```bash
ts-node src/chatbot/main.ts
```

### The bot will engage you in conversation

You can ask for product information and order status. For this demo app the product and order information has been
stubbed out, but the tool calls work.

```
$ ts-node src/chatbot/main.ts
Start your conversation. Type `exit` to end the conversation.
> how much is that 6ft dog leash?
-- Calling tool get_products
-- Tool call result: [{'name': 'Tan Rope Dog Leash', 'brand': 'Reddy', 'in_stock': 8, 'price': 9.99}]
The 6ft Tan Rope Dog Leash from Reddy is currently priced at $9.99. And good news, we have 8 of these in stock! Ready to be fetched for your furry friend. Would you like to go ahead and order one? 🐾🐶
> can i talk to a human?
-- Calling tool escalate
-- Tool call result: True
Absolutely, I can connect you with a human representative to assist you further. Please hold on for a moment while I transfer the chat. 🤗
> exit
How would you rate this conversation on a scale of 1 to 10?
> 4
```

## What Baserun is doing

This chatbot exercises much of Baserun's functionality:

- User sessions
- Tracing, including setting the trace's result
- Logging of an internal function (persistence in this case)
- Annotating the conversation with feedback
