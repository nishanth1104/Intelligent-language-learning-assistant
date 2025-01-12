# Intelligent Language Learning Assistant

## Overview
The Intelligent Language Learning Assistant is a web-based application that leverages state-of-the-art natural language processing (NLP) models to help users improve their language skills. This assistant is built using Flask and integrates Hugging Face’s T5 model for grammar correction, with plans to add vocabulary enhancement and interactive learning features.

---

## Features
- **Grammar Correction**: Automatically corrects grammatical errors in user-input sentences using a pre-trained T5 model.
- **User-Friendly Interface**: A simple web interface for users to input text and view corrections.
- **Extensibility**: Designed to accommodate additional features like vocabulary suggestions and learning exercises.

---

## Technology Stack
1. **Backend**: Flask (Python)
2. **Frontend**: HTML, CSS (basic, integrated with Flask templates)
3. **NLP Model**: Hugging Face’s T5 (for grammar correction)
4. **Dependencies**:
   - Flask
   - Transformers (Hugging Face)
   - PyTorch
   - SentencePiece

---

## Project Structure
```
language-learning-assistant/
├── app/
│   ├── templates/
│   │   └── index.html         # HTML file for the web interface
│   ├── static/                # Folder for static files
│   │   ├── css/               # CSS files for styling
│   │   ├── js/                # JavaScript files
│   │   └── images/            # Images used in the application
│   └── __init__.py            # Flask app initialization (optional for larger projects)
├── main.py                    # Main Flask application
├── requirements.txt           # List of dependencies
├── README.md                  # Project documentation
└── .gitignore                 # Ignored files for Git
```

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/language-learning-assistant.git
cd language-learning-assistant
```

### 2. Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Flask App
```bash
python main.py
```
- Open your browser and go to: [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

---

## Usage
1. Launch the app by running `main.py`.
2. Enter a grammatically incorrect sentence in the text box.
3. Click **Submit**.
4. View the corrected sentence in the results section.

---

## Key Functions

### Grammar Correction (`correct_grammar`)
Located in `main.py`, this function uses the Hugging Face T5 model to process and correct user input:
```python
def correct_grammar(text):
    """Correct grammar using T5 model."""
    input_text = f"correct: {text}"
    input_ids = tokenizer.encode(input_text, return_tensors="pt", max_length=512, truncation=True)
    outputs = model.generate(input_ids, max_length=512, num_beams=4, early_stopping=True)
    corrected_text = tokenizer.decode(outputs[0], skip_special_tokens=True)
    return corrected_text
```

---

## Known Issues
- **Performance**: Loading the T5 model may take time, especially on systems without a GPU.
- **Sentence Complexity**: The `t5-small` model may not handle highly complex sentences effectively. Consider upgrading to `t5-base` or `t5-large` for better accuracy.

---

## Future Improvements
1. **Vocabulary Enhancement**:
   - Provide word suggestions and synonyms for better language learning.
2. **Interactive Exercises**:
   - Add quizzes and exercises for language practice.
3. **API Integration**:
   - Convert the app into a RESTful API for broader usage.

---

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m 'Add new feature'`.
4. Push to the branch: `git push origin feature-name`.
5. Submit a pull request.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Acknowledgments
- Hugging Face for their NLP models.
- Flask for providing an easy-to-use web framework.

---

## Contact
For questions or feedback, feel free to reach out:
- **Email**: Nishanth4011@gmail.com
- **GitHub**: [Nishanth1104](https://github.com/nishanth1104)

