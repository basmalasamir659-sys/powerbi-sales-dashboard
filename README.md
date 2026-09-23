Hotel Bookings Data Analysis Project
This project analyzes the Hotel Booking Demand dataset — real booking records from a Resort Hotel and a City Hotel, covering arrivals from 2015 to 2017. The dataset was cleaned and explored to uncover patterns in booking behavior, cancellations, pricing, and guest demographics, using a combination of Python (data cleaning, transformation, and visualization) and an interactive dashboard.

📊 Project Overview
Bookings analyzed: 86,323
Hotels covered: 2 (Resort Hotel, City Hotel)
Average Daily Rate (ADR): 107.34
Charts built: 27, across 6 dashboard pages
Tools used: Python (Pandas, NumPy, SciPy), Matplotlib, Seaborn, Plotly
🗂️ Repository Structure
hotel-bookings-analysis/
├── hotel_bookings_data_cleaning_eda.ipynb   # Data cleaning, transformation & visualization
├── data/
│   └── hotel_bookings.csv                   # Raw dataset
├── docs/
│   └── documentation.pdf                    # Full project documentation
└── README.md
🧹 Data Cleaning
Removed exact duplicate rows.
Standardized inconsistent missing-value markers ('', "Nan", "None", "NA") into proper nulls.
Handled missing values on a column-by-column basis, based on what "missing" actually meant for each field:
Children — negligible missing rows dropped.
Country — rows dropped (no logical default; imputing would distort nationality-based charts).
Agent / Company — missing values filled with 0, since a missing ID reflects a genuine business meaning (no agent/company involved), not an unknown value.
Zero-night, non-canceled bookings — removed, since a completed stay of zero total nights is not logically possible.
🔧 Data Transformation & Feature Engineering
Converted is_canceled and is_repeated_guest to proper boolean types.
Built a unified arrival_date field from year, month, and day columns.
Added arrival_date_month_number for correct calendar-order sorting.
Created has_agent and has_company flag columns.
Decoded abbreviated categorical fields into full, readable labels (meal_label, market_segment_label, distribution_channel_label) while preserving original codes.
Renamed adr → average_daily_rate (ADR) for clarity.
Merged in a full ISO country reference table to get readable country names (including manual handling of the deprecated TMP code for Timor-Leste).
Created a room_mismatch flag comparing reserved vs. assigned room type.
📈 Dashboard Pages & Visualizations
Page	Charts	Highlights
Home	2	Monthly booking trend, cancellation rate by hotel type
Cancellations	5	Trends by month, customer type, deposit type, market segment
Demand & Seasonality	4	Bookings by month/day, ADR by month, bookings by country (choropleth)
Guest Behavior	5	Repeat vs. new guests, guest composition, special requests vs. cancellation
Revenue & Pricing	5	ADR trend, ADR vs. lead time, ADR by customer/room type, ADR distribution
Source & Operations	6	Market segment, distribution channel, room mismatch, meal plan, top countries
Chart types include line charts, bar charts, pie charts, a box plot, a scatter plot, and a choropleth map.

🔍 Key Insights
Cancellation likelihood varies notably by deposit type, market segment, and customer type — strong predictive signals for cancellation risk.
Cancellation rate tends to decrease as the number of special requests increases, suggesting more engaged guests are less likely to cancel.
ADR shows clear seasonal variation, with variance increasing substantially at longer lead times.
A measurable share of bookings show a mismatch between reserved and assigned room type — a useful operational quality indicator.
Booking volume and guest nationality are heavily concentrated in a small number of source countries, with Portugal dominant given the dataset's origin.
🚀 Getting Started
git clone <repo-url>
cd hotel-bookings-analysis
pip install -r requirements.txt
jupyter notebook hotel_bookings_data_cleaning_eda.ipynb
Requirements: pandas, numpy, scipy, seaborn, matplotlib, plotly

📂 **Deliverables Included**

* `.pbix` Source File
* High-resolution Dashboard Screenshots
* Summary Analytics Overview
