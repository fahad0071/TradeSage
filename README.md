
## Installation

Clone the repository

```bash
  git clone https://github.com/kill3rstabs/TradeSageChatbot
  cd TradeSageChatbot
```


Create a python virtual enviornment

```bash
python -m venv .venv
```

Activate your Virtual Enviornment (windows cmd)

```bash
.venv\Scripts\activate
```
or 

Activate your Virtual Enviornment (windows Powershell)

```bash
.\.venv\Scripts\Activate
```
or 

Activate your Virtual Enviornment (mac or linux)

```bash
.venv/bin/activate
```


Copy .env.example into .env (mac or linux)
```bash
cp .env.example .env
```

Copy .env.example into .env (Windows)
```bash
copy .env.example .env
```

Add your API keys for Groq and Hugging Face in the `.env` file:

- **Groq API key**: [https://console.groq.com/keys](https://console.groq.com/keys)
- **Hugging Face token**: [https://huggingface.co/settings/tokens](https://huggingface.co/settings/tokens)


Install the dependencies

```bash
pip install -r requirements.txt
```

Run the flask project
```bash
python app.py
```


## Notebooks
All the notebooks related to the project are in the Notebooks directory

## Data Parsing Scripts
All the scripts which were used to parse the data are stored in Data Engineering directory

## Parsed Data
The final parsed and cleaned data is stored within parsed data.csv

You can add the other data sources by changing the directory in the code.


## Flask app specifics
1. Templates and statics stores the html templates and image files respectively.
2. Ngrok was added to run it on colab you can remove the ngrok now.
