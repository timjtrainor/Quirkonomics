# Quirkonomics Architecture Plan

This document outlines the architecture for the Quirkonomics internal tool, designed to run entirely in a local Docker environment with no external dependencies or authentication layers.


## Overview
	•	Local-only execution
	•	Modular Docker containers via docker-compose
	•	Python-based backend
	•	React frontend
	•	PostgreSQL as primary datastore
	•	PostgREST middleware

## Services (Docker Containers)

1. frontend
	•	React (Vite)
	•	UI components: Dashboard, Data Viewer, Hypothesis Builder, Model Trainer
	•	Serves at localhost:3000

2. backend
	•	Python using FastAPI (CLI mode first)
	•	ML model training, backtest evaluation, hypothesis parser
	•	Optional REST interface later
	•	Serves at localhost:8000

3. postgrest
	•	REST API for CRUD over database tables
	•	Secure via role-based access and schema constraints
	•	Serves at localhost:3001

4. db
	•	PostgreSQL instance
	•	Stores:
	•	FTD and price history
	•	Hypotheses
	•	Backtest results
	•	Model metadata

5. scheduler (optional)
	•	Airflow or cron container
	•	Automates data ingestion and model retraining

6. notebook (optional)
	•	Jupyter Lab for dev experimentation

## Service Communication Flow
	•	frontend → backend: For ML training, backtesting, hypothesis evaluation (CLI or REST)
	•	frontend ↔ postgrest: For direct CRUD on raw and derived data
	•	backend ↔ db: For training data, labels, results
	•	scheduler → backend: For job triggers (e.g., refresh models)

## API Integrations
	•	Initial: SEC FTD (ZIP or FTP), Yahoo Finance (widget or API)
	•	Future: Modular ingestion pipeline for additional sources
	•	API keys and tokens stored via .env or Docker secrets


## Design Notes
	•	Start backend CLI-first to reduce scope
	•	Add FastAPI routes later if needed for dynamic inference or complex triggers
	•	Frontend can function with PostgREST + widgets in MVP-A
