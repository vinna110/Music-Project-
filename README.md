How to Run
Follow these steps to set up and execute the AI pipeline in your own environment.
1. Prerequisites
- A Google Gemini API Key. You can obtain one for free at the Google AI Studio.
- A Google Colab account.

2. Environment Setup

- Open the Notebook: Upload the .ipynb file to Google Colab.
- Configure Secrets: * Click on the Secrets (key icon ) in the left sidebar.
- Add a new secret named GOOGLE_API_KEY.
- Paste your API key into the value field and toggle "Notebook access" to on.
- Install Dependencies: The notebook uses google-generativeai and nltk. These are usually pre-installed or handled within the code cells.

3. Data Ingestion
- Choose a song you wish to analyze.
- Save the song lyrics into a plain text file named lyrics_input.txt.
- Upload this text file to the root directory of your Colab session (Files icon -> Upload).

4. Execution
- Run all cells sequentially (Runtime -> Run all).
- The pipeline will automatically: Load and validate your lyrics file using robust try...except blocks.
- Retrieve metadata with a 3-stage exponential backoff retry mechanism to ensure API resilience.
- Generate a deeply enriched JSON dataset and creative outputs.

5. Expected Outputs
Once executed, the notebook provides:
- Enriched Song Dictionary: A Python dictionary containing parsed metadata (Album, Release Date) and deep analysis (Genre, Sentiments, Themes).
- Contextual Recommendations: A curated list of similar media based on lyrical depth.
- Creative Synthesis: Original song verses and critical reviews generated based on the specific "DNA" of your chosen song.
