## Machine Learning with Text in Python

* **Instructor:** [Kevin Markham](http://www.dataschool.io/about/)
* **Teaching Assistant:** [Alex Egorenkov](https://www.linkedin.com/in/aegorenkov)
* [Course information and FAQs](http://www.dataschool.io/learn/)
* [Slack team](https://mltextpython.slack.com/)

### Course Schedule

* [Before the Course](#before-the-course)
* [Week 1: Working with Text Data in scikit-learn](#week-1-working-with-text-data-in-scikit-learn)
* [Week 2: Basic Natural Language Processing (NLP)](#week-2-basic-natural-language-processing-nlp)
* [Week 3: Intermediate NLP and Basic Regular Expressions](#week-3-intermediate-nlp-and-basic-regular-expressions)
* [Week 4: Intermediate Regular Expressions](#week-4-intermediate-regular-expressions)
* [Week 5: Working a Text-Based Data Science Problem](#week-5-working-a-text-based-data-science-problem)
* [Week 6: Advanced Machine Learning Techniques](#week-6-advanced-machine-learning-techniques)
* [After the Course](#after-the-course)

### Course Videos

Links to the video recordings can be found under each section below. Alternatively, you can [view all of the videos on one page](http://www.dataschool.io/mltext-videos/), or [view the YouTube playlist](https://www.youtube.com/playlist?list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I).

### Software Versions

The course was originally taught using **scikit-learn 0.17** and **Python 2.7**. Due to some minor changes to the scikit-learn API since that time, a small percentage of the course code is out of date. (You can read my [summary of the relevant changes](https://www.dataschool.io/how-to-update-your-scikit-learn-code-for-2018/).) I am currently updating the course notebooks and scripts to use **scikit-learn 0.21** and **Python 3.7**.

If you would like to access the original notebooks and scripts, they will always be available in the [archive branch](https://github.com/dataschool/MLtext2/tree/archive).

-----

### Before the Course

* Make sure that [scikit-learn](http://scikit-learn.org/stable/install.html), [pandas](http://pandas.pydata.org/pandas-docs/stable/install.html), and [matplotlib](http://matplotlib.org/users/installing.html) (and their dependencies) are installed on your system. The easiest way to accomplish this is by downloading the [Anaconda distribution](https://www.anaconda.com/distribution/) of Python. Both Python 2 and 3 are welcome.
* If you are not familiar with Git and GitHub, watch my [quick introduction to Git and GitHub](https://www.youtube.com/watch?v=zYG8B8q722g) (8 minutes). Note that the repository shown in the video is from a previous iteration of the course, and the GitHub interface has also changed slightly.
    * For a longer introduction to Git and GitHub, watch my [11-video series](https://www.youtube.com/playlist?list=PL5-da3qGB5IBLMp7LtN8Nc3Efd4hJq0kD) (36 minutes).
* If you are not familiar with the Jupyter notebook, watch my [introductory video](https://www.youtube.com/watch?v=IsXXlYVBt1M&t=4m57s) (8 minute segment). Note that the Jupyter notebook was previously called the "IPython notebook", and the interface has also changed slightly. (Here is the [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/02_machine_learning_setup.ipynb) shown in the video.)
* If you are not yet comfortable with scikit-learn, review the notebooks and/or videos from my [scikit-learn video series](https://github.com/justmarkham/scikit-learn-videos), focusing specifically on the following topics:
    * Machine learning terminology, and working with data in scikit-learn ([video 3](https://www.youtube.com/watch?v=hd1W4CyPX58&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=3), [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/03_getting_started_with_iris.ipynb))
    * scikit-learn's 4-step modeling pattern ([video 4](https://www.youtube.com/watch?v=RlQuVL6-qe8&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=4), [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/04_model_training.ipynb))
    * Train/test split ([video 5](https://www.youtube.com/watch?v=0pP4EwWJgIU&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=5), [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/05_model_evaluation.ipynb))
    * Accuracy, confusion matrix, and AUC ([video 9](https://www.youtube.com/watch?v=85dtiMz9tSo&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=9), [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/09_classification_metrics.ipynb))
* If you are not yet comfortable with pandas, review the notebook and/or videos from my [pandas video series](https://github.com/justmarkham/pandas-videos). Alternatively, review another one of my [recommended pandas resources](http://www.dataschool.io/best-python-pandas-resources/).

-----

### Week 1: Working with Text Data in scikit-learn

**Topics covered:**
* Model building in scikit-learn (refresher)
* Representing text as numerical data
* Reading the SMS data
* Vectorizing the SMS data
* Building a Naive Bayes model
* Comparing Naive Bayes with logistic regression
* Calculating the "spamminess" of each token
* Creating a DataFrame from individual text files

**Video recordings:**
* [Part 1](https://www.youtube.com/watch?v=Qtbrdvc2ags&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=1) (1:08:05)
* [Part 2](https://www.youtube.com/watch?v=G6G7BMkQLY4&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=2) (52:33)

**Before class:**
* Read Paul Graham's classic post, [A Plan for Spam](http://www.paulgraham.com/spam.html), for an overview of a basic text classification system (using a Bayesian approach).
* Read this brief Quora post on [airport security](http://www.quora.com/In-laymans-terms-how-does-Naive-Bayes-work/answer/Konstantin-Tt) for an intuitive explanation of how Naive Bayes classification works.
* Watch [What is Text Classification?](https://www.youtube.com/watch?v=kxImnFg4ZiQ&list=PLQiyVNMpDLKnZYBTUOlSI9mi9wAErFtFm&index=24) (8 minutes) and [Naive Bayes](https://www.youtube.com/watch?v=j39c7Gjx2gE&list=PLQiyVNMpDLKnZYBTUOlSI9mi9wAErFtFm&index=25) (3 minutes) from Coursera's NLP course. (Here are the [slides](http://spark-public.s3.amazonaws.com/nlp/slides/naivebayes.pdf) used in the videos.)

**During class:**
* Working with Text Data in scikit-learn ([notebook](notebooks/01_text_data.ipynb), [notebook with output](notebooks/01_text_data_updated.ipynb), [script](scripts/01_text_data.py))
    * Documentation: [Text feature extraction](http://scikit-learn.org/stable/modules/feature_extraction.html#text-feature-extraction), [CountVectorizer](http://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html), [MultinomialNB](http://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.MultinomialNB.html)
    * Dataset: [SMS spam collection](https://archive.ics.uci.edu/ml/datasets/SMS+Spam+Collection)

**After class:**
* Homework with Yelp reviews data ([notebook](notebooks/01_yelp_homework.ipynb), [script](scripts/01_yelp_homework.py))
    * Dataset: Subset of the data from Kaggle's [Yelp Business Rating Prediction](https://www.kaggle.com/c/yelp-recsys-2013) competition
    * Solution ([notebook](notebooks/01_yelp_homework_solution.ipynb), [script](scripts/01_yelp_homework_solution.py))

**Resources:**
* The scikit-learn documentation describes the [performance trade-offs](https://scikit-learn.org/stable/modules/computing.html#influence-of-the-input-data-representation) involved when choosing between sparse and dense input data representations.
* If you enjoyed Paul Graham's article, you can read [his follow-up article](http://www.paulgraham.com/better.html) on how he improved his spam filter and this [related paper](http://www.merl.com/publications/docs/TR2004-091.pdf) about state-of-the-art spam filtering in 2004.
* If you like cheat sheets, this is a well-organized 12-page [Cheat sheet to the pandas DataFrame object](https://ugoproto.github.io/ugo_py_doc/Pandas_DataFrame_Notes.pdf).
* For an introduction to Naive Bayes, read Sebastian Raschka's article on [Naive Bayes and Text Classification](http://sebastianraschka.com/Articles/2014_naive_bayes_1.html). As well, Wikipedia has two excellent articles ([Naive Bayes classifier](http://en.wikipedia.org/wiki/Naive_Bayes_classifier) and [Naive Bayes spam filtering](http://en.wikipedia.org/wiki/Naive_Bayes_spam_filtering)), and Cross Validated has a good [Q&A](http://stats.stackexchange.com/questions/21822/understanding-naive-bayes).
* For an introduction to logistic regression, read my [lesson notebook](http://nbviewer.jupyter.org/github/justmarkham/DAT8/blob/master/notebooks/12_logistic_regression.ipynb).
* For a comparison of Naive Bayes and logistic regression (and other classifiers), read the [Supervised learning superstitions cheat sheet](http://ryancompton.net/assets/ml_cheat_sheet/supervised_learning.html) or browse my [comparison table](http://www.dataschool.io/comparing-supervised-learning-algorithms/). Also, this [paper by Andrew Ng](http://ai.stanford.edu/~ang/papers/nips01-discriminativegenerative.pdf) compares the performance of Naive Bayes and logistic regression across a variety of datasets, demonstrating that logistic regression tends to have a lower asymptotic error than Naive Bayes.
* The scikit-learn documentation on [probability calibration](http://scikit-learn.org/stable/modules/calibration.html) explains what it means for a predicted probability to be calibrated, and my blog post on [click-through rate prediction with logistic regression](https://web.archive.org/web/20160420174205/http://blog.dato.com/beginners-guide-to-click-through-rate-prediction-with-logistic-regression) explains why calibrated probabilities are useful in the real world.

-----

### Week 2: Basic Natural Language Processing (NLP)

**Topics covered:**
* What is NLP?
* Reading in the Yelp reviews corpus
* Tokenizing the text
* Comparing the accuracy of different approaches
* Removing frequent terms (stop words)
* Removing infrequent terms
* Handling Unicode errors

**Video recordings:**
* [Part 1](https://www.youtube.com/watch?v=QaWYpEVzjkk&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=3) (1:05:32)
* [Part 2](https://www.youtube.com/watch?v=TB8ptQ35Wzo&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=4) (1:05:39)
* [Explanation of Week 2 homework solution](https://www.youtube.com/watch?v=T4zbsw6cl1s&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=5) (1:07:01)

**Before class:**
* Watch [Introduction to NLP](https://www.youtube.com/watch?v=3Dt_yh1mf_U&list=PLQiyVNMpDLKnZYBTUOlSI9mi9wAErFtFm&index=1) (13 minutes) from Coursera's NLP course. (Here are the [slides](http://spark-public.s3.amazonaws.com/nlp/slides/intro.pdf) used in the video.)
* Read the [CountVectorizer documentation](http://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html), focusing on the Parameters section, for a preview of some of the options we will tune during class.

**During class:**
* Basic Natural Language Processing ([notebook](notebooks/02_basic_nlp.ipynb), [notebook with output](notebooks/02_basic_nlp_updated.ipynb), [script](scripts/02_basic_nlp.py))
    * Documentation: [CountVectorizer](http://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html), [Decoding text files](http://scikit-learn.org/stable/modules/feature_extraction.html#decoding-text-files)
    * Dataset: Subset of the data from Kaggle's [Yelp Business Rating Prediction](https://www.kaggle.com/c/yelp-recsys-2013) competition

**After class:**
* Homework with McDonald's sentiment data ([notebook](notebooks/02_mcdonalds_homework.ipynb), [script](scripts/02_mcdonalds_homework.py))
    * Dataset: McDonald's customer comments annotated by [CrowdFlower](http://www.crowdflower.com/data-for-everyone)
    * Solution ([notebook](notebooks/02_mcdonalds_homework_solution.ipynb), [script](scripts/02_mcdonalds_homework_solution.py), [video explanation](https://www.youtube.com/watch?v=T4zbsw6cl1s&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=5))

**Resources:**
* [A Few Useful Things to Know about Machine Learning](https://homes.cs.washington.edu/~pedrod/papers/cacm12.pdf) is a classic paper that discusses multiple topics relevant to this week's class: overfitting, feature engineering, and the curse of dimensionality.
* [Automatically Categorizing Yelp Businesses](http://engineeringblog.yelp.com/2015/09/automatically-categorizing-yelp-businesses.html) discusses how Yelp uses NLP and scikit-learn to solve the problem of uncategorized businesses.
* [Putting 1 million new words into the dictionary](https://www.youtube.com/watch?v=sum5Hq2FTsw) (42 minutes) presents a Python-based text classification pipeline for locating the definitions of previously undefined words.
* [How to Read the Mind of a Supreme Court Justice](http://fivethirtyeight.com/features/how-to-read-the-mind-of-a-supreme-court-justice/) discusses CourtCast, a machine learning model that predicts the outcome of Supreme Court cases using text-based features only. (The CourtCast creator wrote a post explaining [how it works](https://sciencecowboy.wordpress.com/2015/03/05/predicting-the-supreme-court-from-oral-arguments/), and the [Python code](https://github.com/nasrallah/CourtCast) is available on GitHub.)
* [Identifying Humorous Cartoon Captions](http://www.cs.huji.ac.il/~dshahaf/pHumor.pdf) is a readable paper about identifying funny captions submitted to the New Yorker Caption Contest.
* The Unicode Consortium has helpful materials on the Unicode standard, including a [Technical Introduction](http://www.unicode.org/standard/principles.html) and an incredibly detailed [tutorial](http://www.unicode.org/notes/tn23/Muller-Slides+Narr.pdf).
* [The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets](http://www.joelonsoftware.com/articles/Unicode.html) is a classic post by Joel Spolsky. [Unicode in Python, Completely Demystified](http://farmdev.com/talks/unicode/), Ned Batchelder's [Pragmatic Unicode](http://nedbatchelder.com/text/unipain.html), the [Unicode HOWTO](https://docs.python.org/3/howto/unicode.html) from Python's documentation, and this [StackOverflow Q&A](http://stackoverflow.com/questions/11339955/python-string-encode-decode) are also good resources.
* If you are a fan of emoji, you may enjoy browsing the Unicode Code Charts for [Emoticons](http://www.unicode.org/charts/PDF/U1F600.pdf) and [Miscellaneous Symbols and Pictographs](http://www.unicode.org/charts/PDF/U1F300.pdf), or reading about [how to propose a new emoji](https://www.joypixels.com/blog/so-you-want-to-propose-an-emoji-to-unicode-heres-how).
* The scikit-learn documentation on [decoding text files](http://scikit-learn.org/stable/modules/feature_extraction.html#decoding-text-files) contains good advice for dealing with encoding errors.

-----

### Week 3: Intermediate NLP and Basic Regular Expressions

**Topics covered:**
* Intermediate NLP:
    * Reading in the Yelp reviews corpus
    * Term Frequency-Inverse Document Frequency (TF-IDF)
    * Using TF-IDF to summarize a Yelp review
    * Sentiment analysis using TextBlob
* Basic Regular Expressions:
    * Why learn regular expressions?
    * Rules for searching
    * Metacharacters
    * Quantifiers
    * Using regular expressions in Python
    * Match groups
    * Character classes
    * Finding multiple matches

**Video recordings:**
* [Part 1](https://www.youtube.com/watch?v=jEsEJlrn-io&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=6) on Intermediate NLP (56:51)
* [Part 2](https://www.youtube.com/watch?v=Vyn99hLGZwM&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=7) on Basic Regular Expressions (1:27:21)

**Before class:**
* Install TextBlob by following [these instructions](https://github.com/sloria/TextBlob/blob/dev/docs/install.rst), and then test that installation was successful by running `import textblob` from within Python.

**During class:**
* Intermediate Natural Language Processing ([notebook](notebooks/03_intermediate_nlp.ipynb), [notebook with output](notebooks/03_intermediate_nlp_updated.ipynb), [script](scripts/03_intermediate_nlp.py))
    * Documentation: [CountVectorizer](http://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html), [TfidfVectorizer](http://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html), [TextBlob](https://textblob.readthedocs.org/)
    * Dataset: Subset of the data from Kaggle's [Yelp Business Rating Prediction](https://www.kaggle.com/c/yelp-recsys-2013) competition
* Basic Regular Expressions
    * [Regular expressions 101](https://regex101.com/#python): real-time testing of regular expressions
    * Reference guide ([notebook](notebooks/03_basic_regex.ipynb), [notebook with output](notebooks/03_basic_regex_updated.ipynb), [script](scripts/03_basic_regex.py))
    * Class exercises ([notebook](notebooks/03_basic_regex_exercise.ipynb), [script](scripts/03_basic_regex_exercise.py))
    * Solution to class exercises ([notebook](notebooks/03_basic_regex_exercise_solution.ipynb), [script](scripts/03_basic_regex_exercise_solution.py))
    * Datasets: Baltimore homicides, email messages

**After class:**
* Using TF-IDF, write a document summarizer for a corpus of your choosing, but summarize using full sentences or paragraphs rather than individual words. (This approach is similar to the [SMMRY](http://smmry.com/about) algorithm, which is used by Reddit's [autotldr](https://np.reddit.com/r/autotldr/comments/31b9fm/faq_autotldr_bot/).)
    * Before beginning, you may want to watch the [four lectures on summarization](https://www.youtube.com/watch?v=wUF9r2pMEag&list=PLQiyVNMpDLKnZYBTUOlSI9mi9wAErFtFm&index=98) (28 minutes) from Coursera's NLP course. (Here are the [slides](http://spark-public.s3.amazonaws.com/nlp/slides/summarization.pdf) used in the videos.)
    * You can use my lesson code as a starting point, or build something from scratch!
    * Example solution ([notebook](notebooks/03_intermediate_nlp_homework_solution.ipynb), [script](scripts/03_intermediate_nlp_homework_solution.py))
* Homework with basic regular expressions ([notebook](notebooks/03_basic_regex_homework.ipynb), [script](scripts/03_basic_regex_homework.py))
    * Datasets: [FAA tower closures](http://www.faa.gov/news/media/fct_closed.pdf), my Stack Overflow [reputation history](http://stackoverflow.com/reputation)
    * Solution ([notebook](notebooks/03_basic_regex_homework_solution.ipynb), [script](scripts/03_basic_regex_homework_solution.py))

**NLP Resources:**
* Coursera's NLP course has [video lectures](https://www.youtube.com/playlist?list=PLQiyVNMpDLKnZYBTUOlSI9mi9wAErFtFm) on sentiment analysis, TFIDF, summarization, and many other fundamental NLP topics. (Here are the [slides](http://web.stanford.edu/~jurafsky/NLPCourseraSlides.html) used in all of the videos.)
* [TF-IDF is about what matters](http://planspace.org/20150524-tfidf_is_about_what_matters/) explains how scikit-learn computes TF-IDF scores.
* FiveThirtyEight used TF-IDF to compute the most repeated talking points by the 2016 [Republican](http://fivethirtyeight.com/features/these-are-the-phrases-each-gop-candidate-repeats-most/) and [Democratic](http://fivethirtyeight.com/features/these-are-the-phrases-that-sanders-and-clinton-repeat-most/) presidential candidates. (Here is the [data and Python script](https://github.com/fivethirtyeight/data/tree/master/repeated-phrases-gop) for the Republican analysis.)
* [The Simpsons by the Data](http://toddwschneider.com/posts/the-simpsons-by-the-data/) uses TF-IDF on episode scripts from The Simpsons to create episode summaries. (Here is the [dataset](https://www.kaggle.com/wcukierski/the-simpsons-by-the-data).)
* [Modern Methods for Sentiment Analysis](http://districtdatalabs.silvrback.com/modern-methods-for-sentiment-analysis) shows how "word vectors" can be used for more accurate sentiment analysis.
* In [Sentiment Classification Using scikit-learn](https://www.youtube.com/watch?v=y3ZTKFZ-1QQ) (50 minutes), Facebook explains how they detect sentiment by training a Naive Bayes model on emoji-labeled data.
* [Natural Language Processing with Python](http://www.nltk.org/book/) is the most popular book for going in-depth with the [Natural Language Toolkit](http://www.nltk.org/) (NLTK).
* [spaCy](https://spacy.io/) is a newer Python library for text processing that is focused on performance (unlike NLTK).
* If you want to get serious about NLP, [Stanford CoreNLP](http://stanfordnlp.github.io/CoreNLP/) is a suite of tools (written in Java) that is highly regarded.

**Regular Expressions Resources:**
* Google's Python Class includes an excellent [introductory lesson](https://developers.google.com/edu/python/regular-expressions) on regular expressions (which also has an associated [video](https://www.youtube.com/watch?v=kWyoYtvJpe4&index=4&list=PL5-da3qGB5IA5NwDxcEJ5dvt8F9OQP7q5)).
* Python for Informatics has a nice [chapter](http://www.pythonlearn.com/html-270/book012.html) on regular expressions. (If you want to run the examples, you'll need to download [mbox.txt](http://www.py4inf.com/code/mbox.txt) and [mbox-short.txt](http://www.py4inf.com/code/mbox-short.txt).)
* This relatively simple [regular expression pattern](http://sentiment.christopherpotts.net/tokenizing.html#emoticons) can apparently capture 96% of emoticons used on Twitter.

-----

### Week 4: Intermediate Regular Expressions

**Topics covered:**
* Week 3 homework review
* Greedy or lazy quantifiers
* Alternatives
* Substitution
* Anchors
* Option flags
* Assorted functionality

**Video recordings:**
* [Part 1](https://www.youtube.com/watch?v=kYbDXprRx4Y&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=8) (1:03:24)
* [Part 2](https://www.youtube.com/watch?v=tX7G77V7YyI&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=9) (1:00:10)

**During class:**
* Intermediate Regular Expressions
    * [Regular expressions 101](https://regex101.com/#python): real-time testing of regular expressions
    * Reference guide ([notebook](notebooks/04_intermediate_regex.ipynb), [notebook with output](notebooks/04_intermediate_regex_updated.ipynb), [script](scripts/04_intermediate_regex.py))
    * Class exercises ([notebook](notebooks/04_intermediate_regex_exercise.ipynb), [script](scripts/04_intermediate_regex_exercise.py))
    * Solution to class exercises ([notebook](notebooks/04_intermediate_regex_exercise_solution.ipynb), [script](scripts/04_intermediate_regex_exercise_solution.py))
    * Datasets: [FAA tower closures](http://www.faa.gov/news/media/fct_closed.pdf), my Stack Overflow [reputation history](http://stackoverflow.com/reputation), Baltimore homicides, subset of the data from Kaggle's [Yelp Business Rating Prediction](https://www.kaggle.com/c/yelp-recsys-2013) competition, [IMDb top 100 movies](http://www.imdb.com/chart/top)

**After class:**
* Homework with intermediate regular expressions ([notebook](notebooks/04_intermediate_regex_homework.ipynb), [script](scripts/04_intermediate_regex_homework.py))
    * Dataset: [UFO reports](https://github.com/planetsig/ufo-reports) from the [National UFO Reporting Center](http://www.nuforc.org/)
    * Solution ([notebook](notebooks/04_intermediate_regex_homework_solution.ipynb), [script](scripts/04_intermediate_regex_homework_solution.py))

**Resources:**
* The [Regular Expression HOWTO](https://docs.python.org/3/howto/regex.html) from Python's documentation is well-written and includes some additional functionality not covered in class.
* Here are two nice sets of exercises ([part 1](https://regex.netlify.com/exercises), [part 2](https://regex.netlify.com/exercises2)) for practicing regular expressions, including solutions ([part 1](http://pastebin.com/DbGHbmUF), [part 2](http://pastebin.com/nVDrfJ1K)). The same author also created a simple [regex cheat sheet](https://regex.netlify.com/cheat-sheet).
* [Regex Golf](http://regex.alf.nu/) is an interactive game for practicing regular expressions. (It inspired this [xkcd comic](http://www.explainxkcd.com/wiki/index.php/1313:_Regex_Golf), which then inspired two lengthy notebooks by Peter Norvig: [part 1](http://nbviewer.jupyter.org/url/norvig.com/ipython/xkcd1313.ipynb), [part 2](http://nbviewer.jupyter.org/url/norvig.com/ipython/xkcd1313-part2.ipynb).)
* If you want to go really deep with regular expressions, [RexEgg](http://www.rexegg.com/) includes endless articles and tutorials.
* [Exploring Expressions of Emotions in GitHub Commit Messages](http://geeksta.net/geeklog/exploring-expressions-emotions-github-commit-messages/) is a fun example of how regular expressions can be used for data analysis, and [Writing a Fuzzy Receipt Parser in Python](http://tech.trivago.com/2015/10/06/python_receipt_parser/) demonstrates the use of regular expressions for extracting structured data from OCR-generated text.

-----

### Week 5: Working a Text-Based Data Science Problem

**Topics covered:**
* Reading in and exploring the data
* Feature engineering
* Model evaluation using train_test_split and cross_val_score
* Making predictions for new data
* Searching for optimal tuning parameters using GridSearchCV
* Extracting features from text using CountVectorizer
* Chaining steps into a Pipeline

**Video recordings:**
* [Part 1](https://www.youtube.com/watch?v=3ptoJ7A4Ogw&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=10) (1:13:13)
* [Part 2](https://www.youtube.com/watch?v=6btVIHcBjAM&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=11) (1:00:50)

**Before class:**
* Watch my video on [cross-validation](https://www.youtube.com/watch?v=6dbrR-WymjI&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=7) (36 minutes), or at least scan through the associated [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/07_cross_validation.ipynb), to refresh your memory on how cross-validation works and how to use it in scikit-learn.
* Browse through the information about Kaggle's [What's Cooking?](https://www.kaggle.com/c/whats-cooking) competition, which is the problem we will work through during class. (The data files have already been added to our repository, so there is no need to download them from Kaggle.)
* Watch my video presentation about a [past Kaggle competition](https://www.youtube.com/watch?v=HGr1yQV3Um0) (16 minutes) for a tour of the end-to-end machine learning process. (Here are the associated [slides](https://speakerdeck.com/justmarkham/allstate-purchase-prediction-challenge-on-kaggle).)

**During class:**
* Working a Text-Based Data Science Problem ([notebook](notebooks/05_kaggle.ipynb), [notebook with output](notebooks/05_kaggle_updated.ipynb), [script](scripts/05_kaggle.py))
    * Kaggle competition: [What's Cooking?](https://www.kaggle.com/c/whats-cooking)
    * Documentation: [Nearest Neighbors classification](http://scikit-learn.org/stable/modules/neighbors.html#nearest-neighbors-classification), [Cross-validation](http://scikit-learn.org/stable/modules/cross_validation.html), [Dummy estimators](http://scikit-learn.org/stable/modules/model_evaluation.html#dummy-estimators), [Grid search](http://scikit-learn.org/stable/modules/grid_search.html), [Imputation of missing values](https://scikit-learn.org/stable/modules/impute.html), [Pipeline](http://scikit-learn.org/stable/modules/pipeline.html)

**After class:**
* Homework with Hacker News data ([notebook](notebooks/05_hacker_news_homework.ipynb), [script](scripts/05_hacker_news_homework.py))
    * Dataset: A year of posts from [Hacker News](https://www.kaggle.com/hacker-news/hacker-news-posts)
    * Solution ([notebook](notebooks/05_hacker_news_homework_solution.ipynb), [script](scripts/05_hacker_news_homework_solution.py))

**Resources:**
* [Learning from the best](http://blog.kaggle.com/2014/08/01/learning-from-the-best/) is an excellent blog post covering top tips from Kaggle Masters on how to do well on Kaggle.
* [Getting in Shape for the Sport of Data Science](https://www.youtube.com/watch?v=kwt6XEh7U3g) (74 minutes), by Jeremy Howard (past president of Kaggle), contains a lot of tips for competitive machine learning.
* [Feature Engineering Without Domain Expertise](https://www.youtube.com/watch?v=bL4b1sGnILU) (17 minutes), a talk by Kaggle Master Nick Kridler, provides some simple advice about how to iterate quickly and where to spend your time during a Kaggle competition.
* [Non-Mathematical Feature Engineering Techniques](https://codesachin.wordpress.com/2016/06/25/non-mathematical-feature-engineering-techniques-for-data-science/) includes some simple ideas for getting started with feature engineering.
* [How do I create dummy variables in pandas?](https://www.youtube.com/watch?v=0s_1IsROgDc&list=PL5-da3qGB5ICCsgW1MxlZ0Hq8LL5U3u9y&index=24) (13 minutes) demonstrates three ways to create dummy variables from unordered categorical features, one of the most common feature engineering techniques.
* Kaggle Master Triskelion provides a list of [advanced feature engineering and feature selection tactics](https://www.kaggle.com/c/bnp-paribas-cardif-claims-management/forums/t/18754/feature-engineering) in a thread from Kaggle's forums.
* These examples may help you to better understand the process of feature engineering: predicting the number of [passengers at a train station](https://medium.com/@chris_bour/french-largest-data-science-challenge-ever-organized-shows-the-unreasonable-effectiveness-of-open-8399705a20ef), identifying [fraudulent users of an online store](https://docs.google.com/presentation/d/1UdI5NY-mlHyseiRVbpTLyvbrHxY8RciHp5Vc-ZLrwmU/edit#slide=id.p), identifying [bots in an online auction](https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot/forums/t/14628/share-your-secret-sauce), predicting who will [subscribe to the next season of an orchestra](http://blog.kaggle.com/2015/01/05/kaggle-inclass-stanfords-getting-a-handel-on-data-science-winners-report/), evaluating the [quality of e-commerce search engine results](http://blog.kaggle.com/2015/07/22/crowdflower-winners-interview-3rd-place-team-quartet/), and predicting [user engagement in a corporate social network](https://github.com/mikeyea/DAT7_project/blob/master/final%20project/Class_Presention_MYea.ipynb).
* Watch my video on [GridSearchCV](https://www.youtube.com/watch?v=Gol_qOgRqfA&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=8) (28 minutes) for a recap of part of this week's lesson. (Here is the associated [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/08_grid_search.ipynb).)

-----

### Week 6: Advanced Machine Learning Techniques

**Topics covered:**
* Reading in the Kaggle data and adding features
* Using a Pipeline for proper cross-validation
* Combining GridSearchCV with Pipeline
* Efficiently searching for tuning parameters using RandomizedSearchCV
* Adding features to a document-term matrix (using SciPy)
* Adding features to a document-term matrix (using FeatureUnion)
* Ensembling models
* Locating groups of similar cuisines
* Model stacking

**Video recordings:**
* [Part 1](https://www.youtube.com/watch?v=NhDlrY1QGtA&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=12) (57:10)
* [Part 2](https://www.youtube.com/watch?v=v6XPBaHnTw0&list=PL5-da3qGB5ICtEuNW8zWzmxc_NqCHhy_I&index=13) (1:12:07)

**Before class:**
* This class builds directly on the previous class, and so I highly recommend that you review the [week 5 notebook](notebooks/05_kaggle_updated.ipynb) in advance of class.
* If you're unfamiliar with the distinction between "class predictions" and "predicted probabilities of class membership", watch my video on [classifier evaluation](https://www.youtube.com/watch?v=85dtiMz9tSo&list=PL5-da3qGB5ICeMbQuqbbCOQWcS6OYBr5A&index=9) (55 minutes), focusing on the section "Adjusting the classification threshold". (Here is the associated [notebook](https://github.com/justmarkham/scikit-learn-videos/blob/master/09_classification_metrics.ipynb).)
* Install Seaborn by following [these instructions](http://seaborn.pydata.org/installing.html), and then test that installation was successful by running `import seaborn as sns` from within Python.

**During class:**
* Advanced Machine Learning Techniques ([notebook](notebooks/06_kaggle.ipynb), [notebook with output](notebooks/06_kaggle_updated.ipynb), [script](scripts/06_kaggle.py))
    * Kaggle competition: [What's Cooking?](https://www.kaggle.com/c/whats-cooking)
    * Documentation: [Grid search](http://scikit-learn.org/stable/modules/grid_search.html), [Pipeline and FeatureUnion](http://scikit-learn.org/stable/modules/pipeline.html), [Custom transformers](http://scikit-learn.org/stable/modules/preprocessing.html#custom-transformers), [Seaborn](http://seaborn.pydata.org/)

**After class:**
* Create your own model for the What's Cooking? competition, and submit your predictions to Kaggle! Try tuning your model using some of the techniques we have learned in this course. Also, here are some code samples from Kaggle competitors that may help you to come up with ideas: [sample one](https://github.com/mtad/kaggle/blob/master/whats_cooking/Whats_Cooking.ipynb), [sample two](https://github.com/kylejshaffer/kaggle_whatscooking), [sample three](https://www.kaggle.com/dipayan/whats-cooking/whatscooking-python/code), [sample four](https://github.com/SaquibAhmad/Kaggle/blob/master/whats-cooking/source/svm_model.ipynb).
* Alternatively, practice the techniques you learned this week on the Hacker News homework from week 5.

**Resources:**
* scikit-learn has an incredibly active mailing list that is often much more useful than Stack Overflow for researching functions and asking questions. Search the [archive of the old list](https://www.mail-archive.com/scikit-learn-general@lists.sourceforge.net/) (which closed in May 2016) before searching the [current list](https://www.mail-archive.com/scikit-learn@python.org/).
* Sebastian Raschka has a number of excellent resources for scikit-learn users, including a repository of [tutorials and examples](https://github.com/rasbt/pattern_classification), a library of machine learning [tools and extensions](http://rasbt.github.io/mlxtend/), a recent [book](https://github.com/rasbt/python-machine-learning-book), and a [blog](http://sebastianraschka.com/blog/).
* [Using scikit-learn Pipelines and FeatureUnions](http://zacstewart.com/2014/08/05/pipelines-of-featureunions-of-pipelines.html) and [FeatureUnion with Heterogeneous Data Sources](https://scikit-learn.org/0.18/auto_examples/hetero_feature_union.html) include more complex examples of FeatureUnions and custom transformers.
* [Practical Data Science in Python](http://radimrehurek.com/data_science_python/) is a long and well-written notebook that uses a few advanced scikit-learn features: pipelining, plotting a learning curve, and pickling a model.
* Yoshua Bengio's paper, [Random Search for Hyper-Parameter Optimization](http://www.jmlr.org/papers/volume13/bergstra12a/bergstra12a.pdf), explains the benefits of random search over grid search.
* [Bayesian optimization](https://en.wikipedia.org/wiki/Hyperparameter_optimization) is a methodology for choosing model hyperparameters in a "smarter" way, with the goal of producing better results than grid or random search in less time. Some recent papers on the topic have been [optimistic](http://papers.nips.cc/paper/5872-efficient-and-robust-automated-machine-learning.pdf), whereas others have been [pessimistic](http://www.argmin.net/2016/06/20/hypertuning/). There has been an [attempt](https://github.com/scikit-learn/scikit-learn/pull/5491) to add this technique to scikit-learn, but so far it has stalled.
* [TPOT](https://github.com/EpistasisLab/tpot) is a tool based on scikit-learn that "automatically creates and optimizes machine learning pipelines using genetic programming."
* MLWave's [Kaggle Ensembling Guide](http://mlwave.com/kaggle-ensembling-guide/) is very thorough and explains many different methods for both ensembling and stacking.
* Browse the excellent [solution paper](https://docs.google.com/viewer?url=https://raw.githubusercontent.com/ChenglongChen/Kaggle_CrowdFlower/master/Doc/Kaggle_CrowdFlower_ChenglongChen.pdf) from the winner of Kaggle's [CrowdFlower competition](https://www.kaggle.com/c/crowdflower-search-relevance) for an example of the work and insight required to win a Kaggle competition.
* [Interpretable vs Powerful Predictive Models: Why We Need Them Both](https://medium.com/@chris_bour/interpretable-vs-powerful-predictive-models-why-we-need-them-both-990340074979) is a short post on how the tactics useful in a Kaggle competition are not always useful in the real world.

-----

### After the Course

* Congratulations on completing the course! I would appreciate it if you would fill out the [end of course survey](https://goo.gl/forms/vKWiAHNu5Jliy8oh2). At the end of the survey, you will be able to request a course completion certificate (PDF).