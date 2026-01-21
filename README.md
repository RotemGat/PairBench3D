# PairBench3D
Text-Guided Object–Object Interaction Benchmark

This repository provides a benchmark of **50 object–object pairs** for evaluating **3D object alignment and relational understanding** methods.

Each benchmark instance consists of two 3D meshes together with a natural-language prompt describing their intended semantic relationship (e.g., *"Captain America holding a shield"*). The benchmark is designed to support research in zero-shot object alignment, semantic placement, and physically plausible object–object interactions.

## Example: Object–Object Alignment

<p align="center">
  <img src="assets/pinocchio_hat_example.png" width="700">
</p>

<p align="center">
  <em>Example benchmark instance: Pinocchio and hat meshes with the prompt “Pinocchio wearing a hat”.</em>
</p>

## Dataset Structure

All benchmark data is located under the `data/` directory.

Each of the 50 subdirectories corresponds to a single object–object pair:

data/
- pair_001/
- pair_002/
- ...
- pair_050/

Inside each pair directory, the structure is as follows:

data/pair_xxx/
- object_1/
- object_2/
- ATTRIBUTION.txt
- original_files (optional)

## Object Directories

Each object directory contains:
- A single `.obj` mesh file
- A corresponding `.mtl` material file
- One or more texture image files

All objects are converted to a consistent OBJ-based representation to ensure compatibility across different alignment pipelines.

## Original Files

If the original asset was not provided as an OBJ file (e.g., GLB), the original files are included in the directory for reference.

## Attribution File

Each pair directory includes an `ATTRIBUTION.txt` file that documents asset provenance, licensing, and alignment intent.

Example:

Avengers - Endgame  
Veysel Gök  
https://sketchfab.com/3d-models/avengers-endgame-df0ab2d8550b430e96819e1d3967bdcf  
CC Attribution https://creativecommons.org/licenses/by/4.0/  
Split into parts  
"Captain America holding a shield"

The fields correspond to:
1. Original asset name  
2. Creator (Sketchfab user)  
3. Source URL  
4. License type and license URL  
5. Description of modifications applied to the original mesh  
6. Text prompt describing the desired object–object alignment

### Pairs from Two Separate Assets

If a pair is constructed from two independent Sketchfab objects (rather than splitting a single mesh), the attribution file contains a separate attribution block for each object. The final line of the file is a single text prompt describing the desired alignment between the two objects.

## Example Pairs

The benchmark covers a wide range of object categories and relations, including:
- Ice cream inside a cone
- Candle inside a candle holder
- Crown worn on a head
- Knife cutting an apple
- Hat worn on a head

All assets are used in accordance with their original licenses, and full attribution is preserved for every object.
