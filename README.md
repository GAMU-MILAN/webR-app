# MILAN: Interactive webR App for Data Analysis

This is an **interactive HTML + webR application** that lets you run `R` code directly in your browser. Everything runs client-side — no `R` installation or server required.

## Features

* **Upload ZIP files** containing folders with curve files in *spm* format.
* **Explore files** inside extracted folders.
* **Classify your curves** with the selected classifier.
* **Plot your data** and classification results using `ggplot2` library.
* **Download results**: prediction and metrics as CSV and plots as PNG.

## Example Data

For testing, you can use the example ZIP files included in this repository:

* `Data_example.zip` (recommended)
* `Data_small.zip`
* `Data_small_3.zip`

Upload a ZIP file containing curve files in the *spm* format or your own data.

## How to Run

The app is hosted via GitHub Pages, visit:

```
https://github.com/GAMU-MILAN/webR-app/
```

## Notes

* Uses **webR** with `ggplot2` and `dplyr`.
* All computations are performed in your browser; no server required.

