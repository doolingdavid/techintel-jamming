# techintel-jamming

RF jamming / GNSS interference / CRPA-antenna focused example of techintel,
covering the anti-jam / electronic-protection and PNT-resilience literature.

Same pipeline as `techintel-quantum`, re-run from scratch on a keyword OpenAlex
Works corpus (GPS/GNSS jamming & spoofing, controlled reception pattern antennas,
anti-jam / adaptive nulling, navigation warfare, PNT resilience).

run

`> streamlit run jamming2d.py`

## Data pipeline

`jamming.ipynb` builds the runtime data:

OpenAlex keyword Works search → abstract reconstruction → YAKE keywords →
flair sentence embeddings (`all-MiniLM-L6-v2`) → UMAP (2D) → HDBSCAN clusters →
paper/author/affiliation triples → topic centroids → source & affiliation-geo dicts.

Outputs (loaded by `jamming2d.py`):
`jammingcrpacentroids2d.pkl.gz`, `jammingcrpadfinfo2d.pkl.gz`,
`jammingcrpadftriple2d.pkl.gz`, `updatesource_page_dict.pkl`, `updateaffil_geo_dict.pkl`.
