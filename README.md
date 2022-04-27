# Classifying DNA Sequences

# Table of Contents
<a id='table_of_contents'></a><br>
[I know absolutely nothing about DNA](#section_1)<br>
[What the heck is a promoter?](#section_2)<br>
[And what the heck are we going to do with a promoter?](#section_3)<br>
[K-mers](#section_4)<br>
[In conclusion, I still know next to nothing about DNA but...](#section_5)<br>
[Datasets and libraries used](#section_6)<br>

<a id='section_1'></a>
# I know absolutely nothing about DNA

I know absolutely nothing about DNA.

Actually, that’s a lie.

I’m vaguely familiar with what DNA is and what a DNA structure looks like.

![DNA sequence](https://imgur.com/oJR9Vxx.jpg)

Yeah, that thingy. 

The point remains though, I’m anything but a DNA expert.

This is why I experienced a not-insignificant amount of trepidation if we’re being kind, or sheer terror, if we’re being honest, when I participated in a hackathon recently to create a model to classify DNA sequences into promotor and non-promoter classes.

<a id='section_2'></a>
# What the heck is a promoter?
[(Back to table of contents)](#table_of_contents)<br>

As the DNA sequence data grows rapidly, the maintenance and annotation of these data are now of utmost importance. 

A promoter is necessary for DNA sequence transcription. Knowing the position of the promoter in the sequence, we can get the starting position of the transcription region that will later be translated into a protein sequence.

If we know which part of a DNA sequence is a promoter sequence, we can use that promoter sequence to keep the rate of translation from DNA into protein under control.

In other words, identifying the promoter is essential for DNA sequence analysis. 

Many methods and tools have been developed for this purpose, and many have achieved high accuracy. 

The goal of this hackathon was to create a model of my own to classify whether a given DNA sequence is a promoter sequence or not.

<a id='section_3'></a>
# And what the heck are we going to do with a promoter?
[(Back to table of contents)](#table_of_contents)<br>

Good question!

I had no earthly idea how I was going to do that either. 

Luckily, we weren’t left completely on our own for the hackathon. 

We received a selection of papers to read from for ideas on how we might proceed. 

Two papers of note caught my attention:
- <a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-9-414#citeas">Pol II promoter prediction using characteristic 4-mer motifs: a machine learning approach </a>by Anwar et al.
- <a href="https://www.cell.com/molecular-therapy-family/nucleic-acids/fulltext/S2162-2531(19)30161-1?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS2162253119301611%3Fshowall%3Dtrue">iProEP: A Computational Predictor for Predicting Promoter </a>by Lai et al.

While I didn’t understand the ins-and-outs of the DNA parts, I most definitely was able to understand the machine learning/NLP parts, and that is how I came across the concept of k-mers.

<a id='section_4'></a>
# K-mers
[(Back to table of contents)](#table_of_contents)<br>

In Bioinformatics, k-mers are subsequences of length k contained within a biological sequence. 

What k-mers help you to do is turn DNA into a language of sorts by creating a group of words of k length.

An example of a DNA sequence and k-mer sequences where k = 3

![An example of a DNA sequence and k-mer sequences where k = 3](https://imgur.com/LwI1bH9.jpg)
<a href="https://towardsdatascience.com/how-to-process-bio-sequences-for-use-in-data-science-7740c199c412">Source</a>

Once you choose your k, you simply divide up the rest of a DNA sequence in chunks of the same length.

Again, for k =3

![Dividing a DNA sequence into chunks of 3](https://imgur.com/HmuWZ8M.jpg)
<a href="https://towardsdatascience.com/how-to-process-bio-sequences-for-use-in-data-science-7740c199c412">Source</a>

Generally speaking, decomposing a sequence into k-size chunks allows for fast and easy string manipulation.

Once you figure that out, it simply becomes a matter of picking a model type (or two or three) and playing around with the parameters to see what gives you the best results.

For me, that was a Convolutional Neural Network that peaked at a validation accuracy score of 90.04%. It did a little worse on the unseen test data that we were given to predict for the hackathon, but that’s nothing a little parameter tuning can’t fix.

<a id='section_5'></a>
# In conclusion, I still know next to nothing about DNA but...
[(Back to table of contents)](#table_of_contents)<br>

Thankfully, that doesn’t prevent me from creating a model that can differentiate between promoter and non-promoter classes. And with a high degree of accuracy too.

Though I can’t help but wonder how much better my models would perform if I knew more about DNA...

<a id='section_6'></a>
# Datasets and libraries used
[(Back to table of contents)](#table_of_contents)<br>

<b>Dataset:</b>
- Custom Hackathon dataset

<b>Libraries:</b> keras, numpy, pandas, sklearn, and tensorflow.
