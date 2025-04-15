# LuciaDoval-fcc_book_recommendation_knn

This project implements a **book recommendation engine** using the **K-Nearest Neighbors (KNN)** algorithm, based on the **Book-Crossings** dataset, which contains over 1.1 million ratings of books by users.

## 🧠 Objective

To build a function that, given a book title, recommends 5 similar books based on user ratings using the KNN algorithm and cosine distance metric.

## 📁 Dataset

Two CSV files are used:

- `BX-Books.csv`: contains book information.
- `BX-Book-Ratings.csv`: contains user ratings (scale 1–10).

These files are automatically downloaded and extracted in Google Colab using:

```python
!wget https://cdn.freecodecamp.org/project-data/books/book-crossings.zip
!unzip book-crossings.zip
```
🧹 Data Preprocessing
```python
Filter users with fewer than 200 ratings.

Filter books with fewer than 100 ratings.

Merge book titles with ratings.

Create a book-user matrix (pivot_table).

Convert to a sparse matrix for efficiency.

Train the KNN model using cosine distance.
```

🧮 Model
The model uses NearestNeighbors from sklearn.neighbors:

```python
model = NearestNeighbors(metric='cosine', algorithm='brute')
model.fit(book_user_sparse)
```
🚀 Main Function
```python
def get_recommends(book=""):
    """
    Returns a list of 5 books similar to the given title, along with their distances.
    """
Example Usage:
python
Copy
Edit
get_recommends("The Queen of the Damned (Vampire Chronicles (Paperback))")
```
Expected output:

```python
[
  'The Queen of the Damned (Vampire Chronicles (Paperback))',
  [
    ['Catch 22', 0.7939],
    ['The Witching Hour (Lives of the Mayfair Witches)', 0.7448],
    ['Interview with the Vampire', 0.7345],
    ['The Tale of the Body Thief (Vampire Chronicles (Paperback))', 0.5376],
    ['The Vampire Lestat (Vampire Chronicles, Book II)', 0.5178]
  ]
]
```
✅ Testing
The project includes a testing function that checks if the recommendations returned for a specific book are correct and sorted by similarity:

```python
test_book_recommendation()
🛠 Libraries Used
numpy

pandas

scikit-learn

scipy

matplotlib (optional, for visualization)
```
🧠 Skills Applied
- Real-world data cleaning and filtering

- Recommender systems

- Sparse matrix optimization

- KNN for high-dimensional data

📎 Credits
This is an educational project based on the FreeCodeCamp Machine Learning Certification challenge.
