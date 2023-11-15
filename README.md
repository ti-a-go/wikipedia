# Wikipedia

This project uses Wikipedia data for NLP tasks.

# How to access the data

Use __Jupyter Notebooks__ to access the data. ([how to run Jupyter Lab](#running-the-project))

After opening Jupyter Lab on the browser you can create a new notebook and use the objects from the `main` module .

```python
from main import wiki, data, spc

page_titles = wiki.search("Luís Gama")

page = wiki.page(page_titles[0])

data.save_page(page)

doc = spc.doc(page.content)
```

### `wiki`

Use to search on the Wikipedia and get the pages.

### `data`

Use to save/load data locally

### `spc`

Use to process the text data using Spacy.

# Dependencies

## Wikipedia:

[Pypi Registry](https://pypi.org/project/wikipedia/)

[Library API Reference](https://wikipedia.readthedocs.io/en/latest/code.html)

## Spacy

[Official Website](https://spacy.io/)


OBS: In the future we plan to use other libraries as Gensim, Stanza and NLTK to mention a few.

# Data Storage

The current solution stores the data into flat files on OS file system.

An alternative solution is to use a noSQL DB. It needs to be implemented though.

# Running the project

## Create a virtual environment

```shell
python3 -m venv venv
```

## Activate the virtual environment

```shell
source venv/bin/activate
```

## Install the dependencies 

```shell
pip install -r requirements.txt
```

## start Jupyter Lab

```shell
jupyter lab
```

# Wikipedia Dumps

Wikipedia allow us to download all articles data, but it's in XML format.

The latest dump can be found in the file 
[ptwiki-20231020-pages-articles-multistream.xml](./data/ptwiki-20231020-pages-articles-multistream.xml)

The articles index can be found in the index file: [ptwiki-20231020-pages-articles-multistream-index.txt](./data/ptwiki-20231020-pages-articles-multistream-index.txt)

It's necessary a solution to extract the text data from this dump XML file.

[Here's a github repo](https://github.com/eberlitz/pt-br-corpus) that presents a solution that maybe is a good one.

# Web Interface (to be developed)

A web interface to view the Wikipedia data and metadata. More over, this interface will show linguistic features annotated by the [Spacy library](https://spacy.io/).
