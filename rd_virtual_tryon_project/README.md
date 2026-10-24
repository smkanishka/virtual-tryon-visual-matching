# R&D Prototype: Virtual Try-On and Visual Matching

## Overview
This project compares two basic image-processing approaches for try-on previews and creates a visual matching prototype.

## Features
- Person and garment image inputs
- Approach 1: garment overlay
- Approach 2: image blending
- Top-5 visual matching results
- Latency comparison for 10 sample pairs
- Feasibility memo

## Project Structure
- data/person_images/: person photos
- data/garment_images/: garment images
- data/catalog/: garment catalog
- outputs/approach1/: overlay previews
- outputs/approach2/: blending previews
- outputs/visual_matching_results.csv: matching results
- outputs/latency_comparison.csv: latency measurements
- outputs/feasibility_memo.md: feasibility memo

## Methodology
Approach 1 overlays a resized garment image on a person image.
Approach 2 blends the person image with a resized garment image.
Visual matching ranks catalog images using average RGB color distance.

## Results
Ten sample pairs were processed using each approach.
Approach 1 average latency: 0.3247 seconds.
Approach 2 average latency: 0.3338 seconds.
Visual matching generated 55 result records for 11 catalog images.

## Limitations
These are basic image-processing prototypes, not realistic AI-powered virtual try-on systems. The catalog contains 11 images rather than the target of approximately 50. Color similarity does not guarantee that two garments have similar styles.

## Privacy
Use person photos only with appropriate consent. Avoid publicly sharing identifiable images, restrict access, and delete test photos when they are no longer needed.

## Reproduction
Run the notebook cells in order to install dependencies, load images, generate previews, run visual matching, measure latency, and create the feasibility memo.
