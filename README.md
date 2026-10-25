# Virtual Try-On and Visual Matching Prototype

## Overview

This R&D project explores two basic image-processing approaches for virtual try-on previews and develops a visual matching prototype that retrieves similar garment images from a catalog of 50 items.

## Features

- Garment overlay preview (Approach 1)
- Image blending preview (Approach 2)
- Top-5 visual matching using colour-based image features
- Latency comparison using 10 person–garment pairs per approach
- 50-image garment catalog
- Feasibility memo covering quality, cost, privacy, and limitations

## Methodology

**Approach 1: Garment Overlay**  
Resizes and overlays a garment image on a person's image.

**Approach 2: Image Blending**  
Resizes and blends a garment image with a person's image.

**Visual Matching**  
Uses average RGB colour and colour histograms to rank visually similar catalog images. The system returns five matches for each of the 50 query images.

## Results

| Metric | Result |
|---|---|
| Catalog images | 50 |
| Query images | 50 |
| Matches per query | 5 |
| Total matching records | 250 |
| Approach 1 average latency | 0.3247 seconds |
| Approach 2 average latency | 0.3338 seconds |

Latency measurements are from one Google Colab run and may vary between environments.

## Project Files

- `R&D_task.ipynb` — prototype notebook
- `rd_virtual_tryon_project/data/person_images/` — person images
- `rd_virtual_tryon_project/data/garment_images/` — garment images
- `rd_virtual_tryon_project/data/catalog/` — 50-image catalog
- `rd_virtual_tryon_project/outputs/approach1/` — overlay previews
- `rd_virtual_tryon_project/outputs/approach2/` — blending previews
- `rd_virtual_tryon_project/outputs/visual_matching_results.csv` — top-five matching results
- `rd_virtual_tryon_project/outputs/latency_comparison.csv` — latency measurements
- `rd_virtual_tryon_project/outputs/feasibility_memo.md` — feasibility evaluation

## Reproduction

1. Open `R&D_task.ipynb` in Google Colab.
2. Follow the notebook cells in order.
3. Make sure the required input images and dependencies are available.
4. Run the try-on preview and latency comparison cells.
5. Run visual matching using the 50-image catalog.
6. Review the generated preview images and CSV results.

Exact file paths may need adjustment when running the notebook in a different environment.

## Limitations

The two try-on approaches are basic image-processing demonstrations, not realistic AI-powered virtual try-on systems. They do not adapt garments to body shape, pose, or perspective.

Visual matching is based on colour-related features. Similar colours do not guarantee similar garment styles or designs. The system has not been validated through a formal human evaluation.

## Privacy and Consent

Use only images permitted for the intended purpose. Obtain appropriate consent before processing personal photographs, restrict access to identifiable images, avoid publishing them without permission, and delete them when no longer needed. Review third-party service data-handling practices before uploading personal images.

## Conclusion

This prototype demonstrates a lightweight try-on image-processing workflow and a colour-based visual matching baseline. Further testing with pretrained virtual try-on models and image embeddings is recommended before production use.
