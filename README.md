# Predicting Chinese Tallow Tree Spread with Machine Learning

## Overview
Invasive species negatively impact native habitats, biodiversity, and human activity. Across Texas alone, invasive species cause more than **$1 billion in damages each year**.

The **Chinese Tallow tree**, originally from China, is an invasive species found throughout the Southern United States. It disrupts local ecosystems by crowding out native plants and reducing biodiversity.

Preventing its spread requires identifying areas where it is most likely to grow, allowing for efficient allocation of removal resources. Early detection is especially important, as Chinese Tallow trees are easiest to remove during the seedling stage.

---

## Approach
One effective way to predict future spread is through **machine learning**, which uses data and algorithms to extract insights and make predictions.

Using historical sighting data of Chinese Tallow trees in Texas, this project builds a predictive model to estimate where the species is likely to spread next.

---

## Data Collection & Preparation
- Sourced data from the **Global Biodiversity Information Facility (GBIF)** via their free API  
- Dataset included **9,500+ sightings**, reduced to **6,000 coordinates** for modeling  
- Performed **data cleaning** to remove invalid or incomplete entries  
- Used a **Texas county map from the U.S. Census Bureau** for geographic visualization  

### Feature Engineering
Constructed a dataset at the county level including:
- Presence of sightings (binary: 0 or 1)
- Number of sightings per county
- Geographic location of each county

---

## Model Development
Two models were trained using Python:

### 1. Logistic Regression
- Simpler, more interpretable model  
- Predicts probability of a sighting occurring in a county  

### 2. Random Forest
- More complex, ensemble-based model  
- Typically offers higher accuracy by combining multiple decision trees  

---

## Evaluation Metrics
Models were evaluated using:
- **Accuracy**
- **AUC-ROC (Area Under the Receiver Operating Characteristic Curve)**  
  - 0.5 = random prediction  
  - 1.0 = perfect classification  

---

## Results
| Model               | Accuracy   | AUC-ROC |
|--------------------|------------|--------|
| Logistic Regression| 84.375%    | 0.898  |
| Random Forest      | 82.813%    | 0.918  |

Both models performed well, with strong AUC-ROC scores indicating effective separation between invaded and uninvaded counties.

---

## Visualization
- Generated a **heatmap of Texas counties** showing predicted invasion risk  
- Risk values ranged from **0 (low risk) to 1 (high risk)**  
- Overlaid **actual sighting coordinates** for comparison  

---

## Limitations
- Relies only on historical sightings and geographic location  
- Does not include additional factors such as:
  - Weather patterns  
  - Population density  
  - Satellite or environmental data  
- Observation-based data may miss unreported or remote occurrences  

---

## Future Improvements
- Incorporate environmental and climate data  
- Use satellite imagery for more comprehensive detection  
- Improve coverage of underreported regions  

---

## Conclusion
This project demonstrates how machine learning can be used to predict the spread of invasive species like the Chinese Tallow tree. By identifying high-risk areas, it can help guide resource allocation for removal and prevention efforts.

---

## Citations
- Texas State Invasive Species Institute. “Invasives 101.” https://tsusinvasives.org/home/invasives-101/  
- Wang, Hsiao-Hsuan, et al. “Integrating Spread Dynamics and Economics of Timber Production to Manage Chinese Tallow Invasions in Southern U.S.” U.S. Department of Agriculture, 2012. https://research.fs.usda.gov/treesearch/40584  
- GBIF Secretariat. *Triadica sebifera (L.) Small.* GBIF Backbone Taxonomy, 2023. https://www.gbif.org/species/3054399  

---

## Notes
- Code executed using **Python**, hosted on **GitHub** and **Google Colab**  
- Coordinate data sourced from **GBIF API**  
- Texas county map obtained from the **U.S. Census Bureau**  
- Slideshow template courtesy of Slides Carnival  
- Citations formatted using a citation generator
- Slideshow: https://docs.google.com/presentation/d/1cdG8d8Hhx46qlJYj8zwIOCxgC7DU-5jsppmbETgEVmo/edit?slide=id.g3cbcff7c4bb_0_54#slide=id.g3cbcff7c4bb_0_54
