# Quirkonomics Product Roadmap

This roadmap outlines the phased development of Quirkonomics, an internal tool designed to explore predictive financial models using SEC FTD data and external market sources.

## Phase 1 – Discovery & Validation

	•	Define user personas (e.g. retail traders, AI hobbyists)
	•	Identify core value proposition
	•	Early sketches or prototypes
	
## Phase 2 – MVP Development (Split into MVP-A and MVP-B)

### MVP-A: Data Ingestion & Visualization
	•	SEC Fail-to-Deliver (FTD) data ingestion
	•	Historical financial data ingestion (Yahoo Finance)
	•	Flexible ingestion framework for new APIs/scrapers (deferred)
	•	Display of current price and key financial metrics per symbol (API or embeddable widgets)
	•	Event overlay chart showing FTDs and key metrics over time
	•	Basic hypothesis builder UI (no evaluation logic yet)
	•	Save/load hypothesis configurations locally

### 3 MVP-B: Hypothesis Engine & ML Modeling
	•	Define hypotheses in structured JSON or rule format
	•	Backtesting engine for validating hypotheses
	•	ML model training interface on selected features
	•	View model performance metrics (accuracy, return profiles)
	•	Result visualizer for backtests and predictions

## Phase 3 – Alpha/Beta Testing
	•	Internal testing of MVP functionality
	•	Private iteration cycles with saved test configurations
	•	Data debugging and UX improvement based on feedback

## Phase 4 – Wrap-up and Documentation
	•	Final data and feature documentation
	•	Recorded demo and GitHub project showcase
	•	GitHub README and issue linking for reference
