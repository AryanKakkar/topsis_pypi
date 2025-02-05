# TOPSIS Implementation

## Overview
This Python package provides a straightforward implementation of the TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) method for multi-criteria decision-making. With this tool, you can rank alternatives based on multiple criteria using weights and impacts for each criterion.

## Features
- Easy-to-use command-line interface.
- Supports customizable weights and impacts for criteria.
- Outputs a ranked list of alternatives with TOPSIS scores.
- Handles CSV input and output for seamless integration with data workflows.

## Installation

To install the package, use the following command:

```bash
pip install 102203148-topsis
```

## Usage

### Command-Line Interface

To execute TOPSIS, use the following command:

```bash
python topsis.py <input_file> <weights> <impacts> <output_file>
```

### Arguments
- `<input_file>`: Path to the CSV file containing the input data. The first column should contain alternative names, and subsequent columns should contain numerical criteria values.
- `<weights>`: Comma-separated weights for each criterion (e.g., `1,2,3`).
- `<impacts>`: Comma-separated impacts for each criterion (`+` for benefit criteria, `-` for cost criteria, e.g., `+, -, +`).
- `<output_file>`: Path to the CSV file where the results will be saved.

### Example

Suppose you have the following input file (`data.csv`):

| Alternative | Criterion 1 | Criterion 2 | Criterion 3 |
|-------------|-------------|-------------|-------------|
| A1          | 250         | 16          | 12          |
| A2          | 200         | 20          | 8           |
| A3          | 300         | 12          | 15          |
| A4          | 275         | 14          | 10          |

To rank the alternatives with weights `1,1,1` and impacts `+, +, -`, run:

```bash
python topsis.py data.csv 1,1,1 +,+,- results.csv
```

The output (`results.csv`) will include the TOPSIS scores and ranks:

| Alternative | Criterion 1 | Criterion 2 | Criterion 3 | Topsis Score | Rank |
|-------------|-------------|-------------|-------------|--------------|------|
| A1          | 250         | 16          | 12          | 0.6547       | 2    |
| A2          | 200         | 20          | 8           | 0.3001       | 4    |
| A3          | 300         | 12          | 15          | 0.8234       | 1    |
| A4          | 275         | 14          | 10          | 0.4921       | 3    |

## Input File Requirements
- The input file must be a CSV with at least three columns.
- The first column should contain the names of the alternatives.
- The remaining columns should contain numerical values for criteria.

## Output File
The output file will contain the original data along with two additional columns:
- `Topsis Score`: The calculated TOPSIS score for each alternative.
- `Rank`: The rank of each alternative based on the TOPSIS score (1 = best).

## Error Handling
The package validates inputs and raises errors for:
- Input files with fewer than three columns.
- Mismatched lengths of weights or impacts compared to the criteria.
- Invalid impact values (must be `+` or `-`).

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request.

## Contact
For questions or feedback, please contact [aryan10767@gmail.com].

