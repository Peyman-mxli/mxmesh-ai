# MxMesh AI — Notebooks

This directory contains the **Google Colab notebooks** used to research, develop, test, and document the artificial intelligence components of **MxMesh AI**.

MxMesh AI is an AI-powered 3D generation platform designed to transform **images and text into 3D assets** and progressively provide tools for texturing, optimization, rigging, animation, visualization, 3D printing, and model export.

---

## Purpose of This Directory

The `notebooks/` directory is the experimental AI workspace of **MxMesh AI**.

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
```

Once this pipeline works reliably, it will become the foundation for the **MxMesh AI web application**.

---

## Notebooks

### Image to 3D

**Notebook:**

```text
MxMesh-AI-Image-to-3D.ipynb
```

### Purpose

This notebook will be used to:

- Configure the Google Colab GPU environment
- Verify NVIDIA CUDA availability
- Install the required AI libraries
- Load an open-source Image-to-3D model
- Upload a JPG or PNG image
- Preprocess the input image
- Generate 3D geometry
- Generate textures and materials
- Export the generated model
- Test GLB output
- Document experiments and results

### Status

**In Development**

---

## Planned AI Experiments

Future notebooks may include the following areas.

### 1. Image to 3D

Generate a 3D model from a single reference image.

```text
Image
  ↓
AI Model
  ↓
3D Geometry
  ↓
Texture
  ↓
GLB
```

---

### 2. Multi-Image to 3D

Generate more accurate 3D geometry using several images of the same object from different viewpoints.

Example:

```text
Front Image ──┐
Side Image  ──┼──► AI 3D Generation ──► 3D Model
Back Image  ──┤
Top Image   ──┘
```

---

### 3. Text to 3D

Generate 3D assets from natural-language prompts.

Example prompt:

```text
A small medieval wooden treasure chest
with iron details and gold decorations.
```

Possible pipeline:

```text
Text Prompt
    │
    ▼
AI Generation
    │
    ▼
3D Geometry
    │
    ▼
Texture / Materials
    │
    ▼
3D Model
```

---

### 4. AI Texturing

Generate or improve textures and materials for 3D models.

Possible features include:

- Texture generation
- Texture enhancement
- PBR materials
- Albedo maps
- Normal maps
- Roughness maps
- Metallic maps
- Material editing

---

### 5. Mesh Optimization

Experiment with different techniques for improving generated geometry.

Possible operations include:

- Polygon reduction
- Mesh cleanup
- Retopology
- UV generation
- UV unwrapping
- Geometry optimization
- Mesh simplification
- Hole repair

---

### 6. Automatic Rigging

Automatically create skeletons for supported 3D characters.

Possible pipeline:

```text
3D Character
     │
     ▼
Character Analysis
     │
     ▼
Skeleton Generation
     │
     ▼
Skinning
     │
     ▼
Rigged Character
```

---

### 7. Animation

Apply animations to supported rigged characters.

Possible examples include:

- Idle
- Walk
- Run
- Jump
- Attack
- Character actions

Possible pipeline:

```text
Rigged Character
       │
       ▼
Animation
       │
       ▼
Animated 3D Model
```

---

### 8. 3D Printing

Prepare generated models for 3D printing.

Possible operations include:

- Mesh repair
- Watertight geometry
- Hole detection
- Scaling
- Polygon optimization
- Print validation
- STL export
- 3MF export

---

## Planned Export Formats

MxMesh AI aims to progressively support common 3D formats.

| Format | Purpose |
|---|---|
| **GLB** | Web and real-time 3D |
| **OBJ** | General 3D interchange |
| **FBX** | Animation and game development |
| **STL** | 3D printing |
| **USDZ** | Apple AR and spatial experiences |
| **BLEND** | Blender workflows |
| **3MF** | Modern 3D printing |

Support for each format will be implemented and tested progressively.

---

## Development Environment

Initial AI development will use:

- Python
- PyTorch
- CUDA
- Google Colab
- NVIDIA GPU
- Open-source 3D generation models
- Git
- GitHub

---

## Google Colab

Google Colab will initially serve as the GPU development environment for MxMesh AI.

The first notebook is:

```text
MxMesh-AI-Image-to-3D.ipynb
```

The notebook will initially use an NVIDIA **T4 GPU** when available.

The first GPU verification command will be:

```python
!nvidia-smi
```

This allows us to verify that Colab has successfully assigned an NVIDIA GPU before installing or running the Image-to-3D model.

---

## Local Development

The local computer will primarily be used for:

- Source-code development
- Git
- GitHub
- Documentation
- Frontend development
- Backend development
- API development
- 3D visualization
- Project management

GPU-intensive AI inference will initially be performed using **Google Colab**.

---

## Planned MxMesh AI Architecture

The long-term architecture is expected to evolve toward:

```text
                         MxMesh AI
                             │
            ┌────────────────┴────────────────┐
            │                                 │
        Frontend                           Backend
            │                                 │
            │                                 ▼
            │                            MxMesh API
            │                                 │
            └────────────────┬────────────────┘
                             │
                             ▼
                         Job System
                             │
                             ▼
                         GPU Worker
                             │
               ┌─────────────┼─────────────┐
               │             │             │
               ▼             ▼             ▼
           Image→3D      Text→3D      Multi-Image→3D
               │             │             │
               └─────────────┼─────────────┘
                             │
                             ▼
                        3D Processing
                             │
                ┌────────────┼────────────┐
                │            │            │
                ▼            ▼            ▼
             Texture       Rigging     3D Print
                │            │            │
                │            ▼            │
                │        Animation        │
                └────────────┼────────────┘
                             │
                             ▼
                         3D Model
                             │
                             ▼
                        Web Viewer
                             │
                             ▼
                           Export
