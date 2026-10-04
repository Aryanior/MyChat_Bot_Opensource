# FLAN-T5 Custom Chatbot

An open-source AI chatbot built using **Google FLAN-T5 Large**, **Hugging Face Transformers**, **PyTorch**, and **Gradio**.

This project demonstrates how an open-source instruction-tuned language model can be integrated into an interactive chatbot using prompt construction and a lightweight web interface.

## Features

-  AI-powered conversational interface
-  Powered by Google **FLAN-T5 Large**
-  Hugging Face Transformers integration
-  PyTorch-based model inference
-  Interactive Gradio web interface
-  Prompt-based text generation
-  Supports GPU acceleration when CUDA is available
-  No proprietary LLM API required
-  Built completely with Python

##  How It Works

The chatbot follows a simple text-generation pipeline:

```text
User Input
    ↓
Prompt Construction
    ↓
FLAN-T5 Large
    ↓
Text Generation
    ↓
Generated Response
    ↓
Gradio Chat Interface
```

The user's question is combined with a prompt before being passed to the FLAN-T5 model.

Example:

```text
Question: What is artificial intelligence?
Response:
```

The model then generates the response.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Google FLAN-T5 Large | Language model |
| Hugging Face Transformers | Model loading and inference |
| PyTorch | Deep learning framework |
| Gradio | Interactive chatbot interface |
| Jupyter Notebook | Development and experimentation |

## Model

This project uses:

```text
google/flan-t5-large
```

FLAN-T5 is an instruction-tuned version of the T5 sequence-to-sequence model family developed by Google.

The model is accessed through Hugging Face Transformers.

```python
from transformers import AutoTokenizer, AutoModelForSeq2SeqLM

model_name = "google/flan-t5-large"

tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSeq2SeqLM.from_pretrained(model_name)
```

## Project Structure

```text
flan-t5-custom-chatbot/
│
├── MyChat_Bot_Opensource.ipynb
├── app.py
├── requirements.txt
├── README.md
└── .gitignore
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/flan-t5-custom-chatbot.git
```

Navigate into the project:

```bash
cd flan-t5-custom-chatbot
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Activate it on macOS/Linux:

```bash
source venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Running the Chatbot

Run:

```bash
python app.py
```

After launching, Gradio will provide a local URL where you can interact with the chatbot.

## Running the Notebook

The project also includes the original Jupyter Notebook.

Launch Jupyter:

```bash
jupyter notebook
```

Then open:

```text
MyChat_Bot_Opensource.ipynb
```

## Text Generation

The chatbot uses configurable generation parameters such as:

```python
max_length=200
do_sample=True
temperature=0.2
```

These parameters influence the length and randomness of generated responses.

## Hardware

The application automatically detects whether CUDA is available.

```python
device = torch.device(
    "cuda" if torch.cuda.is_available() else "cpu"
)
```

A CUDA-compatible GPU is recommended for faster inference.

The chatbot can also run on CPU, although inference may be significantly slower because FLAN-T5 Large is a relatively large model.

## Limitations

This project is primarily intended as an open-source learning and experimentation project.

Current limitations include:

- No persistent long-term conversation memory
- No Retrieval-Augmented Generation (RAG)
- No external knowledge base
- No vector database
- Model responses may occasionally be inaccurate
- CPU inference can be slow
- No production-grade authentication or security layer

## Future Improvements

Potential improvements include:

-  Conversation memory
-  RAG-based question answering
-  PDF and document chat
-  Custom knowledge-base integration
-  Vector database integration
-  Streaming responses
-  Improved conversation history
-  User authentication
-  Model quantization
-  Docker support
-  Cloud deployment
-  Response evaluation
-  AI safety and guardrails

## Demo

Add screenshots or a screen recording of the chatbot here.

Example:

```markdown
![Chatbot Demo](docs/chatbot-demo.png)
```

## Privacy

The project does not require a proprietary LLM API key.

When run locally, model inference is performed on the machine running the application.

If deployed publicly, appropriate authentication, security, privacy, and resource-management measures should be implemented.

## Attribution

The original notebook contains attribution to **Anmol Talwar**. Appropriate attribution should be retained when publishing or modifying the original work.

Before redistributing the project or adding a project-level open-source license, verify the licensing requirements of the original code, FLAN-T5, and other third-party components.

## Contributing

Contributions and improvements are welcome.

```bash
git checkout -b feature/new-feature
```

Make your changes, then:

```bash
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
```

Open a Pull Request on GitHub.

## Author

Aryan Mathuriya

GitHub:  
`https://github.com/Aryanior`

## Support

If you found this project useful or interesting, consider giving the repository a on GitHub.
