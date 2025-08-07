# ALXprodev-Devops — Advanced_shell Pokémon API Automation

## Overview

This repository contains shell scripts that automate interactions with the [Pokémon API](https://pokeapi.co/), demonstrating advanced shell scripting skills including API requests, JSON parsing, batch processing, error handling, and parallel execution.

These scripts are designed as part of the ALX DevOps program to practice automation, data extraction, and processing in real-world scenarios.

---

## Directory Structure

```

Advanced\_shell/
├── apiAutomation-0x00             # Fetch single Pokémon data (Pikachu)
├── data\_extraction\_automation-0x01 # Extract Pokémon details from JSON
├── batchProcessing-0x02           # Sequential batch fetch of multiple Pokémon
├── batchProcessing-0x04           # Parallel batch fetch for faster retrieval
├── summaryData-0x03               # Generate CSV report and averages
├── pokemon\_data/                  # Directory storing Pokémon JSON data files
├── data.json                     # Pikachu API response JSON file
├── errors.txt                    # Logs of API request errors
└── README.md                     # This documentation file

````

---

## Scripts and Usage

### 1. `apiAutomation-0x00`
Fetches data for **Pikachu** from the Pokémon API and saves it to `data.json`.

```bash
./apiAutomation-0x00
````

* Logs errors to `errors.txt` if the request fails.

---

### 2. `data_extraction_automation-0x01`

Extracts and prints Pikachu's name, type, height, and weight from `data.json`.

```bash
./data_extraction_automation-0x01
```

Example output:

```
Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.
```

---

### 3. `batchProcessing-0x02`

Sequentially fetches data for a list of Pokémon:
`Bulbasaur`, `Ivysaur`, `Venusaur`, `Charmander`, `Charmeleon`.

Stores JSON responses in `pokemon_data/`.

```bash
./batchProcessing-0x02
```

Implements retry logic and logs failures to `errors.txt`.

---

### 4. `batchProcessing-0x04`

Fetches the same list of Pokémon **in parallel** to speed up data retrieval.

```bash
./batchProcessing-0x04
```

---

### 5. `summaryData-0x03`

Generates a CSV report with Pokémon name, height (m), and weight (kg) from all JSON files in `pokemon_data/`.

Calculates and prints average height and weight.

```bash
./summaryData-0x03
```

Output example:

```
CSV Report generated at: pokemon_report.csv

Name,Height (m),Weight (kg)
Bulbasaur,0.7,6.9
Charmander,0.6,8.5
...

Average Height: 1.08 m
Average Weight: 29.48 kg
```

---

## Prerequisites

* `bash` shell
* `curl` for API requests
* `jq` for JSON parsing
* `awk` and `sed` for text processing

Make sure these tools are installed and accessible in your PATH.

---

## How to Run

1. Clone the repository
2. Navigate to `Advanced_shell`
3. Make scripts executable (only required once):

   ```bash
   chmod +x apiAutomation-0x00 data_extraction_automation-0x01 batchProcessing-0x02 batchProcessing-0x04 summaryData-0x03
   ```
4. Run the scripts in the order described above.

---

## Error Handling

* API request failures are logged to `errors.txt`.
* Retry logic in batch scripts attempts up to 3 times before logging an error.

---

