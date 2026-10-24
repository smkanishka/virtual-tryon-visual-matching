
 Virtual Try-On and Visual Matching Prototype

 Overview
This project is an R&D prototype exploring basic image-processing approaches for virtual try-on previews and visual garment matching.

 Features
- Garment overlay preview (Approach 1)
- Image blending preview (Approach 2)
- Top-5 garment matching using average RGB color distance
- Latency comparison for 10 sample pairs per approach
- Feasibility memo and project documentation

 Methodology
Approach 1 overlays a resized garment image on a person image. Approach 2 blends the person image with a resized garment image. Visual matching ranks catalog images by average RGB color distance.

 Results
- Approach 1 average latency: 0.3247 seconds
- Approach 2 average latency: 0.3338 seconds
- 11 catalog images and 55 matching result records

 Limitations
These are basic image-processing prototypes, not realistic AI-powered virtual try-on systems. The catalog contains 11 images rather than approximately 50, and color similarity does not guarantee similar garment styles.

 Privacy
Use person photos only with appropriate consent. Avoid publishing identifiable photographs without permission.

 Reproduction
Run the provided Google Colab notebook cells in order to generate previews, visual matching results, and latency measurements.
