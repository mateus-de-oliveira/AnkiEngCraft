# Anki Deck Creator

Anki Deck Creator is a Python script that reads sentences from an input file (CSV or TXT format), translates the sentences using Google Translate, generates audio using Azure Speech API, and creates Anki decks (.apkg) or CSV files with the translated sentences and audio files.

## Requirements

- Python 3.6+
- Azure Speech API key (you can sign up for a free trial)

## Installation

1. Clone the repository:

```bash
git clone git@github.com:willycamargo/csv-google-translate-python.git
cd csv-google-translate-python
```

2. Install the required packages:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file using the provided `.env.example` file and fill in the `AZURE_SPEECH_KEY` and `AZURE_REGION` with your Azure Speech API key and region, respectively:

```bash
cp .env.example .env
```

## Getting Started

### Input Files

Prepare an input file with sentences in CSV or TXT format.

- CSV format: The CSV file should have a header with a `sentence` column, e.g.:
```csv
id,sentence
1,The cat is on the mat.
2,The sky is blue.
```

- TXT format: The TXT file should have one sentence per line, e.g.:
```txt
The cat is on the mat.
The sky is blue.
```

Place your input file in the `input` directory.

### Running the Script

Run the script using the following command:

```bash
python anki_deck_creator.py --input input_file_name --format output_format --output output_file_name
```


- `input_file_name`: The name of the input file (with extension) located in the `input` directory.
- `output_format`: The desired output format (`anki` for Anki deck or `csv` for CSV file).
- `output_file_name`: The name of the output file (without extension).

For example, to create an Anki deck from the `example.csv` input file, run:

```bash
python anki_deck_creator.py --input example.csv --format anki --output my_deck
```

The generated Anki deck or CSV file will be saved in the `output` directory.

## License

This project is licensed under the MIT License.
