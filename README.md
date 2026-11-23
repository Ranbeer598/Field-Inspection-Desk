# SIH26095 Field Inspection Desk (CA-1, CSE276, K3P25LH, Group 31)

Prototype for Smart India Hackathon 2026 problem statement SIH26095 (MoSJE): inspection assignment, field reporting and a monitoring dashboard, with risk-based vs random vs round-robin allocation, plus a logistic-regression risk model trained on real, public inspection data.

Group: Ranbeer Singh (12508980, roll 42), Aniket Kumar Singh (12510117, roll 21). Instructor: Piyush Sharma.

## Run the web app (no install)
Open `app/index.html` in any modern browser, or use the hosted copy: https://timely-pixie-0e7b47.netlify.app/
It is one self-contained file; to host it, upload `index.html` to Netlify, GitHub Pages or any static host.

## Reproduce the numbers in the report
```
pip install -r requirements.txt
python src/train_model.py        # downloads the dataset if missing, trains and evaluates -> results/metrics.json
python src/make_figures.py       # EDA figures, confusion matrix, error examples -> results/
node src/run_site_comparison.js  # scheduling comparison using the app's own code (needs: npm i jsdom) -> results/sched.json
```
## Dataset
City of Chicago, food-inspections-evaluation, file `DATA/23_food_insp_features.Rds`, MIT licence:
https://github.com/Chicago/food-inspections-evaluation . Accessed 23-11-2026. Not stored in the ZIP; the script downloads it into `data/`.
The scheduling tests also use 120 synthetic institution records (seed 2026), generated inside the app and labelled synthetic.

## Folders
`app/` web app, `src/` code, `results/` saved metrics and figures, `notebooks/` EDA notebook, `report/` final PDF, `presentation/` slides.
