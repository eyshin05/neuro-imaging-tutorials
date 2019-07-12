# Learning Python
* There are many ways to begin Python. Below are some of my favorites.
  * **Codecademy Python**: https://www.codecademy.com/learn/learn-python
  * **Think Python**: https://greenteapress.com/wp/think-python/
* If you want to study advanced Python, this book would be a good choice.
  * **Effective Python**: https://effectivepython.com/
    * In Korean, 파이썬 코딩의 기술: http://www.gilbut.co.kr/book/bookView.aspx?bookcode=BN001430

# Digging Packages
### In my scenario,
* I tried to run a **searchlight analysis with SVR**(support vector regressor). 
  * Because my task outputs of experiments are numerical values (not categorical).
* I just put 'svr' instead of 'svc' in searchlight instance and run.
* However, in statistical tests, suddenly I was not sure what `searchlight.scores_` is in case of 'svr'.
  * As you know, SVR is a regressor, not a classifier. So it's not a classification accuracy.
* So I searched the **NiLearn documents**, but it didn't come out.
* Then I went to **NiLearn github** and found the searchlight code.
  * Link: https://github.com/nilearn/nilearn/blob/master/nilearn/decoding/searchlight.py
* OK, they use outputs of `cross_val_score`. I went to **skLearn github**.
  * Link: https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/model_selection/_validation.py
* I could found they are calling `check_scoring` function, and the function returns a `score` method if the estimator has.
* After I checked 'svr' of a searchlight is an SVR instance of Sklearn, I saw the **skLearn documents** finally. It returns **the coefficient of R-squared**.
  * Link: http://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html

### In general,
* Python packages are usually easy to see because they have a github repository.
* It's helpful for me to look up codes when there is something ambiguity.

# Miscellaneous Tips
* Jupyter Notebook can **open a terminal**. No need ssh.
* Python is a general programming language, so there are differences between MATLAB or R.
  * Array indexes begin at 0, not 1.
* Some packages use python2.7.
  * If you must use these packages, consider setting **virtual environment** up with venv, virtualenv, pyenv, or anaconda.
* If your OS is Windows, I recommend you to use **Anaconda**.
  * See here: https://www.anaconda.com/download/#windows
* There are other Python IDEs.
  * Jupyter notebook is one of them.
    * It works interactively.
    * Good for **exploratory data analysis**(EDA).
    * It makes easy to visualize graphs, share codes, report results and doing trials.
  * PyCharm is also a recommendable IDE.
    * Good for scripting modules.
    * It makes easy to debugging line by line and constructing a big project containing many files.
    * Also, PyCharm Pro provides access to remote servers. If you have student e-mail account, you might be able to use a free PyCharm Pro version.
