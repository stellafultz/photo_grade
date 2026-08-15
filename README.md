<img src="header2.svg" width="100%" alt="">

# photo_grade

Sorts a set of photos into a perceptually smooth color gradient. Option to automatically color grade outliers to improve gradient flow.

## What it does

1. **Extracts** a representative color from each photo.
2. **Sorts** them by solving the open Traveling Salesman Path in OKLab
   space — nearest-neighbor construction refined with 2-opt — so adjacent
   photos are always the closest perceptual match.
3. **Fits** a smooth trajectory through the sorted sequence. Each photo's
   target color is a Gaussian-weighted average of its neighbors,
   *excluding itself*, so outliers actually register as outliers.
4. **Grades** the photos that deviate past a threshold, scaling lightness
   and shifting chroma in OKLab to pull them onto the curve.

Optionally, pick a reference photo and the whole set adapts to its color
character while keeping its own lightness range.

## Usage & Controls

- Click a photo to set it as the color reference
- Right-click (or long-press) any photo for options — open larger,
  download graded, download unedited, copy hex
- Scroll or drag the carousel

| | |
|---|---|
| **extract** | average vs. dominant color per photo |
| **smoothing** | how many neighbors define each photo's target |
| **sensitivity** | how far a photo must deviate before it's graded |
| **strength** | how far toward its target a photo is pushed |
| **reference pull** | how strongly the set adapts to the reference photo |
