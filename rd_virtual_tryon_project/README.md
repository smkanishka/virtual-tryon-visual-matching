# R&D Prototype: Virtual Try-On and Visual Matching

## Overview

This project compares two basic image-processing approaches for try-on previews and implements a visual matching prototype using a catalog of 50 garment images.

## Features

- Person and garment image inputs
- Approach 1: garment overlay
- Approach 2: image blending
- Top-five visual matching
- Latency comparison for 10 sample pairs per approach
- Feasibility memo

## Project Structure

- `data/person_images/` — person images
- `data/garment_images/` — garment images
- `data/catalog/` — 50 garment catalog images
- `outputs/approach1/` — overlay previews
- `outputs/approach2/` — blending previews
- `outputs/visual_matching_results.csv` — 250 matching result records
- `outputs/latency_comparison.csv` — latency measurements
- `outputs/feasibility_memo.md` — feasibility memo

## Methodology

Approach 1 overlays a resized garment image on a person image. Approach 2 blends a resized garment image with a person's image. Visual matching uses average RGB colour and colour histograms to rank the five most similar catalog items.

## Results

- Catalog size: 50 garment images
- Query images: 50
- Matches per query: 5
- Total matching records: 250
- Approach 1 average latency: 0.3247 seconds
- Approach 2 average latency: 0.3338 seconds

Latency measurements are from one Google Colab run and may vary.

## Limitations

These are basic image-processing prototypes, not realistic AI-powered virtual try-on systems. Colour-based matching does not guarantee similar garment styles, shapes, or designs. No formal human quality evaluation or pretrained AI try-on comparison has been completed.

## Privacy

Use images only with appropriate permission and consent. Restrict access to personal photographs, avoid public sharing without permission, and delete test images when no longer required.

## Reproduction

Open `R&D_task.ipynb` in Google Colab, ensure the input images and dependencies are available, and run the notebook cells in order. Review the generated previews, latency measurements, visual matching CSV, and feasibility memo.

File paths may need adjustment when reproducing the project in another environment.
