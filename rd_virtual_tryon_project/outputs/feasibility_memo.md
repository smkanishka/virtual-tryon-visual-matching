
# Feasibility Memo: Virtual Try-On and Visual Matching Prototype

## 1. Objective
The objective is to evaluate two lightweight image-processing approaches
for virtual try-on previews and build a visual matching prototype.

## 2. Approaches Evaluated
Approach 1: Garment overlay
The garment image is resized and placed over the person's image.
This is simple and fast, but does not adapt the garment to body shape,
pose, perspective, or existing clothing.

Approach 2: Image blending
The garment image is resized to the person's image dimensions and blended
with it. This is easy to implement, but may affect the entire image and
does not produce a realistic garment replacement.

## 3. Latency Results
Ten sample pairs were processed for each approach.

Approach 1 average latency: 0.3247 seconds.
Approach 2 average latency: 0.3338 seconds.

These measurements are from one Colab run and may vary by environment.
They exclude model inference because neither approach uses a trained model.

## 4. Visual Matching
The prototype compares average RGB color features across a catalog of
11 garment images and returns the five nearest items by Euclidean distance.
The output contains 55 records across 11 query images.

This baseline is inexpensive and fast, but matches mainly by average color.
It does not understand garment type, pattern, shape, or semantic similarity.
The assignment's approximate 50-item catalog has not yet been reached.

## 5. Quality and Feasibility
Both try-on approaches demonstrate a reproducible image-processing workflow,
but neither should be considered realistic virtual try-on.
A production-quality system would require garment/person segmentation,
pose or body-part awareness, and an appropriate virtual try-on model.
A pretrained model or hosted service should be evaluated before production use.

## 6. Cost
The prototype uses open-source Python image-processing libraries and runs
in Google Colab. No paid inference service was used in these tests.
This does not include development time, storage, hosting, or future model costs.

## 7. Privacy and Image Consent
Person photographs can contain identifiable personal information.
Obtain informed consent before uploading or processing images, restrict access,
avoid sharing raw images publicly, and delete them when no longer required.
Use secure storage and review the terms and data-handling practices of any
third-party model or hosting service before sending user photographs.

## 8. Recommendation
Use the current prototype as a proof of concept only.
Approach 1 is marginally faster in this test, but neither approach provides
realistic try-on quality. Evaluate a pretrained virtual try-on model on the
same 10 pairs before choosing a production approach.
Improve visual matching with image embeddings and expand the catalog to
approximately 50 items before drawing stronger conclusions.

## 9. Limitations
The current catalog has 11 items rather than approximately 50.
No trained AI try-on model was evaluated, and visual quality was not scored
using a formal human evaluation. Latency results come from a single run.
