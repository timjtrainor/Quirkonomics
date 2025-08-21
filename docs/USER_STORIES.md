# Quirkonomics User Stories

These user stories support GitHub issue creation and guide feature-level implementation. They’re organized by MVP phase and reflect strategic goals and implementation constraints.


## MVP-A: Data Ingestion & UI

### 1. Ingest SEC FTD data (FTP polling)
As a trader exploring regulatory market inefficiencies, I want the system to automatically poll and ingest SEC Fail-to-Deliver (FTD) data for all symbols via FTP so I can identify unusual delivery events without manual downloads.

### 2. Ingest historical price/volume data for relevant tickers
As a hypothesis-driven analyst, I want to fetch historical daily price and volume data only for tickers recently appearing in FTD files so I can correlate historical behavior without unnecessary API load.

### 3. Visualize ticker overlays
As a data explorer, I want to view single-ticker price charts with FTD overlays and optionally earnings or volume spikes so I can explore event-based market patterns.

### 4. Display real-time stock data
As a user investigating a specific stock, I want to view its current price and intraday chart via an iframe or API-based widget so I can explore recent action in context.

### 5. Save and manage hypotheses
As a repeat user, I want to persist hypotheses in the PostgreSQL database and have the ability to label, clone, and version them so I can iterate and compare variations over time.

---

## MVP-B: Hypotheses & ML

### 6. Define a hypothesis using JSON logic
As a technically fluent user, I want to define hypotheses using JSON rule syntax supporting AND/OR logic and multiple time windows so I can test complex event-driven conditions without building a full UI.

### 7. Backtest hypotheses with metrics
As a researcher, I want to backtest hypotheses using custom date ranges and return key performance metrics (win rate, P&L, volatility) so I can evaluate historical validity of signal conditions.

### 8. Train ML models with scikit-learn
As an experimenter, I want to train scikit-learn models using labeled datasets generated from hypotheses and optionally adjust those labels so I can refine prediction accuracy.

### 9. Schedule and log backend jobs
As a developer, I want to trigger ingestion and model jobs from a cron-enabled container that logs activity and stores metadata so I can troubleshoot runs and monitor behavior over time.

### 10. Compare model results visually
As an evaluator, I want to eventually compare output of different hypotheses or models in a visual format so I can decide which strategies show consistent predictive value.

> Note: Metrics and layout preferences for visual comparisons are still under consideration.

