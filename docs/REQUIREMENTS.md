# Quirkonomics Requirements Document

This file outlines all functional and non-functional requirements for the Quirkonomics internal application, broken down by MVP phase.

## Functional Requirements

### MVP -A: Data Ingestion & UI
	1.	Upload or fetch SEC FTD data (ZIP or FTP)
	2.	Ingest historical price/volume data from Yahoo Finance
	3.	Display ticker-level data overlays (price + FTD events)
	4.	Display current data using widgets or embedded content
	5.	Build, save, and reload hypotheses using a basic UI and local storage

### MVP-B: Hypotheses & ML
	6.	Define structured hypothesis logic (JSON-based rule sets)
	7.	Run backtests with historical data and report outcome metrics
	8.	Train ML models on labeled datasets and visualize predictions
	9.	View model performance and export/save metadata
	10.	Evaluate saved hypotheses against fresh data
	11.	Trigger jobs via CLI (for ingestion, training, testing)


## Non-Functional Requirements
	1.	Responsiveness over Speed
	  •	Real-time execution is not required
	  •	UI must give users feedback during long tasks (e.g., loading indicators, active progress)
	2.	Error Handling and Feedback
	  •	Clear, user-friendly error messages for ingestion, ML, and display failures
	  •	Log errors and surface actionable messages when possible
	3.	Portability
	  •	Full system runs locally in Docker
	  •	One-command startup via docker-compose
	4.	Extensibility
	  •	Modular ingestion and ML logic
	  •	Backend and frontend designed for future feature expansion
	5.	Security (Local Only)
	  •	API keys and OAuth tokens stored securely in .env or Docker secrets
	  •	No external auth system required
	6.	Documentation and Usability
	  •	README and usage examples included
	  •	UI accessible and intuitive for technical users
	7.	Data Persistence
	  •	All ingested and derived data is saved to PostgreSQL by default
	  •	Container restarts do not delete stored results
