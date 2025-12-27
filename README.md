# Analysis of Google Play Store app ratings
This projects delves into what influences the rating that a user gives an app on the Google Play Store, including variables such as price, storage size, update frequency, etc., utilising data visualisations and statistical testing.

## Key insights (Summary)
> For full results, visualisations, and detailed discussion, open the Jupyter notebook google.ipynb in this repository.
- Cleaned messy columns, and dropped unnecessary and created useful columns, using ```pandas```.
- Visualised correlation between control variables (`Price ($)`/`Price Type`, `Size (bites)`, `Category`, `Content Rating`) and outcome variable (`Rating`) via scatterplots and boxplots generated using ```matplotlib``` and ```seaborn```.
- Statistically tested for significant correlation (Spearman Rank test) between each control variable and `exam_score` using `statsmodels` and `scipy.stats`.

## Tools and Libraries
| Purpose | Libraries Used |
|----------|----------------|
| Data manipulation | `pandas`, `numpy` |
| Statistical testing | `scipy.stats`, `statsmodels`|
| Data visualization | `matplotlib`, `seaborn` |
| Environment | Jupyter Notebook (`%matplotlib inline`) |

## Installation
1. **Clone this repository**
   ```bash
   git clone https://github.com/lloydy-92/Google-Play-Store-App-ratings.git
   cd Google-Play-Store-App-ratings
2. **(Optional) Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate       # On Windows use: venv\Scripts\activate
3. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels scipy jupyter
4. **Launch the notebook**
   ```bash
   jupyter notebook google.ipynb

## Project Structure
```bash
Google-Play-Store-App-ratings/
├── google.ipynb        # Main analysis notebook
├── googleplaystore.csv # Dataset of Google Play Store apps
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

## Contributing
Contributions, suggestions, and improvements are welcome and encouraged! If you would like the enhance any aspect of the project, such as analysis or visualisations:
1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/improve-analysis
3. Commit your changes
   ```bash
   git commit -m 'Add new visualisation'
4. Push to the branch
   ```bash
   git push origin feature/improve-analysis
5. Open a Pull Request

## Acknowledgements
- Codecademy Data Science Path for providing structured guidance on this project.
- The open-source community for libraries like ```pandas```, ```matplotlib```, and ```scipy```.
---------------------------------------------------------------------------------------------------
“*Turns out app ratings aren’t random — a bit of data and stats go a long way.*”
