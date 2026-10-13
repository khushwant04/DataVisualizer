# DataVisualizer

A small Streamlit app for quick exploratory plots: pick a CSV from the `data/` folder, choose the
X / Y columns and a plot type, and render it with seaborn.

## Features

- Lists every `.csv` file in `data/` (the Pima Indians diabetes dataset is bundled as an example)
  and previews the first rows.
- Plot types: line plot, bar chart, scatter plot, distribution plot (histogram + KDE), and a
  "count plot" (currently rendered with `sns.histplot`).

## Project structure

```
main.py            # Streamlit app
data/diabetes.csv  # sample dataset
requirements.txt   # pinned streamlit / pandas / matplotlib / seaborn versions
```

## Getting started

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
streamlit run main.py
```

Open the URL Streamlit prints (default `http://localhost:8501`). To visualise your own data, drop a
CSV file into `data/` and reload the page.

## Known limitations

- Only reads files placed in `data/`; there is no upload widget.
- Choosing the `None` option for an axis is not handled and raises a `KeyError`; line, bar and
  scatter plots need both axes selected.
