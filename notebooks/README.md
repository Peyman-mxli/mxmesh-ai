# MxMesh AI — Notebooks

This directory contains the Google Colab notebooks used to research, develop, test, and document the artificial intelligence components of **MxMesh AI**.

MxMesh AI is an AI-powered 3D generation platform designed to transform images and text into 3D assets and progressively provide tools for texturing, optimization, rigging, animation, visualization, 3D printing, and model export.

---

## Purpose of This Directory

The `notebooks/` directory is the experimental AI workspace of MxMesh AI.

Google Colab is used during the early development stages because it provides access to NVIDIA GPU resources without requiring a local NVIDIA GPU.

Each notebook will focus on a specific AI capability and will be documented separately.

---

## Current Development Goal

The first milestone of MxMesh AI is:

> **Convert a single JPG or PNG image into a textured 3D model.**

The initial pipeline will be:

```text
Input Image
    │
    ▼
Image Preprocessing
    │
    ▼
AI 3D Generation
    │
    ▼
3D Geometry
    │
    ▼
Texture / Materials
    │
    ▼
GLB Model
    │
    ▼
3D Preview
