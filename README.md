# NLP_Webcrawler_summarization
In today’s digital age, the volume of information available on the internet is overwhelming. Users often struggle to sift through large amounts of content across multiple platforms to find relevant and concise information that aligns with their
specific interests. Traditional web browsing requires individuals to navigate through
numerous search engines and websites, leading to information overload, inefficient time usage, and missed opportunities for discovering valuable content. This challenge is
compounded by the fact that search engines and platforms each have unique algorithms and indexing strategies, making it difficult for users to consistently obtain tailored, relevant, and real-time information across multiple sources.
To address this issue, an intelligent, automated solution is required—one that can continuously crawl the web, summarise content in real time, and deliver personalised information that aligns with user preferences. A web crawler with intelligent
summarization and alert capabilities can reduce the noise of information overload, allowing users to stay informed on topics that matter most to them without the need for manual searches.

# Problem statement
The problem at hand is how to efficiently extract and sum-marise information from multiple search engines—Google,DuckDuckGo, Yahoo, Yandex, and Microsoft Edge—while offering real-time, personalised updates that are tailored to users’ specific interests.

# Methodology
# A. Data collection
The system starts by allowing users to input a search
query along with a specific date range. Selenium is then
used to interact with various search engines like Google,
Bing, Yandex, DuckDuckGo, and Yahoo. Once the search is
complete, Selenium or BeautifulSoup collects key information
such as URLs, titles, and publication dates from the search
results. These are filtered based on the provided date range,
and the top ten most frequently appearing URLs are selected
for further analysis.
# B. Pre-processing
Scrapy or browsers such as Google’s Goose, Safara, or Pyra-
mid Scrapy extract contents independently from the HTML
tags, discarding features that users do not need, like navigation
menus. The next step is Text pre-processing during which it
is cleaner and normalized using tools from libraries such as
NLTK, Spacy or Regex. It is involved with the removal of
HTML tags, stop words among other noise that does not add
value to the processing that will be done on the articles.
# C. Embeddings
The clean text is then tokenized by using a BART tokenizer
which transposes the actual text into tokenized format for
model input. Tokenization helps the summarization model
in data preprocessing by converting the pre-processed pieces
of content into something which the neural network will
understand.
# D. Model Architecture
In the system’s model for the summarization task, BART
stands for Bidirectional and Auto-Regressive Transformer.
The model consists of two primary components: Bidirectional
Encoder: Preserves all the information of the input text by
decoding the text forward and backward. Autoregressive De-
coder: Produce a summary token by token; let some of the
already produced tokens feed a consecutive step of the process.
In softmax and linear layers, numbers are produced for each
of the tokens, thereby enabling the generation of the next word
in the summary. A random encoder initializes raw inputs so
they can be more readable and easily interpreted by the model.
# E. evaluation
After the system produces a summary, the user inspects it
and offers comments on the quality of the summary. Such feed-
back loop enable the system to be self-improving and thereby
enhancing the possibility of generating good summaries that
will suit the user
