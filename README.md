# Automatic Classification of Czech Verbs into Classes and Conjugation Groups
This repository contains codes of rule-based approach to the classification of Czech verbs into 5 commonly used conjugation classes (-e, -ne, -je, -í, -á). It also identifies conjugation groups in the particular classes (-e: nese, bere, maže, peče, tře; -ne: tiskne, mine, začne; -je: kryje, kupuje; -í: prosí, trpí, sází; -á: dělá, kopá). For rurther informati, see e.g. [Morphological classification of Czech verbs on Wikipedia](https://en.wikipedia.org/wiki/Morphological_classification_of_Czech_verbs).

The script requests Czech morphological tagger MorphoDiTa. MorphoDita generates a whole paradigm for given verb. Based on the paradigm, the script identifies verb class and group for the given verb.

Older versions can be found in GitHub releases. `CHANGELOG.txt` contains list of changes in each version. Current (still open) version is this version (2).

**License:** CC-BY-NC-SA 4.0

## Usage
These scripts can be used both as imported in any project, and as shell scripts. Bellow, three examples how to use them are shown.
The input verb (string) should be in infinitive form. Connection to the internet is necessary (the script requests Czech MorphoDiTa to generate a whole paradigm of given verb).

**1. Import as the function to your Python3 project.**
```python
from verbalclass import give_class

word1 = give_class('koupat')
word2 = give_class('krotit')
word3 = give_class('zírat')

print(word1, word2, word3, sep='\n')
```

**2. Read from stdin in the shell pipeline.**
```bash
echo -e 'koupat' | python3 verbalclass.py
echo -e 'krotit' | python3 verbalclass.py
echo -e 'zírat' | python3 verbalclass.py
```

```bash
cat 'path-to-input-file' | python3 verbalclass.py
cat 'path-to-input-file' | python3 verbalclass.py
cat 'path-to-input-file' | python3 verbalclass.py
```

**3. Read from file in shell pipeline.**
```bash
python3 verbalclass.py 'path-to-input-file'
python3 verbalclass.py 'path-to-input-file'
python3 verbalclass.py 'path-to-input-file'
```

## Based on these studies
- HÖFLEROVÁ, Eva. 2010. Průvodce tvaroslovím současné češtiny. Opava: Vade Mecum Bohemiae, pp. 144. ISBN: 978-80-86041-38-4.
- OSOLSOBĚ, Klára. 2017. SLOVESNÁ TŘÍDA. In: Petr Karlík, Marek Nekula, Jana Pleskalová (eds.), CzechEncy - Nový encyklopedický slovník češtiny. URL: https://www.czechency.org/slovnik/SLOVESNÁ TŘÍDA.
- SKŘIVÁNKOVÁ, Jana. 2014. Slovesné třídy a vzory. (online). URL: https://www.mojecestina.cz/article/2014072702-slovesne-tridy-a-vzory.
