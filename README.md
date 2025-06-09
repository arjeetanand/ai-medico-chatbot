# AI Medico Chatbot

AI Medico Chatbot is a web-based application that leverages machine learning and natural language processing to assist users with medical queries, symptom analysis, and dietary recommendations. The chatbot can predict diseases based on user input, suggest relevant diets, and manage user authentication.

## Features

- **Disease Prediction:** Predicts possible diseases based on user-described symptoms using trained ML models.
- **Diet Recommendations:** Suggests diets for various diseases from a curated dataset.
- **User Authentication:** Signup and login functionality with SQLite database.
- **Interactive Chatbot:** Engages users in conversation to collect symptoms and provide medical advice.
- **Data Visualization:** (If implemented in notebooks) Visualizes data and model performance.

## Project Structure

```
├── app.py                  # Main Flask application
├── my_nltk_script.py       # NLTK-based text processing script
├── notebook.py             # Additional Python logic (possibly for Jupyter)
├── Notebook.ipynb          # Jupyter notebook for experiments/visualization
├── combined_data.csv       # Combined dataset (if used)
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
├── sample.py               # Sample/test script
├── signup.db               # SQLite database for user info
├── Dataset/
│   ├── dataset.csv         # Main dataset for training/prediction
│   └── disease_drugs.csv   # Disease-drug mapping
├── diets/
│   ├── aids.txt
│   ├── diabetes.txt
│   └── ...                 # Diet plans for various diseases
├── static/                 # Static files (CSS, JS, images)
├── templates/              # HTML templates for Flask
└── __pycache__/            # Python cache files
```

## Installation

1. **Clone the repository:**
   ```sh
   git clone <repository-url>
   cd ai-medico-chatbot-main
   ```

2. **Create a virtual environment (optional but recommended):**
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

4. **Download NLTK data (if not already downloaded):**
   The app will attempt to download required NLTK data (`stopwords`, `wordnet`) on first run, but you can also do:
   ```sh
   python -m nltk.downloader stopwords wordnet
   ```

5. **Set up the database:**
   The app uses `signup.db` for user authentication. If not present, create the database and table:
   ```sql
   -- Using SQLite CLI or a tool like DB Browser for SQLite
   CREATE TABLE info (
     user TEXT,
     email TEXT,
     password TEXT,
     mobile TEXT,
     name TEXT
   );
   ```

## Usage

1. **Run the Flask app:**
   ```sh
   python app.py
   ```

2. **Open your browser and navigate to:**
   ```
   http://127.0.0.1:5000/
   ```

3. **Interact with the chatbot:**
   - Sign up or log in.
   - Enter your symptoms.
   - Receive disease predictions and dietary recommendations.

## Key Files

- [`app.py`](app.py): Main Flask application. Handles routing, user authentication, disease prediction, and diet recommendation.
- [`Dataset/dataset.csv`](Dataset/dataset.csv): Dataset used for training and prediction.
- [`diets/`](diets/): Contains text files with diet recommendations for each disease.
- [`templates/`](templates/): HTML templates for rendering web pages.
- [`signup.db`](signup.db): SQLite database for storing user information.

## Customization

- **Adding New Diets:** Add a new `.txt` file in the `diets/` folder named after the disease (e.g., `hypertension.txt`) with the recommended diet.
- **Updating the Dataset:** Replace or update `Dataset/dataset.csv` with new data as needed.
- **Improving Models:** Retrain or replace the ML models as required for better accuracy.

## Dependencies

- Flask
- pandas
- numpy
- scikit-learn
- tensorflow / keras
- nltk
- sqlite3

See [`requirements.txt`](requirements.txt) for the full list.

## Security Note

- Passwords are stored in plaintext in the database. For production, use password hashing and secure authentication practices.

## License

[MIT License](LICENSE) (or specify your license here)

## Acknowledgements

- Disease and diet datasets sourced from public medical datasets.
- Built using open-source libraries: Flask, scikit-learn, TensorFlow, NLTK, etc.

---

For questions or contributions, please open an issue or submit a pull request.