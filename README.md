# tripplanner
✈️ Trip Planner

An AI-powered trip planning tool that researches, filters, and ranks sights and restaurants for international travel — built as a single-page web app running inside Claude Cowork.

What it does

Enter a destination city and the tool returns a ranked shortlist of places to visit or eat, with quality summaries, star ratings, traveler reviews, and walkability notes. A pin map shows the spatial layout of all results. You make the final call — the AI never decides for you.

Key principle: AI narrows and ranks. Human chooses.

Features
🏛 Separate sections for Sights and Restaurants
⭐ Star ratings + traveler review quotes for each result
📍 SVG pin map with color-coded pins (gold = top pick, teal = sight, orange = restaurant)
🗺 Open in Google Maps link for multi-stop directions
🔗 Google + TripAdvisor search links per location
✅ Per-card deselect toggle — uncheck any result to exclude it
📋 Copy Text — formatted itinerary text for the selected picks
📊 Copy Table — TSV format that pastes directly into Google Sheets or Excel
Filters by neighborhood, count (3 / 5 / 7 results), and custom notes/preferences
How to use
Open the tool in Claude Cowork
Enter your destination city
Choose Sights, Restaurants, or Both
Optionally add a neighborhood focus, result count, and any preferences (e.g. "no tourist traps")
Click Find Top Picks
Review the ranked results, map, and links
Uncheck any picks you don't want
Use Copy Text to paste into a notes app or Copy Table to paste into a spreadsheet
Tech
Single-file HTML/CSS/JS — no framework, no build step
AI calls powered by window.cowork.askClaude() (Claude Cowork built-in — no API key required)
Map rendered as inline SVG using coordinates returned by Claude
Google Maps directions link constructed from clean search_name fields
Limitations
Requires Claude Cowork to run — window.cowork.askClaude() is only available inside the Cowork environment
Map shows approximate pin positions based on Claude's coordinate estimates, not live GPS data
Review quotes are synthesized consensus from Claude's training data, not scraped live
Project context

Built as part of the TMMBA 522 IMPACT framework project. Modules completed:

Module	Topic	Status
1	Intent — problem, stakes, success metric	✅
2	Mental Model — AI vs. human task ownership, autonomy ladder	✅
3	Plumbing — n8n automation for geocoding + walking distances	✅
4	UI — this tool	✅

v1 success metric: Go from no candidates to a ranked shortlist ready to choose from, for a full 2-week trip, in under one hour.

Parked for later versions: group coordination with trip partners, day sequencing and pacing, bookings.

Future ideas
Connect to Google Sheets to read/write trip itinerary data directly
Live distance calculation using the existing n8n + OpenRouteService automation
Day sequencing view — arrange selected picks into a walking route
Export to PDF itinerary
