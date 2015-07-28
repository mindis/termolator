# Termolator - Chinese Terminology Extraction and TJet

This package contains NYU's Chinese terminology extraction system and a Jet wrapper to support English Terminology extraction. The system is released under the Apache License, except for the files in sampleRDG/ and sampleBackground/ directories.

Files in sampleRDG/ and sampleBackground/ are taken from Wikipedia and licensed under [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) License.

## Chinese Terminology Extraction

To perform Chinese Terminology extraction: 

    ./run_cn.sh IN_DOMAIN_FILELIST OUT_OF_DOMAIN_FILELIST OUTPUT_FILE

* IN_DOMAIN_FILELIST: List of in-domain files generated by a Chinese noun chunker, in CONLL format. The CONLL fomrat we use assumes one word per line. Each line has four fields, delimited by the tab character. Field 1: Word; Field 2: Word; Field 3: Part-of-speech tag; Field 4: BIO tag for NP (B-NP, I-NP, or O).

* OUT_OF_DOMAIN_FILELIST: List of background files generated by a Chinese noun chunker, in CONLL format

* OUTPUT_FILE: Name of the output file. The output file will be	a ranked list of terminologies. 

## Building the System

We build the system by maven. In the FuseJet directory, run:

    mvn package

The produced jar file is the FuseJet.jar used in the Chinese system, as well as the TJet.jar in the English system. 

## Using the Word Segmenter and Part-of-Speech Tagger

We provide a Chinese word segmenter and part-of-speech tagger, by courtesy of the Chinese Natural Language Processing Group, Brandeis University. It is available at:

(URL to be revealed)

The Termolator License terms do __NOT__ cover the word segmenter and part-of-speech tagger. Please find usage and license terms for the Brandeis tagger in Readme.txt from the zip package.

We also provide a Python3 script to convert the word segmenter/pos tagger output into the CoNLL format that our term extraction system requires. Usage:

    ./pos2conll.py POS_OUTPUT_DIR CONLL_OUTPUT_DIR CONLL_FILE_LIST

where POS_OUTPUT_DIR is the output directory of the Brandeis tagger, CONLL_OUTPUT_DIR is the directory that we save the output files in CoNLL format, and 

## Authors

Termolator is developed by Adam Meyers, Yifan He, Zachary Glass and Shasha Liao.

The Java code for the Chinese terminology extractor and the English part-of-speech tagger in this git repository is developed by Yifan He and Shasha Liao.