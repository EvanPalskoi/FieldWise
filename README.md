🌱 FieldWise
Data-driven crop planning and crop-rotation guidance, built for the 2026 NASA Space Apps Challenge.

FieldWise is a web application that helps farmers and growers explore what to plant next based on where their field is located, what was grown previously, and relevant environmental conditions. Instead of relying on a single dataset, it brings together climate, soil, crop-suitability, planting-calendar, and agricultural-economics information to make crop options easier to compare.
Try the live FieldWise website:

https://cache-check---fieldwise-ajl6erw3ka-ue.a.run.app/

Project status: Interactive web demo deployed on Google Cloud Run. Initial location screening can take several minutes while data is processed.

Why we built it
Choosing the next crop is more than finding something that grows in a region. Weather patterns, soil conditions, planting windows, and the previous crop can all affect whether a choice makes sense. Relevant data exists across multiple scientific sources, but comparing it can be difficult.

FieldWise was built to bring these considerations into one accessible workflow so that users can explore crop and rotation options with data-backed context, rather than manually navigating multiple datasets.
What FieldWise does
- Location-based screening: Evaluate crop options for a selected location.
- Crop-rotation context: Take the most recently grown crop into account when exploring what to plant next.
- Flexible inputs: Optionally specify when the field will be ready, irrigation access, and local measurements such as soil pH, rainfall, or temperature.
- Multiple environmental datasets: Draw on weather, soil, and modeled crop-suitability information rather than a single source.
- Planting-window context: Consider available regional planting-calendar information.
- Practical comparisons: Present crop and rotation results in an interactive website.
- Additional exploration: Surface a separate “Food crops to investigate” section for possibilities that warrant further review; these are not equivalent to the primary suitability recommendations.
How it works
1. Enter field information. Choose a location and the last crop grown there. Add optional details such as a field-ready date, irrigation availability, or locally measured conditions.
2. Gather relevant context. The backend uses available climate, soil, crop-suitability, planting-calendar, and agricultural-economics data.
3. Screen crop options. The analysis evaluates candidate crops against location-specific information and rotation considerations.
4. Review the results. Explore the returned crop and rotation options, including any separately identified crops that need additional investigation.
Some analyses are processed asynchronously: the website starts a screening job, checks its status, and displays the results when they are ready.
Data sources
Source	Role in FieldWise
NASA POWER	Historical weather and climate context, including precipitation and temperature
SoilGrids	Estimated soil properties, including soil pH where available
FAO GAEZ	Modeled agro-ecological crop-suitability estimates
Regional planting calendars	Planting-season context, using available calendar datasets
Agricultural-economics data	Additional context for comparing practical crop options


Coverage and precision vary by region and dataset. FieldWise is designed to use the information available for the selected location, and some results may require additional local verification.
Technology
Layer	Technologies
Frontend	React, TypeScript
Backend and analysis	Python, FastAPI
Deployment	Docker, Google Cloud Run
Data	NASA POWER, SoilGrids, FAO GAEZ, and complementary agricultural datasets


Try it yourself
Open FieldWise →

https://cache-check---fieldwise-ajl6erw3ka-ue.a.run.app/

For a first test, pick a location and enter the most recent crop. Leave optional measurements blank if you don't have them, then run the analysis and review the results. The initial screen may take a few minutes.
Limitations
FieldWise is a decision-support prototype, not a guarantee of crop performance or profitability. Weather datasets, gridded soil estimates, modeled suitability scores, and regional planting calendars may not reflect every condition on a specific farm. The “Food crops to investigate” results are exploratory candidates and should not be treated as validated primary recommendations.

Before making planting decisions, users should confirm local growing conditions, planting dates, crop requirements, and economic considerations with appropriate regional sources or agricultural professionals.
About the project
FieldWise was developed collaboratively for the 2026 NASA Space Apps Challenge, with an emphasis on combining scientific datasets and software engineering into a usable crop-planning tool.

This is an independent hackathon project and is not an official NASA or FAO product.
