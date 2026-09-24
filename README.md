<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=Hi%2C%20I'm%20Ankush&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Data%20science%20and%20machine%20learning%20in%20Python&descAlignY=58&descSize=18" width="100%" alt="Header banner" />

<a href="https://github.com/Ankush-Manhas840/crop-yield-prediction">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1200&color=58A6FF&center=true&vCenter=true&width=700&lines=Predicting+crop+yield+from+Indian+agricultural+data;Python+%7C+pandas+%7C+scikit-learn+%7C+Streamlit;Cleaning+messy+real-world+data;Measuring+error+before+trusting+a+model" alt="Typing animation" />
</a>

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

[![Live demo](https://img.shields.io/badge/Live%20demo-Crop%20Yield%20Predictor-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://crop-yield-prediction-wpnuufdz2fc9tmbm4k8t3y.streamlit.app/)

</div>

---

## About me

```python
class Ankush:
    def __init__(self):
        self.language = "Python"
        self.tools = ["pandas", "scikit-learn", "Streamlit", "Jupyter"]
        self.featured_project = "Crop Yield Predictor"
        self.approach = "build a weak baseline first, measure error per group, fix what the breakdown shows"
```

---

## Featured project: Crop Yield Predictor

[**Live demo**](https://crop-yield-prediction-wpnuufdz2fc9tmbm4k8t3y.streamlit.app/) | [**Source code**](https://github.com/Ankush-Manhas840/crop-yield-prediction) | [**Cleaning and modelling notebook**](https://github.com/Ankush-Manhas840/crop-yield-prediction/blob/master/notebooks/01_eda.ipynb)

A model that predicts crop yield (tonnes per hectare) for **Rice, Wheat, Maize and Sugarcane** in Indian states, from the state, season, year and planted area. It is built on government district-level production data and wrapped in a Streamlit app.

It is a portfolio project, not a forecasting tool: it interpolates within the range of its training data, and the repo says so plainly. The value is in the data cleaning and the modelling process.

<div align="center">

<img src="https://raw.githubusercontent.com/Ankush-Manhas840/crop-yield-prediction/master/assets/pipeline.svg" width="90%" alt="Pipeline: raw data through cleaning and feature engineering to a trained Random Forest, then the flow from user input to prediction" />

</div>

| | |
|---|---|
| **Data** | 246,091 raw rows from data.gov.in (district-wise, season-wise crop production since 1997), cleaned down to 44,257 |
| **Model** | Random Forest (100 trees) on 45 one-hot encoded features |
| **Result** | 2.04 t/ha mean absolute error on a held-out 20% test split, against 107.63 for a linear-regression baseline |
| **App** | Streamlit; it trains its model on first run and caches it, so nothing large lives in the repo |

> The demo is hosted on Streamlit's free tier, so it may be asleep. If you see a "gone to sleep" page, click **Yes, get this app back up** and give it a minute or two.

### What made it interesting

- **A units trap hidden in the data.** Some crops in the dataset aren't measured in tonnes: coconut is counted in nuts, cotton and jute in bales. Coconut's "production" goes up to 1.25 billion, which is impossible as tonnes. Guessing conversion factors would have been unreliable, so I narrowed the scope to four crops with consistent units.
- **A deliberately weak baseline.** Linear regression scored 107.63 and predicted yields from -319 to 981, which showed that one formula can't fit crops averaging 2 t/ha and 55 t/ha together.
- **Per-group error, not just one score.** Breaking the Random Forest's error down by crop showed 0.55 t/ha on everything except sugarcane and 65.15 on sugarcane. An overall score had been hiding that. Removing 50 physically implausible sugarcane rows brought the final error to 2.04.

### Limitations and next steps

- There is no weather data in the model yet. Rainfall data is already downloaded, and joining it in is the biggest planned improvement.
- It cannot forecast future years, and it only uses state-level location, not district.
- Next: target-encode districts, use cross-validation instead of a single split, and warn in the app when a combination has little support in the training data.

---

## GitHub

<div align="center">

<img src="https://streak-stats.demolab.com?user=Ankush-Manhas840&theme=tokyonight&hide_border=true" alt="Streak stats" />

<br/><br/>

![Followers](https://img.shields.io/github/followers/Ankush-Manhas840?style=for-the-badge&logo=github&color=58A6FF)
![Last commit](https://img.shields.io/github/last-commit/Ankush-Manhas840/crop-yield-prediction?style=for-the-badge&logo=git&logoColor=white&color=58A6FF)

<br/>

<img src="https://ghchart.rshah.org/58a6ff/Ankush-Manhas840" width="100%" alt="Contribution heatmap" />

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=120&section=footer" width="100%" alt="Footer banner" />

</div>
