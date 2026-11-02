# Machine Learning-Driven Analysis of AFM Force–Distance Curves for Cell Membrane Integrity Assessment

This **interactive webR-based application** lets you run `R` code directly in your browser to perform pre-defined statistical operations and specialized F-D curve analysis. Because everything runs entirely client-side, no server or local `R` installation is required.

> Table of Contents

* [Features](#features)
* [Quickstart Example](#quickstart-example)
* [Technical Notes](#technical-notes)
* [Citation & License](#citation--license)

## Features

* **ZIP File Batch Processing:** Upload a single `.zip` archive containing folders of `.spm` curve files.
* **In-Memory webR Execution:** Load all `.spm` files directly into `R` memory client-side. *(Processing time scales with the number of files).*
* **Customizable Parameters:** Tune default analysis parameters to match your specific force-distance curve profiles.
* **Multi-Classifier Evaluation:** Compare curve classifications across three built-in models and visualize prediction distributions across methods.
* **Automated Curve Metrics:** Compute key metrics — including force, bilayer thickness, and peak counts — based on selected classification model and Contact Point (CP) detection method.
* **Interactive Visual Fine-Tuning:** Plot individual curves to inspect detected Contact Points (from all three methods), rupture maxima and minima. Adjust the CP position manually if visual assessment warrants it.
* **Flexible Data Export:** Download classification results and calculated metrics as semicolon-separated CSV files (`.csv`). Export rendered plots directly as PNGs or download raw plot data in CSV format for external visualization and post-processing.

## Quickstart Example

Below are detailed instructions for analyzing the example data file `PS270113.zip`. The file contains 27 `.spm` files. Before you proceed, please download the `.zip` file to your desired folder.

1. *Upload and extract the ZIP*: Select the ZIP file containing your data and click **Upload and extract**. A green checkmark should appear, and all folders within the ZIP file should be listed under *First-level folders:*.
2. *Upload files into `R`*: Click **Upload into R**. The application will show how many curves (i.e., `.spm` files) have already been processed. Once all 27 curves are successfully uploaded into `R` memory, a green checkmark will be displayed.
3. *Configure parameters*: You can adjust the default parameter values to match your data. For `PS270113.zip`, set *Distance-based interpolation threshold* to 2, as some F-D curves contain "small" rupture events where a higher value might skip the rupture minimum and maximum.
4. *Calculate summary statistics*: Click **Summarize the data** to compute basic summary statistics for the curves based on your chosen parameters.
5. *Classification*: Click **Classify** to run three classification methods for predicting the number of rupture events. You will see the level of agreement between the classifiers (in the case of `PS270113.zip`, there is 100% agreement).
6. *Plot the prediction distribution*: You can generate a bar plot showing the prediction distribution per method. Each first-level folder is displayed in its own subfigure. You can download the plot as a PNG or CSV file, and export the classification results as a CSV file.
7. *Calculate curve metrics*: Based on the results above and your preferences, select the classification model you want to use for metric calculation (for `PS270113.zip`, any choice yields the same results) and select a method for CP detection (e.g., select the second option for `PS270113.zip`). Then click **Compute metrics**; a green checkmark will be displayed. You can download the classification results along with the computed metrics by clicking the green button.
8. *Fine-tuning*: First, select a curve to inspect (you must initially select a curve other than the first one). Clicking **Plot the selected curve** generates the graph (which you can download using the corresponding button). Clicking **Done! Do you want to plot the next curve?** displays the next curve. In `PS270113.zip`, curve `cr00017.0_00000.spm` is noisier than the rest, requiring a correction to its CP index. Enter `440` into the *New contact point index:* input field and press **overwrite**. The graph will regenerate and the metrics will recompute. The remaining curves look correct, so no further CP index adjustments are needed.
9. *Data export*: Finally, download the classification results containing the corrected metrics in CSV format.

> Other example data

For testing, you can use the example ZIP file included in this repository:

* `Data_example.zip` 

Upload a ZIP file containing curve files in the `.spm` format or your own data.

## Technical Notes

* The application uses **webR** and `R` packages `ggplot2`, `tidyr`, `dplyr`, `afmToolkit`, and `changepoint`.
* All computations are performed in your browser; no server required.

### How to Run

The app is hosted via GitHub Pages, visit:

```
https://gamu-milan.github.io/webR-app/
```

## Citation & License

If you use this tool, please cite the associated paper:

> To be updated upon publication.

The archived version of this specific repository can be found on Zenodo:

> To be updated later.

### License

This project is licensed under the **MIT License**. See the LICENSE file for details.


