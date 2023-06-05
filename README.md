## Project Name

Recommender System for Book Ratings

## Project Description

This project aims to build a recommender system for book ratings. The system utilizes collaboration filtering methods and ensemble techniques to provide accurate recommendations to users based on their preferences. The project includes data exploration, preprocessing, model selection, model construction, and evaluation phases.

The recommender system employs three standalone models, implementing collaboration filtering methods. The models are fine-tuned and compared using cross-validation to select the best-performing model. The chosen model is then further optimized using random search cross-validation. The top-performing models, including SVD, SVDpp, and KNNwithZscore, are used to construct an ensemble model for testing.

## Key Features

- Data exploration to understand trends and patterns in book ratings.
- Data preprocessing to remove outliers and reduce dataset size for improved training speed.
- Model selection using cross-validation to identify the best-performing model.
- Fine-tuning of selected models using random search cross-validation.
- Construction of an ensemble model combining the top-performing models.
- Evaluation of model performance using MAE and RMSE metrics.
- Future enhancements involving more aggressive preprocessing, hybrid approaches, and scalability using frameworks like Spark.



## Usage

The recommender system can be used to provide book recommendations based on user preferences. Users can input their user ID or book name to receive personalized recommendations. The system utilizes collaborative filtering techniques and an ensemble model to generate accurate recommendations.

To obtain recommendations for a specific user:

```python
import recommender_system

user_id = "12345"  # User ID for whom recommendations are required
recommendations(df = test_data,user_id = int(user_id))

```

To obtain a potenical reader of a book:

```python
import recommender_system

book_name = "Angels & Demons (Robert Langdon, #1)"  # Name of the book for which recommendations are required
recommendations(df = test_data,book_name = book_name)


id user_id	rating
33038	1783	4
26076	1483	4
193	6	3
26074	1541	3
930	65	3
```

For sample output ,we look at the reading history of top user 1783

```python
train[train['user_id'] == 1483]
```

| user_id | item_id | rating | book_name |                                                   |
| ------: | ------: | -----: | --------: | ------------------------------------------------- |
|  135608 |    1483 |    399 |         4 | The Da Vinci Code (Robert Langdon, #2)            |
|  135673 |    1483 |    456 |         4 | Memoirs of a Geisha                               |
|  135757 |    1483 |   1074 |         5 | 1984                                              |
|  135885 |    1483 |   1113 |         4 | Harry Potter and the Order of the Phoenix (Har... |
|  136250 |    1483 |   1302 |         5 | The Devil in the White City                       |

Since this user readed the Da Vinci Code, they might also interesting in its prequel. So the recommendation logically make sence



