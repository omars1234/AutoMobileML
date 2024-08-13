 
# *Auto Mobile price MachineLearning notebooks Using Python Language*

## *Author  [Omar Soub](https://github.com/omars1234)*

## *Overview*


*In this Project ,we will use Python Language and find the best Machine Learning Models with hypert parameter tuning for regression problem*

* *To predict the Auto Mobile Prices based on given features inputs Using Python*

* *For detailed data analysis , you can see [*AutoMobilePricesAnalysis-http://rpubs.com/omars/1196926*](http://rpubs.com/omars/1196926) where we have aplplied deep Analysis using R-Programming*



## *Table of Contents*

*  *Installation*  
*  *Data*  
*  *Usage*  
*  *Project Structure*  
*  *Models and Parameters used in hypert tuning*  
*  *Results*  

## *Installation*  
*To run this project, you need to have Python installed on your machine. Additionally, install the required libraries by running the following libraries on requirements.txt file:*

```bash
pandas
numpy
seaborn
matplotlib
scikit-learn
xgboost
tqdm
ipykernel
pyjanitor
feature_engine
hyperopt
```
## *Data*  
*The dataset used for this project contains AutoMobile Insurance data. It includes the following columns:*



## *Usage*

*Clone the repository:*


```bash
https://github.com/omars1234/AutoMobileML.git
```

## *Project Structure*

```bash
Automobile_data_Analysis/
├── DataSet/
│   └── automobile_data.csv
|   └── new_cleaned_df.csv   
├── Notebooks/
│   ├── Analysis.ipynb

├── outcomes/
|   ├── bestModels
|   ├── bestParams
|   ├── featuresImportanceGraphs
|   ├── modelsEvaluations
|   ├── modelsEvaluationsGraphs
|
├── README.md
├── requiremnts.txt
```

## *Models and Parameters used in hyper tuning*  

```bash
models = {
                "RandomForestRegressor": RandomForestRegressor(),
                "DecisionTreeRegressor": DecisionTreeRegressor(),
                "XGBRFRegressor": XGBRFRegressor(),
                "GradientBoostingRegressor":GradientBoostingRegressor(),
                "AdaBoostRegressor": AdaBoostRegressor()
}

search_spaces ={        
        "XGBRFRegressor":{
            "learning_rate": hp.uniform("learning_rate",0.01,1.0),   
            "max_depth": hp.choice("max_depth", [2, 4, 5, 6,7,8]),
            "subsample": hp.uniform("subsample",0.5,1.0),
            "n_estimators": hp.choice("n_estimators", [100, 200, 300, 400,500,600]),
            'colsample_bytree': hp.uniform("colsample_bytree",0.5,1.0), 
            'colsample_bynode': hp.uniform("colsample_bynode",0.5,1.0),
            "reg_lambda": hp.quniform("reg_lambda",0,2,1),         
            "reg_alpha": hp.quniform("reg_alpha",0,2,1),
            "num_parallel_tree": hp.choice("num_parallel_tree", [100,110])
            },                    
        "GradientBoostingRegressor":{
            "loss": hp.choice("loss",['squared_error', 'huber', 'absolute_error', 'quantile']),
            "n_estimators": hp.choice("n_estimators", [100, 200, 300, 400,500,600]),
            "max_depth": hp.choice("max_depth", [2, 4, 5, 6,7,8]),
            "max_features": hp.choice("max_features",["sqrt", "log2"]),
            "learning_rate": hp.uniform("learning_rate",0.01,1.0),
            "subsample": hp.uniform("subsample",0.8,1.0),
            "min_samples_split": hp.uniform("min_samples_split",0.8,1.0),
            "min_samples_leaf": hp.uniform("min_samples_leaf",0.8,1.0),
            "criterion": hp.choice("criterion",["squared_error", "friedman_mse"]) 
            },
        "RandomForestRegressor":{
            "n_estimators": hp.choice("n_estimators", [100, 200, 300, 400,500,600]), 
            "min_samples_split": hp.uniform("min_samples_split",0.8,1.0),
            "min_samples_leaf": hp.uniform("min_samples_leaf",0.8,1.0),
            "bootstrap": hp.choice("bootstrap",[True, False]),                                                                                                    
            "max_features": hp.choice("max_features",["sqrt", "log2"]),                                    
            "max_depth": hp.choice("max_depth", [2, 4, 5, 6,7,8]),
            "criterion": hp.choice("criterion",["poisson", "squared_error", "friedman_mse","absolute_error"])                    
            },
        "AdaBoostRegressor":{
            "n_estimators": hp.choice("n_estimators", [100, 200, 300, 400,500,600]),
            "learning_rate": hp.uniform("learning_rate",0.01,1.0),
            "loss": hp.choice("loss",["linear","square","exponential"])
            },
        "DecisionTreeRegressor": {
                    "criterion": hp.choice("criterion",["poisson", "squared_error", "friedman_mse","absolute_error"]),
                    'splitter': hp.choice("splitter",["best", "random"]),
                    "max_depth": hp.choice("max_depth", [2, 4, 5, 6,7,8]),
                    "min_samples_split": hp.uniform("min_samples_split",0.8,1.0),
                    "min_samples_leaf": hp.uniform("min_samples_leaf",0.8,1.0),
                    "max_features": hp.choice("max_features",["sqrt", "log2"])
            }                    
}
```

## *Results*

### *Price feature as Regression Target ML :*

* *The best model was XGBRFRegressor() with the default parameters*


*model Evaluations Graph*             |  *Model Features Importance Graphs*
:-------------------------:|:-------------------------:
 ![Logo](outcomes/modelsEvaluationsGraphs/price_EvaluationsGraph.png)  |   ![Logo](outcomes/featuresImportanceGraphs/price_featureImportanc.png)

 ----------------------------------------

## *Feedback*

*If you have any feedback, please reach out to us at omars.soub@gmail.com*

## 🔗 Links

[*my github page-https://github.com/omars1234*](https://github.com/omars1234)

## *🛠 Skills*
*python, R, SQL ,PowerBi ,Tableaue*
