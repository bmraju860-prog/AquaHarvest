# AquaSense AI — Real AI Starter (beginner setup)

Live demo: https://aquaharvest-o3s9.onrender.com/

This cleaned-up version keeps the core rainwater calculator, dashboard, Rain Planner, urban management, recommendations, AI Assistant, and separate Locations page. It removes a duplicate urban-calculation button and replaces a troubleshooting-only AI suggestion with “Interpret my results”. The AI chat receives current calculator/planner/urban input values so it can give more project-specific explanations. The AI chat calls the OpenAI Responses API through a Python/Flask backend. The private API key is read from `.env` and is never placed in `index.html`.

## Before you start
- Install Python 3.10 or newer.
- You need an OpenAI API key and API billing/access. A ChatGPT subscription does not automatically include API usage. Usage may cost money.
- Keep the API key private. Never paste it into HTML, screenshots, GitHub, or a public chat.

## Windows setup (step by step)
1. Extract this ZIP into a folder, for example `Desktop\AquaSenseAI_Final_Top10_Edition`.
2. Open that folder in File Explorer.
3. Click the folder address bar, type `cmd`, and press Enter. A Command Prompt opens in that folder.
4. Create a virtual environment:
   ```bat
   py -m venv .venv
   ```
5. Activate it:
   ```bat
   .venv\Scripts\activate
   ```
6. Install packages:
   ```bat
   python -m pip install -r requirements.txt
   ```
7. Copy `.env.example` and rename the copy to `.env` (make sure Windows does not name it `.env.txt`).
8. Open `.env` in Notepad. Replace `put_your_private_api_key_here` with your real API key. Do not include quotes. Save and close.
9. Start the website:
   ```bat
   python app.py
   ```
10. Open Chrome and go to `http://127.0.0.1:5000`.
11. Click **AI Assistant** and test two different questions, then ask a follow-up. The backend must remain running while you use the site.
12. To stop the server, return to Command Prompt and press `Ctrl+C`.

## If it does not work
- `OPENAI_API_KEY is missing`: check the `.env` file is named exactly `.env` and sits beside `app.py`.
- API key/model/billing error: check your key, API access, selected model availability, and API billing.
- Page will not open: ensure Command Prompt still shows the server running and visit `http://127.0.0.1:5000`.
- Do not open `index.html` by double-clicking it for real AI mode. Use the local server URL so `/api/chat` can work.

## Notes
- Recent chat messages are sent from the browser to the backend for follow-up context. This starter does not save chats to a database.
- This is a local development setup, not a public production deployment. Before public launch, add authentication, rate limiting, monitoring, and hosting configured for secrets.
- AI output can be incorrect. Verify engineering designs, water quality, and safety decisions with qualified professionals and local standards.
- Location search is a map-search helper, not a directory of verified contractors.
- This is a hackathon prototype: rainfall and ward values are sample inputs, not a live forecast or verified city dataset. Do not claim live IoT sensor readings unless you actually connect hardware.
- For a stronger judging demo, show one clear scenario: enter rainfall and roof details, calculate collected litres, demonstrate tank overflow in the planner, then ask the AI to interpret the current values and recommend practical actions.

API reference: https://platform.openai.com/docs/api-reference/responses
API keys: https://platform.openai.com/api-keys


FINAL VISUAL EDITION
- Refreshed responsive layout, navigation, cards, calculator controls, dashboard tables, and chat styling.
- Added a visual home hero and quick feature strip without adding unverified live-data claims.
- Rainfall/ward data remains sample data unless you replace it.
- Run and test on your own computer before presenting; the AI needs a valid API key and API billing/access.
