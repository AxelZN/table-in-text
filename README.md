# table-in-text

## Description
Script for identifying tables in plain text documents and saving them in output files.
The model was trained using SVM classifier on a dataset of 150 articles containing 410 tables and 45406 non-table sentences.


## CoreNLP Preprocessing
This classifier works with Part-of-speech tagged text documents.
You can do this by using Standford CoreNLP in the following way:
 
The inputs files of this code are generated by Stanford Core NLP, for details of installation visit: https://stanfordnlp.github.io/CoreNLP/index.html
Once the program is installed, run the following comands inside table-in-text directory: 
```
export CLASSPATH=$CLASSPATH:/path/to/stanford-corenlp-4.2.0/*:
```
```
for file in - path/files/to_tokenize/ 
do
java -mx3g edu.stanford.nlp.pipeline.StanfordCoreNLP -annotators tokenize,ssplit,pos,lemma -outputFormat json -outputDirectory NLP/TestJsonNLP_Files/ -file "${file}" ;
done                            
```

The processed results include

## Run the classifier

```
python3 Table_Identifier.py -iJ '../path/to/JsonCoreNLP_Files/'
```

## Requirements

Our classifier was tested using Python 3.8 on Windows and macOS. Following Python 3.8 libraries are required.
```
joblib
argparse
pandas
sklearn
json 
```

## Developers
Carlos Francisco Méndez Cruz\
Dante Torres Sepúlveda\
Axel Zagal Norman\
Joel Rodríguez Herrera

## Contact
Carlos Méndez: cmendezc at ccg.unam.mx\
Dante Torres: dtorres@lcg.unam.mx\
Axel Zagal: azagal@lcg.unam.mx\
Joel Rodríguez: joelrh@lcg.unam.mx
