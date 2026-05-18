# Recognizing Vehicle Identity in Real-Time Video Streams Using Frame-to-Frame Tracking

A real-time vehicle recognition system that reduces redundant video processing using frame-to-frame tracking and visual fingerprinting. The project combines lightweight similarity checking, YOLO-based vehicle detection, license plate recognition, and OCR to improve efficiency while maintaining high detection accuracy.

## Overview

Traditional vehicle recognition systems process every frame in a video stream, which causes unnecessary computation and processing delays. This project introduces a detect-on-change approach that skips visually redundant frames and only performs inference when meaningful scene changes are detected.

The system uses:
- Frame-to-frame tracking
- Levenshtein distance visual fingerprinting
- YOLO-based vehicle detection
- License plate localization
- OCR-based text extraction

## Features

- Real-time vehicle recognition
- Redundant frame suppression
- YOLO vehicle detection
- License plate recognition
- OCR text extraction using EasyOCR
- Lightweight frame similarity tracking
- Reduced computational overhead
- Optimized for limited hardware environments

## Methodology

### 1. Frame Extraction
Video streams are divided into ordered frames at 30 FPS.

### 2. Visual Fingerprinting
Frames are:
- Converted to grayscale
- Downscaled by 50%
- Serialized into byte-level signatures

### 3. Frame-to-Frame Tracking
Levenshtein distance is used to compare consecutive frame signatures.

- Similar frames are skipped
- Distinct frames trigger recognition

### 4. Vehicle Recognition Pipeline
The selected frames pass through:
- YOLO Vehicle Detector
- License Plate Detector
- EasyOCR Text Recognition

## Experimental Results

Dataset:
- Resolution: 1080p
- FPS: 30
- Duration: 2 hours, 19 minutes, 11 seconds
- Total Frames: 250,580

Performance at optimal threshold (`m = 0.49`):
- 100% vehicle detection reliability
- 475 unique vehicles detected
- 72.49% frame reduction
- 69.66% processing time reduction

## Tech Stack
- Levenshtein
- Python
- OpenCV
- YOLO
- EasyOCR
- NumPy
