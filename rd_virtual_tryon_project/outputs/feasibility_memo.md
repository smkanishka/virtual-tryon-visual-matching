# Feasibility Memo: Virtual Try-On and Visual Matching Prototype

## 1. Objective

The objective of this prototype is to evaluate two lightweight image-processing approaches for virtual try-on previews and develop a visual matching system that returns the five most visually similar garment images from a catalog of 50 items.

## 2. Approaches Evaluated

**Approach 1: Garment Overlay**

The garment image is resized and placed over the person's image. This method is simple and fast, but it does not adapt the garment to the person's body shape, pose, or perspective. It should be treated as a basic visual demonstration rather than realistic virtual try-on.

**Approach 2: Image Blending**

The garment image is resized and blended with the person's image. This demonstrates a second image-processing method, but blending may affect the entire image and does not realistically replace the person's existing clothing.

Neither approach uses a trained virtual try-on model.

## 3. Latency Comparison

Ten sample person–garment pairs were processed using each approach.

| Metric | Approach 1 | Approach 2 |
|---|---:|---:|
| Number of sample pairs | 10 | 10 |
| Average latency | 0.3247 seconds | 0.3338 seconds |
| Total processing time | 3.2473 seconds | 3.3383 seconds |

Approach 1 was approximately 0.0091 seconds faster per pair in this run. These measurements were collected in Google Colab and may vary depending on the runtime environment. They measure the prototype's image-processing time, not AI model inference time.

## 4. Visual Matching Results

The visual matching prototype uses a catalog of 50 garment images and returns five ranked matches for each query image. The generated CSV contains 250 result records: 50 query images multiplied by five matches per query.

The current baseline uses simple image features, including average RGB colour and colour histograms, to estimate visual similarity. It is inexpensive and computationally lightweight. However, it mainly captures colour similarity and may not reliably understand garment categories, patterns, shapes, or semantic design.

Some zero-distance results may occur when images are duplicates or nearly identical. Therefore, these scores should not be interpreted as proof of complete visual or semantic similarity.

## 5. Quality and Feasibility

Both try-on approaches demonstrate a reproducible image-processing workflow, but neither produces realistic garment fitting or replacement. Their main value is to demonstrate and compare two simple techniques.

The visual matching system meets the prototype's catalog-size and top-five output requirements. However, its results are a baseline and have not been validated through a formal human evaluation.

A more advanced system could use a pretrained virtual try-on model, person and garment segmentation, pose estimation, or image embeddings. Such alternatives should be tested on the same sample pairs and catalog before selecting a production solution.

## 6. Cost Considerations

The prototype uses Python image-processing libraries and was developed and tested in Google Colab. No paid inference API was used in the reported tests.

This does not mean the overall solution is cost-free. Development time, storage, computing resources, hosting, and future model inference may introduce costs. Actual costs would depend on the selected model, hardware, usage volume, and deployment method.

## 7. Privacy and Image-Consent Risks

Person photographs may contain identifiable personal information. The prototype should use images that are permitted for the intended purpose and obtain appropriate consent before processing personal photographs.

Recommended safeguards include restricting access to uploaded images, avoiding public sharing of raw personal photographs, securely storing files, and deleting them when no longer required. Before using third-party models or hosting services, review their privacy policies, retention practices, and data-handling terms. These measures reduce risk but do not replace a formal privacy or legal review.

## 8. Recommendation

The current implementation is suitable as a proof of concept, not as a production-ready virtual try-on service.

Approach 1 was marginally faster in the measured run, but latency alone does not establish better visual quality. Neither approach provides realistic try-on results. A pretrained virtual try-on model should be evaluated on the same ten sample pairs, with quality and latency assessed separately.

For visual matching, image embeddings could improve semantic similarity beyond simple colour features. Future evaluation should consider relevance of the top-five results, processing speed, computational cost, and performance across different garment colours and styles.

## 9. Limitations and Conclusion

The prototype compares two basic image-processing techniques and provides a top-five visual matching baseline over a 50-image catalog. It does not include custom model training, production integration, video try-on, body measurement, or size prediction.

The latency measurements are from a single Colab run, and no formal human quality scoring or pretrained AI try-on comparison has been completed. Results should therefore be interpreted as preliminary.

Overall, the project demonstrates the feasibility of implementing a lightweight try-on image-processing workflow and a basic visual matching pipeline. Further model evaluation and quality testing are needed before making claims about realistic try-on performance or production readiness.
