# Learning Python
* There are many ways to begin Python. Below are some of my favorites.
  * Codecademy Python: https://www.codecademy.com/learn/learn-python
  * Think Python: https://greenteapress.com/wp/think-python/
* If you want to study advanced Python, this book would be a good choice.
  * Effective Python: https://effectivepython.com/
    * In Korean, 파이썬 코딩의 기술: http://www.gilbut.co.kr/book/bookView.aspx?bookcode=BN001430

# Knowing Packages in Low-level
### In my scenario,
* I tried to run a searchlight analysis with SVR(support vector regressor). 
  * Because, my task outputs of experiments are numerical values (not categorical).
* I just put 'svr' instead of 'svc' in searchlight instance and run.
* But in statistical tests, suddenly I was not sure what `searchlight.scores_` is in case of 'svr'.
  * As you know, SVR is a regressor, not a classifier.
* So I searched the NiLearn documents, but it didn't come out.
* Then I went to NiLearn github and found the searchlight code.
  * Link: https://github.com/nilearn/nilearn/blob/master/nilearn/decoding/searchlight.py
* OK, they use outputs of `cross_val_score`. I went to sklearn.
  * Link: https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/model_selection/_validation.py
* I could found they are calling `check_scoring` function, and the function just returns a `score` method if the estimator has.
* After I checked 'svr' of a searchlight is an SVR instance of Sklearn, I saw the Sklearn document finally. It returns the coefficient of R-squared.
  * Link: http://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html

### In general,
* Python packages are usually easy to see because they have a github repository.
* It's helpful for me to look up codes when there is something ambiguity.

# Miscellaneous Tips
* Jupyter Notebook can open a terminal. No need ssh.
* Python is a general programming language, so there are differences between MATLAB or R.
  * Array indexes bigin at 0, not 1.
* 