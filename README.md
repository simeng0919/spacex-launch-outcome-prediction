# SpaceX Falcon 9 Landing Prediction — IBM Data Science Capstone

An end-to-end data science project exploring and predicting successful first-stage landings for SpaceX Falcon 9 launches. Developed for the **IBM Applied Data Science Capstone**.

## Research question

Can historical launch and vehicle characteristics help predict whether a Falcon 9 first stage lands successfully?

## Workflow

1. **Data collection:** SpaceX API and Wikipedia web scraping.
2. **Data preparation:** clean launch data and construct binary landing outcomes.
3. **EDA:** pandas, Matplotlib/Seaborn and SQL analysis.
4. **Geospatial exploration:** Folium launch-site maps and proximity analysis.
5. **Interactive analytics:** Plotly Dash launch-site selector, success pie chart, payload slider and scatter plot.
6. **Predictive modelling:** Logistic Regression, SVM, Decision Tree and KNN using GridSearchCV.

## Project structure

```text
IBM-SpaceX-Capstone/
├── notebooks/
│   ├── jupyter-labs-spacex-data-collection-api.ipynb
│   ├── jupyter-labs-webscraping.ipynb
│   ├── labs-jupyter-spacex-Data wrangling.ipynb
│   ├── edadataviz.ipynb
│   ├── jupyter-labs-eda-sql-coursera_sqllite.ipynb
│   ├── lab_jupyter_launch_site_location.ipynb
│   └── SpaceX_ML_executed.ipynb
├── dashboard/
│   ├── spacex-dash-app.py
│   └── spacex_launch_dash.csv
├── data/
│   ├── dataset_part_2.csv
│   └── dataset_part_3.csv
├── presentation/
│   └── Data Science Capstone Project Report.pdf
└── README.md
```

## Results

Previously executed course-style ML workflow reported:

| Model | Best 10-fold CV accuracy | Test accuracy |
|---|---:|---:|
| Logistic Regression | 84.64% | 83.33% |
| SVM | 84.82% | 83.33% |
| Decision Tree | **87.68%** | **88.89%** |
| KNN | 84.82% | 83.33% |

**Important limitations:** The test set contains only 18 records. The course-style preprocessing fits the scaler before splitting, introducing data leakage; these metrics should not be interpreted as leakage-free generalisation estimates. Reproducibility also depends on package versions and model randomness.

## Run locally

Install common dependencies (package requirements vary by notebook):

```bash
pip install pandas numpy matplotlib seaborn scikit-learn plotly dash folium beautifulsoup4 requests jupyter ipython-sql sqlalchemy
```

Run notebooks with JupyterLab. The API notebook may require the Skills Network/Pyodide environment because it imports `js.fetch`; the SQL notebook uses SQL magic and may require a compatible environment.

To run the Dash app, open a terminal in `dashboard/` and run:

```bash
python spacex-dash-app.py
```

Then open the local address printed by the application (commonly port 8050). Verify the callbacks and capture genuine screenshots for the final presentation.

## Evidence and submission

The presentation PDF is a **draft**: replace `ADD LINK` placeholders with direct GitHub links, insert executed SQL outputs, Folium map screenshots, Dash screenshots and a verified confusion matrix before submitting. The charts included in the draft are calculated from the supplied `dataset_part_2.csv`; ML figures reflect the previously executed notebook.

## Data and attribution

Course datasets and starter notebooks are provided as part of IBM / Skills Network's Applied Data Science Capstone. Public SpaceX launch data and Wikipedia historical launch information are used in the coursework. Respect the licences and attribution requirements of the original materials.
