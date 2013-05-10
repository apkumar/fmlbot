fmlbot
======

Classifies statements as FML or not FML; A quick machine-learning project to help learn Naive Bayes, NLP, scraping, and Ruby

There are only four real moving parts here.

FMLbot.rb is the instance of the learned robot.  It stores the trained model and can be quered by the other components.

Tokenizer.rb takes full-text strings as input and outputs their tokenized outputs.  This involves both filtering of stop words and stemming of components.

script.rb stitches everything together.

Rakefile.rb is basically used to scrape fmylife.com for training data.