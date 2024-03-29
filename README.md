# Email Classifier

#### This was implemented under the valuable guidance of Prof David Crandall at Indiana University in B551 Elements of AI during Fall 2019.

This is a supervised document classification problem where the algorithm helps in deciding whether an e-mail is a spam or not spam. This problem can be considered as a classic example of Naive Bayes Implementation. The naive Bayes implementation typically is derived from the Bayes Net Problem, keeping in mind the assumption that there exists conditional independence amongst all the observable variables. In the context of this problem, the assumption is that we consider email as a bag of words instead of considering any relation between a set of words or considering rules of grammar.

For example, if we have an email with n words, so we need to find the probability of whether the given email is a spam or not spam which is given by, P(spam | w1, w2, w3, w4, w5, …. wn). We can calculate this probability by the Naive Bayes formula as follows,

#### P(spam | w1, w2, w3, w4, w5, …. wn) = ( P(w1, w2, w3, w4, w5, …. Wn | Spam) * P(spam) ) / P(word)

To describe broadly, the implementation of the problem was done in two steps, first where the training set was read, and cleaned and priori probabilities were calculated and the second step, we used the priori probabilities to calculate the posterior probabilities. We start with the training of the classifier using the training set of the email provided. We read all the spam and not spam emails separately and clean only the newline characters. We store the words in the spam and not-spam emails in two dictionaries and calculate the values of P(word|spam) and P(word|notspam).

The interesting part of this part was cleaning of the data, which very strongly infeluenced the accuracy of this part. We did many hit and trial to get the accuracy, first, we only read the body of the email rather than reading the entire email, this resulted in a very poor accuracy (57%). Then we went on to read the complete emails, including the header and the body, and considered only alpha-numeric characters, which gave us the best accuracy (95%). But we did not go ahead ignoring the alpha-numeric, because we believe special characters can influence the probability of an email being a spam. The solution we have implemented takes in consideration everything except the newline characters. This gave us the accuracy of 91%.

The output of this file is a output-file.txt, which has list of emails and their corresponding type (spam / notspam). On console, we print the Accuracy in percentage. In this part of the assignment, reading the large dataset and then generating the count of each word was a time consuming task, and to increase the efficiency, we used a counter function, which increased the speed by large amount.
