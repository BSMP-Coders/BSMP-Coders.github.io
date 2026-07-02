# Set up the class AI model (one-time)  <!-- {docsify-ignore-all} -->

This adds the **class Azure AI model** to your in-editor **Copilot Chat** so you can use it to write code with prompts (Stage 3 and beyond). You only do this **once per Codespace**, and it takes about a minute.

> **Why isn't this automatic?** In browser-based Codespaces, VS Code stores your model settings in the browser itself (not in the Codespace), so it can't be pre-installed for you. You add it by hand the first time — that's this page.

> **Two different "models" — don't mix them up:**
> - **This page** sets up the model that powers **Copilot Chat** (the AI assistant *you* prompt to write code).
> - **Stage 3** (in `int/` or `adv/`) uses the same Azure values in a **`.env` file** so the **app you build** can talk to Azure. Same key, two different places.

---

## What your teacher gives you

You only need **one** thing from your teacher: the **class API key** (a long string like `a1b2c3...`). The endpoint and model name are already filled in for you below.

| Value | What to use |
|---|---|
| **API key** | the key your teacher shares in class |
| **Endpoint** | `https://YOUR-RESOURCE.openai.azure.com/openai/deployments/gpt-4.1-nano/chat/completions?api-version=2025-01-01-preview` |
| **Deployment / model name** | `gpt-4.1-nano` |

> 🔒 **Keep the key private.** It's a shared class key — don't post it in chat, commit it to a repo, or share it outside class. If it leaks, your teacher rotates it (see [Updating the key](#updating-the-key)).

---

## Method A — the menu (recommended)

This is the easy path and it stores your key securely.

1. Open the Command Palette: **`Ctrl` + `Shift` + `P`**.
2. Run **`Chat: Manage Language Models`**.
3. Click **Add Models** → choose **Azure**.
4. **Group name:** type `BSMP Azure`.
5. Paste the **API key** your teacher gave you, and for the endpoint paste `https://YOUR-RESOURCE.openai.azure.com/openai/deployments/gpt-4.1-nano/chat/completions?api-version=2025-01-01-preview`.
6. Pick the **`gpt-4.1-nano`** model.
7. Open the Chat panel and choose your **BSMP Azure** model from the model picker (the dropdown under the chat box).

> If the model doesn't show up right away, **reload the window**: Command Palette → **`Developer: Reload Window`**.

---

## Method B — the JSON file (what it looks like)

If you used Method A, VS Code writes a file called **`chatLanguageModels.json`** for you — you don't hand-type it. Here's what a finished entry looks like so you can recognize it and check each part:

```json
[
  {
    "name": "BSMP Azure",
    "vendor": "azure",
    "apiKey": "${input:chat.lm.secret.-12345678}",
    "models": [
      {
        "id": "gpt-4.1-nano",
        "name": "BSMP Azure (gpt-4.1-nano)",
        "url": "https://YOUR-RESOURCE.openai.azure.com/openai/deployments/gpt-4.1-nano/chat/completions?api-version=2025-01-01-preview",
        "toolCalling": true,
        "vision": true,
        "maxInputTokens": 128000,
        "maxOutputTokens": 16000
      }
    ]
  }
]
```

> 🔑 **About the `apiKey` line.** VS Code adds it for you when you enter your key in the **Add Models** prompt. The `${input:chat.lm.secret.…}` value is a *pointer* to your key in VS Code's encrypted secret storage — **not** the key itself, and the number is unique to your machine. Don't paste your literal key here, don't edit this line, and don't copy it from someone else.

What each part means:
- **`vendor: "azure"`** — tells VS Code this is an Azure OpenAI model. (Use `azure`, not `customendpoint` — it's more reliable.)
- **`apiKey`** — the auto-generated secret reference described above. VS Code manages it; leave it as-is.
- **`id`** — the **deployment name** (`gpt-4.1-nano`). This is what actually selects the model.
- **`name`** — just the **label shown in the model-picker dropdown**. It's cosmetic — you can name it anything. (If yours reads `BSMP Azure (gpt-4.1-nano)` or another version, that's only the label; the real model is whatever `id` says. Edit `name` if you want the dropdown to match.)
- **`url`** — the full Azure endpoint for the deployment (VS Code fills this in from what you entered).
- **`toolCalling: true`** — **required** so the model shows up in **agent** mode. Leave it on.

Now tell Copilot Chat to use it: open the **Copilot Chat** panel and click the **model picker** — the small dropdown at the bottom of the chat box (next to the send button) that shows the current model's name. Choose your **BSMP Azure** model from the list. If it isn't there yet, reload the window (Command Palette → **`Developer: Reload Window`**) and look again.

---

## Updating the key

If your teacher rotates the class key (or you typed it wrong):

1. Command Palette → **`Chat: Manage Language Models`**.
2. Click the **gear icon** next to **BSMP Azure**.
3. Paste the new **API key** (and update the endpoint if it changed).
4. Reload the window if needed: **`Developer: Reload Window`**.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Model not in the picker | Run **`Developer: Reload Window`**. |
| Not available in **agent** mode | Make sure `toolCalling` is `true`. |
| "Unauthorized" / 401 errors | The **API key** is wrong or expired — redo [Updating the key](#updating-the-key). |
| "Resource not found" / 404 | Check the **endpoint** URL and that the **deployment name** is exactly `gpt-4.1-nano`. |
| Set up once, gone next day | This lives in your **browser**, per Codespace — if you open a brand-new Codespace, add it again (1 min). |

---

## Good to know

- This uses **Bring Your Own Key (BYOK)**, which works on **Copilot Free** for **chat** — you don't need a paid Copilot seat.
- Usage is billed to the **class Azure account**, not your personal Copilot limit.
- BYOK powers **chat only** — inline gray-text autocomplete still needs regular Copilot, and that's fine for these lessons.