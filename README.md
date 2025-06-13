# Ghost Server for Custom GPTs

This repo contains a minimal schema setup for injecting reusable logic or style into OpenAI's Custom GPTs via a failing Action call.

This method lets you define character behavior, visual prompt templates, or session-specific rules without plugins, memory, or external APIs—just a ghost payload and a dead endpoint.

---

## How It Works

OpenAI’s Custom GPTs can trigger Actions—API calls defined by an `openapi` schema. If the server is unreachable, the Action fails. But the GPT still sees the payload.

This repo gives you a working schema that uses a placeholder server and injects your logic on failure. No server is required. The GPT just reads the payload and adjusts accordingly.

---

## Requirements

- OpenAI ChatGPT Pro subscription  
- Access to [https://chat.openai.com/gpts](https://chat.openai.com/gpts)  
- Custom GPT creation enabled

---

## Setup Instructions

1. Create a new GPT using the ChatGPT web interface.
2. Go to **Configure > Add Actions**.
3. Paste the schema found in `openapi_schema.json`.
4. Save and proceed to the **Test Action** panel.
5. Inject your custom logic or prompt by submitting a payload.

---

## Example Use

This setup is perfect for teaching your Custom GPT how to interpret specific scene styles or aesthetics using natural language—without memory or plugins.

For example, after injecting a style like "Neon Vapor Snap" with a description of Shrek in a mech suit, your GPT will understand that "Neon Vapor Snap Shrek" means a glowing, synthwave, mech-themed version of Shrek.

Once injected, you can simply say:

“Give me a Neon Vapor Snap Shrek”

“Render Sonic in Hyper Fidelity”

“Make Peach in Pastel Dreamscape”

...and the GPT will recall exactly what those mean, because it saw the context during the Action test—even though the call failed. (You can GREATLY expand upon these weak example prompts)

This lets you:

Create consistent, high-fidelity prompts with just a phrase

Assign meaning to custom styles or presets

Skip repeating visual details or elaborate scenes every time

Inject once per session, and the GPT picks it up like it's built-in.
