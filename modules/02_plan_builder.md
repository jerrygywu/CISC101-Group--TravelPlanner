### **Module 2 — Plan Builder (Options → Days)**

Create a short list of candidate activities (e.g., attractions, restaurants, parks).  
Each activity includes type, estimated duration, cost range, and distance.

Use a simple loop to build days:

for each day:  
    pick Morning activity (near lodging)  
    pick Midday activity (close by)  
    pick Afternoon activity (different theme)  
    pick Evening restaurant or optional event
    
## ** Module 2 (newly Improved version)**
Module 2 — Plan Builder (Options → Days)
Activity Schema
Each candidate activity must include:

Type (e.g., attraction, restaurant, park, event)

Estimated duration

Cost range

Travel time (from lodging or previous activity, in minutes)

Opening hours (explicitly checked against slot time)

Suitability tags (e.g., family-friendly, mobility accessible, dietary options)

Day Construction Logic
Use a structured loop to build each day:

Timeboxing with buffers

Morning slot (09:00) → activity within 30 minutes travel time; add 30–45 min transit buffer before next slot

Midday slot (12:00) → activity clustered near morning location; ensure opening hours overlap; buffer included

Afternoon slot (15:00) → activity with different theme; allow longer duration; buffer included

Evening slot (18:30) → restaurant or optional event; reservation flag considered; buffer included

Selection Rules
Quantified proximity: Replace “near lodging” with “within 30 minutes travel time.” Prioritize clustering activities to minimize total travel.

Opening hours check: Only select activities open during the slot window.

Suitability check: Ensure activity matches user constraints (family, accessibility, dietary).

Theme diversity: Afternoon activity must differ in theme from morning/midday.

Robustness Enhancements
Partial Days:

If arrival/departure limits available time, reduce plan to one or two slots.

Prioritize proximity and short-duration activities.

Weather Backups:

For outdoor activities, attach an indoor alternative with similar duration and theme.

Backup is automatically suggested if forecast indicates poor weather.
