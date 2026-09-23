# Hotel Bookings Data Analysis Project

This project analyzes the Hotel Booking Demand dataset — real booking records from a Resort Hotel and a City Hotel, covering arrivals from 2015 to 2017. The dataset was cleaned and explored to uncover patterns in booking behavior, cancellations, pricing, and guest demographics, using a combination of Python (data cleaning, transformation, and visualization) and an interactive dashboard.

📊 **Project Overview**

* **Bookings analyzed:** 119,390 records
* **Hotels covered:** 2 (Resort Hotel, City Hotel)
* **Average Daily Rate (ADR):** $101.83
* **Tools used:** Python (Pandas, NumPy, SciPy), Matplotlib, Seaborn, Plotly

🗂️ **Repository Structure**


hotel-bookings-analysis/
├── hotel_bookings_data_cleaning_eda.ipynb   # Data cleaning, transformation & visualization
├── data/
│   └── hotel_bookings.csv                   # Raw dataset
├── docs/
│   └── documentation.pdf                    # Full project documentation
└── README.md

🧹 Data CleaningRemoved exact duplicate rows and standardized inconsistent missing-value markers into proper nulls.Handled missing values on a column-by-column basis depending on business context (e.g., dropping rows where country was missing, filling agent/company IDs with 0 to indicate no agency involvement).Filtered out logically invalid records (such as completed stays with zero total nights).

🔧 Data Transformation & Feature EngineeringConverted boolean/flag fields (is_canceled, is_repeated_guest) to proper types.Created unified arrival dates and sorting keys for chronological analysis.Decoded abbreviated categorical codes into full, readable labels while preserving original data fields.Created custom analytical flags (such as room mismatch between reserved and assigned types).

📈 Dashboard Pages & VisualizationsPage NameKey Focus & HighlightsHomeMonthly booking trends and cancellation rates by hotel type.CancellationsTrends by month, customer type, deposit type, and market segment.Demand & SeasonalityBookings by time periods, ADR trends, and geographic distributions.Guest BehaviorRepeat vs. new guests, composition, and special requests vs. cancellations.Revenue & PricingADR trends, lead-time correlation, and distribution across room types.Source & OperationsMarket segments, distribution channels, room mismatches, and top source countries.Chart types include line charts, bar charts, pie charts, box plots, scatter plots, and choropleth maps.

🔍 Key InsightsCancellation Drivers: Deposit type, market segment, and customer type serve as powerful predictive signals for cancellation risk.Engagement Effect: Cancellation rates decrease as the number of special requests increases, indicating that more engaged guests follow through with stays.Pricing Dynamics: ADR exhibits clear seasonal fluctuations, with price variance increasing substantially at longer lead times.Operational Quality: A measurable share of bookings displays a mismatch between reserved and assigned room types, highlighting an area for operational improvement.Geographic Concentration: Booking volumes are heavily concentrated in a select few European source countries, with Portugal representing the largest share.

🚀 Getting StartedClone the repository:Bashgit clone <repo-url>
cd hotel-bookings-analysis
Install the required dependencies:Bashpip install -r requirements.txt
Open the Jupyter Notebook:Bashjupyter notebook hotel_bookings_data_cleaning_eda.ipynb
Requirements: pandas, numpy, scipy, seaborn, matplotlib, plotly

📄 DocumentationSee docs/documentation.pdf for the full write-up, including the complete data dictionary and detailed methodology notes.
