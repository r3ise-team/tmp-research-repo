# Experiments

This directory contains experiment configurations and scripts.

Each experiment should:
- Be configurable via files (not hard-coded)
- Be repeatable
- Log results and metadata

## Structure

- `configs/`: Configuration files for different experiments
- Experiment scripts should be placed in the root of this directory or in subdirectories

## Running Experiments

1. Create or select a configuration file in `configs/`
2. Run the experiment script with the configuration
3. Results will be logged to the appropriate output directory