```

---

## Project Development Strategy

MxMesh AI will be developed incrementally.

### Phase 1 — Image to 3D

```text
JPG / PNG
    ↓
AI
    ↓
Textured 3D Model
    ↓
GLB
```

This is the **current development phase**.

---

### Phase 2 — Interactive 3D Viewer

Display generated GLB models directly inside a web browser.

Users will eventually be able to:

- Rotate models
- Zoom
- Pan
- Inspect geometry
- Preview materials

---

### Phase 3 — Web Upload Interface

Create the first MxMesh AI user interface.

```text
Upload Image
     ↓
Generate 3D
     ↓
Preview
     ↓
Download
```

---

### Phase 4 — Backend API

Create the MxMesh AI backend responsible for generation requests and task management.

Possible future endpoints:

```text
POST /api/v1/image-to-3d
POST /api/v1/text-to-3d
GET  /api/v1/tasks/{task_id}
```

---

### Phase 5 — Text to 3D

Allow users to describe an object using natural language and generate a 3D model.

---

### Phase 6 — Multi-Image to 3D

Allow multiple reference images to improve 3D reconstruction.

---

### Phase 7 — AI Texturing

Add AI-generated textures and materials.

---

### Phase 8 — Additional Export Formats

Progressively support:

```text
GLB
OBJ
FBX
STL
USDZ
BLEND
3MF
```

---

### Phase 9 — 3D Printing Tools

Prepare generated models for physical 3D printing.

---

### Phase 10 — Automatic Rigging

Automatically create skeletons for supported characters.

---

### Phase 11 — Animation

Apply animations to rigged models.

---

### Phase 12 — User Accounts and Projects

Possible future functionality:

- User registration
- Login
- Personal dashboard
- Saved generations
- Project history
- Model management

---

### Phase 13 — Public MxMesh AI Platform

The long-term objective is to combine the individual systems into a complete web application.

```text
                  MxMesh AI

Image ───────┐
             │
Text ────────┼──► AI 3D Generation
             │
Images ──────┘
                    │
                    ▼
                 3D Model
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
     Texture       Rig       Optimize
                    │
                    ▼
                Animation
                    │
                    ▼
                 3D Viewer
                    │
                    ▼
                  Export
```

---

## Development Principles

MxMesh AI will follow several important principles.

### Build One Feature at a Time

Each major component will be developed and tested separately before being integrated into the full platform.

### Keep the Project Documented

Important experiments, architecture decisions, problems, solutions, and results will be documented in GitHub.

### Use Open Technologies Where Appropriate

During the research and prototyping stages, MxMesh AI will investigate suitable open-source AI models and 3D technologies.

### Understand the Technology

The objective is not simply to call an external 3D-generation API.

The long-term goal is to understand and build the complete application architecture around:

- Generative AI
- Computer vision
- 3D reconstruction
- GPU inference
- 3D geometry
- Web development
- APIs
- 3D visualization
- Model processing

---

## Current Project Status

| Component | Status |
|---|---|
| GitHub Repository | Completed |
| Repository Documentation | In Progress |
| Google Colab Environment | Created |
| T4 GPU Configuration | Selected |
| GPU Verification | Next Step |
| Image → 3D | In Development |
| GLB Generation | Planned |
| Browser 3D Viewer | Planned |
| Website | Planned |
| Backend API | Planned |
| Text → 3D | Planned |
| Multi-Image → 3D | Planned |
| AI Texturing | Planned |
| Rigging | Planned |
| Animation | Planned |
| 3D Printing | Planned |

---

## Current Milestone

The immediate objective is:

```text
ONE JPG / PNG IMAGE
          │
          ▼
    IMAGE-TO-3D AI
          │
          ▼
   TEXTURED 3D MODEL
          │
          ▼
         GLB
```

Once this milestone works successfully, development will move to the interactive browser-based 3D viewer.

---
## Author

**Peyman Miyandashti**  
Information Technology and Digital Innovation Engineering  
Universidad Politécnica de Baja California (UPBC)

- GitHub: [Peyman-mxli](https://github.com/Peyman-mxli)
- LinkedIn: [Peyman Miyandashti](https://www.linkedin.com/in/peyman-mxli/)
