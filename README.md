# AI-CHATBOT-WITH-NLP

**COMPANY**: CODTECH IT SOLUTIONS

**NAME**: K.Sai Santhosh Reddy

**INTERN ID**: CT04DF611

**DOMAIN**: PYTHON

**DURATION**: 4 WEEKS (MAY 30TH,2025 TO JUNE 30TH,2025)

**MENTOR**: NEELA SANTOSH.

## **Overview of the Chatbot Code**

This Python script is a simple rule-based chatbot that uses the Natural Language Toolkit (NLTK) to preprocess user inputs and match them against a set of predefined patterns. Based on the matched intent, the chatbot returns a relevant response. It serves as a foundational example of natural language processing (NLP) for beginners and includes features such as lemmatization, stopword removal, and pattern matching.

## **Library Imports and Initial Setup**

The script begins by importing the required libraries:

* `nltk`: A popular library used for natural language processing tasks like tokenization, stemming, lemmatization, and more.
* `re`: Python’s built-in module for regular expressions, used to extract words from user inputs.
* `stopwords` and `WordNetLemmatizer` from `nltk.corpus` and `nltk.stem`, respectively, are used to clean the input.
* `random`: Used to select a response randomly from the list of possible replies.

It then downloads the necessary resources using:

```python
nltk.download('wordnet', quiet=True)
nltk.download('stopwords', quiet=True)

This ensures that lemmatization and stopword filtering can work without errors.

## **Text Preprocessing**

The `preprocess()` function takes the user's input text and prepares it for intent matching. It performs the following operations:

1. **Lowercasing** the text to make pattern matching case-insensitive.
2. **Tokenizing** using regular expressions to extract only words and discard punctuation.
3. **Stopword Removal** eliminates common words like “the”, “is”, and “and” which do not add meaning.
4. **Lemmatization** reduces words to their base form (e.g., “running” → “run”) for better comparison.

By the end of this process, the function returns a list of cleaned, meaningful tokens ready for intent detection.

## **Knowledge Base of Intents**

A `knowledge_base` dictionary stores all the supported intents. Each intent includes:

* `patterns`: common user phrases that represent that intent.
* `responses`: the possible replies the bot should return when that intent is detected.

Some defined intents include:

* `greeting`: handles "hello", "hi", "good morning", etc.
* `goodbye`: handles farewells.
* `thanks`: for appreciation.
* `who_are_you`, `help`, and `time` for informational or supportive inquiries.
* `default`: responses for unmatched or unknown inputs.

The chatbot supports both static replies and functional ones. For example, the `time` intent has a lambda function as a response that returns a string, though in this case, it always says real-time data isn't available.

## **Intent Matching**

The function `match_intent(user_input)` processes the user's input and compares it against all predefined patterns. For each intent and pattern:

1. It tokenizes and cleans the pattern using the same preprocessing function.
2. It calculates the overlap between the user input and the pattern using set intersection.
3. The intent with the highest overlap is selected as the best match.

This approach is simple yet effective for small-scale chatbots.

## **Response Generation**

Once an intent is matched, `get_response(intent)` selects a suitable response from the corresponding intent’s response list. If the response is a callable (like a lambda), it executes it; otherwise, it returns the string directly. If no intent is matched, a random message from the default responses is returned to prompt the user for clarification.

## **Chat Loop and User Interaction**

The `chatbot()` function is the core of the user interaction:

* It welcomes the user and explains how to exit the chat.
* Then it enters a loop where it waits for input.
* Based on the input, it calls the `match_intent()` and `get_response()` functions and prints the chatbot’s response.
* If the user types "exit", "quit", or "bye", the loop breaks, and the session ends gracefully.

## **Script Execution Check**

The final line:

```python
if _name_ == "_main_":
```

is meant to ensure that the chatbot only runs when the script is executed directly. However, this line contains a typo. It should be:

```python
if __name__ == "__main__":
```

With the correct syntax, it ensures modularity and prevents the chatbot from running if the script is imported as a module.

## **Conclusion**

In summary, this chatbot uses fundamental NLP techniques such as tokenization, lemmatization, and stopword removal to match user input to predefined intents. It's a great entry point for building conversational agents and can be easily extended with more intents, smarter matching algorithms or a graphical/web interface.

##**OUTPUT**

![Image](https://github.com/user-attachments/assets/584e1841-abd2-4b80-8dd4-217386ae8b91)
