✈️ Trip Planner

An AI-powered trip planning tool that researches, filters, and ranks sights and restaurants for international travel. Enter a destination, get a ranked shortlist with ratings, reviews, a pin map, and one-click export to text or spreadsheet.

Key principle: AI narrows and ranks. You make the final call.

Features
🏛 Separate sections for Sights and Restaurants
⭐ Star ratings + traveler review quotes per result
📍 SVG pin map with color-coded pins (gold = top pick, teal = sight, orange = restaurant)
🗺 Open in Google Maps link for multi-stop directions
🔗 Google + TripAdvisor search links per location
✅ Per-card deselect toggle — uncheck any result to exclude it
📋 Copy Text — formatted itinerary for selected picks
📊 Copy Table — TSV that pastes directly into Google Sheets or Excel
Setup

Requirements: Node.js 18+, an Anthropic API key

bash
# 1. Clone the repo
git clone https://github.com/yourusername/trip-planner.git
cd trip-planner

# 2. Install dependencies
npm install

# 3. Add your API key
cp .env.example .env
# Open .env and paste your Anthropic API key

# 4. Start the server
npm start

Then open http://localhost:3000 in your browser.

How it works

server.js is a minimal Express server that serves the frontend and proxies AI requests to the Anthropic API — your API key stays on the server and is never exposed to the browser.

browser → POST /api/chat → server.js → Anthropic API → response → browser
Project structure
trip-planner/
├── public/
│   └── index.html   # Single-page frontend (HTML/CSS/JS)
├── server.js        # Express server + Anthropic API proxy
├── package.json
├── .env.example     # Copy to .env and add your API key
├── .gitignore       # Excludes .env and node_modules
└── README.md
Deploying (optional)

To share it with others, deploy to Railway or Render (both have free tiers):

Push this repo to GitHub
Connect the repo in Railway/Render
Add ANTHROPIC_API_KEY as an environment variable in the dashboard
Deploy — they'll run npm start automatically
Project context

Built as part of the TMMBA 522 IMPACT framework project.

Module	Topic	Status
1	Intent — problem, stakes, success metric	✅
2	Mental Model — AI vs. human task ownership	✅
3	Plumbing — n8n automation for geocoding + walking distances	✅
4	UI — this tool	✅

v1 success metric: From no candidates to a ranked shortlist for a 2-week trip in under one hour.

Future ideas
Connect to Google Sheets to read/write itinerary data
Live walking distances via the n8n + OpenRouteService automation
Day sequencing — arrange picks into a walking route
Export to PDF itinerary
