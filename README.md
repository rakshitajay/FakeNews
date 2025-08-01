# FakeNews
Fake News Generator and Detector Using NLP and GenAI

Fake News Detection & Generation System

This repository contains a complete system for Fake News Detection and Generation leveraging state-of-the-art Natural Language Processing (NLP) and Generative AI (Gen AI) technologies. The system is designed as an interactive Streamlit dashboard that runs seamlessly on Google Colab or locally, incorporating:

Fake News Detection using:

Transformer-based classification (DistilBERT fine-tuned for sentiment as a demo, adapted for fake/real classification on news titles)

Classic NLP approach: TF-IDF vectorization + Logistic Regression trained on news titles from the Kaggle Fake and Real News Dataset

Fake News Generation using:

GPT-2 generative language model for creating realistic fake news text based on user-provided titles (seed prompts)

Features
Easy-to-use web app with multi-page interface:

Detection Page: Enter news titles separately and get instant fake/real prediction with two detection methods

Generation Page: Generate fictional fake news text with customizable GPT-2 parameters

Metrics Page: View performance metrics and confusion matrix of the baseline TF-IDF model

Data Preview: Explore random sample titles and labels from the dataset

Uses real labeled data from the Kaggle Fake and Real News Dataset

Combines modern transformer pipelines with classic feature engineering & ML methods for robust detection

Publicly exposable via ngrok tunnel in Google Colab (requires ngrok authtoken)

Setup & Usage
1. Prerequisites
Python 3.7+

Basic knowledge of running Python scripts or Streamlit apps

Kaggle API token (kaggle.json) for dataset download

Ngrok account and authtoken for public Streamlit access

2. Installation
Run the entire setup cell in Google Colab or your local machine to install dependencies, download dataset, train baseline model, and launch the app.

bash
pip install streamlit transformers scikit-learn pyngrok kaggle torch seaborn matplotlib
3. Kaggle API token
Download your Kaggle API token (kaggle.json) from Kaggle account → API section

Upload to your working directory or Colab environment before running the setup

4. Ngrok authtoken
Sign up or log in at ngrok.com

Obtain your authtoken from here

Replace "YOUR_NGROK_AUTH_TOKEN" in the code with your actual token

5. Running the app
In Colab, execute the main cell that:

Downloads Kaggle dataset

Prepares data and trains TF-IDF baseline on title field

Sets up Hugging Face transformers pipelines (Transformer detection & GPT-2 generation)

Launches the Streamlit app accessible via public url printed by ngrok

Example to run locally:

bash
streamlit run app.py
How It Works
Fake News Detection
Baseline: TF-IDF vectorizer + Logistic Regression trained solely on news titles labeled "FAKE" or "REAL"

Transformer-based: Hugging Face’s DistilBERT model fine-tuned on SST-2 sentiment as demo. Labels "NEGATIVE" mapped to FAKE and "POSITIVE" mapped to REAL. Suitable for demo only; real fine-tuning recommended.

Fake News Generation
GPT-2 generates coherent fake news text based on a user-entered title seed with adjustable generation length, temperature, and number of samples.

Code Structure
text
├── app.py              # Streamlit application combining detection & generation
├── Fake.csv            # Kaggle fake news dataset portion (downloaded)
├── True.csv            # Kaggle real news dataset portion (downloaded)
├── kaggle.json         # Your Kaggle API token (not included in repo)
├── README.md           # This documentation
└── requirements.txt    # (Optional) dependency list
Ethical Use Disclaimer
This system is designed for educational and research purposes only.

Generated fake news content must never be shared as real information.

Users should apply critical thinking and media literacy when interpreting model predictions.

The app includes no fact-checking or source verification — it is a tool to study misinformation detection/generation.

Future Work & Improvements
Fine-tune transformers directly on the fake news dataset titles for improved accuracy

Extend detection model to use full article text as input

Support batch processing of multiple news items

Add ability to save or download generated content and detection results

Incorporate explainability (LIME/SHAP) for detection predictions

Experiment with more powerful generative models (GPT-3, GPT-NeoX, etc.)

References
Kaggle Fake and Real News Dataset

Hugging Face Transformers

Streamlit Framework

GPT-2 Language Model

License
MIT License — see LICENSE file for details.

Contact & Contributions
Feel free to open issues or pull requests for improvements or bug fixes.

Happy researching and building responsible AI for combating misinformation!
