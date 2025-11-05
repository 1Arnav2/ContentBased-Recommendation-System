> ```markdown
> # Content-Based Movie Recommendation System
> ```

> This project is a content-based recommendation system built in Python. It recommends movies to a user based on the content and attributes of a movie they like (such as plot, cast, crew, and keywords).

> 
>
> -----

> Collaboration & Credit

> This was a group project. I collaborated on this project with:

> Pragya Kajla (https://github.com/PragyaKajla)
> Nityam Shitap (https://github.com/AZRAEL1727)

> 
>
> -----

> How It Works

> The recommendation logic is built on the concept of content similarity. If a user likes a particular movie, the system will recommend other movies that have the most similar "content."

> The model follows these steps:

> 1.  Data Loading: Loads the "TMDB 5000 Movies" and "TMDB 5000 Credits" datasets.
> 2.  Data Preprocessing: The datasets are merged. Key features are extracted from JSON columns (like `genres`, `keywords`, `cast`, and `crew`).
> 3.  Feature Engineering: A "tags" column is created for each movie. This is a large string that combines:
>       * The movie's `overview` (plot summary)
>       * Its `genres` (e.g., Action, Sci-Fi)
>       * Its `keywords` (e.g., alien, space war)
>       * The top 3 actors from the `cast`
>       * The `director`'s name
> 4.  Text Normalization: All tags are converted to lowercase, and stemming is applied (e.g., "action" and "actions" are treated as the same word "action") using NLTK.
> 5.  Vectorization: The text "tags" for all movies are converted into a numerical vector space using the Bag-of-Words model (`CountVectorizer`). This creates a matrix where each row is a movie and each column is a word.
> 6.  Similarity Calculation: Cosine Similarity is used to calculate the similarity score between every pair of movies based on their tag vectors.
> 7.  Recommendation: A function takes a movie title, finds its similarity scores with all other movies, and returns the top 5 most similar movies.

> ## 🛠️ Technologies Used

>   * Python
>   * Pandas: For data manipulation and analysis.
>   * Numpy: For numerical operations.
>   * Scikit-learn (sklearn): For `CountVectorizer` and `cosine_similarity`.
>   * NLTK (Natural Language Toolkit): For stemming text.

> How to Run This Project

> 1.  Ensure you have Python and Jupyter Notebook installed.
> 2.  Install the required libraries:
>     ```bash
>     pip install pandas numpy scikit-learn nltk
>     ```
> 3.  Place the datasets (`tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`) in the same folder as the notebook.
> 4.  Run the `Reccomend2.ipynb` notebook.
> 5.  Use the `recommend()` function at the end of the notebook to get recommendations. For example:
>     ```python
>     recommend('The Dark Knight')
>     ```
>
> <!-- end list -->
>
> ```
> ```
