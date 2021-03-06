russian-anaphora
================

Ana@phora is a system for automatic pronominal resolution for Russian

The repository is a mess right now. Here are the main moments:
These are rule-based, machine learning and hybrid systems for pronominal anaphora resolution in Russian.

Detailed instructions for rule-based mode are given in the INSTALL file


Machine Learning mode
=====================

To get antecedents for anaphors using only ML, one can use resolute-text.py

```
Usage: resolute-text.py input-text pronouns-list model
```

* input-text may be a file or '-' to read from STDIN. It should be in UTF-8 encoding.
* pronouns-list is a list with all the pronouns with their type. An example is config.txt in the repository.
* model is a file with a stored model.

There is ready-to-use model in the repository: *model.rf.all.dat*: Random Forest classifier trained on approx. 8000 cases.
Note that each model should be accompanied with *model-name.dat.label* file with labels.

Here is the example:
```
echo 'Мальчик, который сидел за столом, был задумчив.' | ./resolute-text.py - config.txt model.rf.all.dat
```

Current status
==============

Currently, this repository is frozen, so it may become incompatible with newer versions of Freeling, plus it contains some bugs.
There is another repository which grew from the same codebase but developed into something different: https://github.com/max-ionov/rucoref. It is still under development and some bugs present here are already fixed there.

Hopefully, the code in this repository will be updated someday in order to fix the bugs.
