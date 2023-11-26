# Wordinary v2.2.0 : User Manual Book

Version: 2.2.0  [new feature!](#New feature!)

Author: Chris Zuo

E-mail: zuojw21@mails.tsinghua.edu.cn

GitHub Account: [Dr-Left](https://github.com/Dr-Left)   (*Star me!!*)

## Contents

* [Introduction](#Introduction)
  * [Extracting high frequency words](#Extracting high frequency words)
  * [Generating quizzes](#Generating quizzes)
  * [Generating standard pronunciation audios](#Generating standard pronunciation audios)
* [Environment Requirements](#Environment Requirements)
* [Operating Instructions](#Operating Instructions)
  * [Extracting high frequency words](#Extracting high frequency words (tab 1))
  * [Generating quizzes](#Generating quizzes (tab 2))
  * [Generating standard pronunciation audios](#Generating standard pronunciation audios (tab 3))
* [Samples](#Samples)
  * [Extracting high frequency words](#Extracting high frequency words (sample))
  * [Generating quizzes](#Generating quizzes (sample))
  * [Generating standard pronunciation audios](#Generating standard pronunciation audios (sample))
* [Author](#Author)
* [Acknowledgements](#Acknowledgements)

## Introduction

* This software focuses upon **vocabulary building**, which may become a powerful assistant for English teachers. 

* Its latest version(2.1.1, published on 30th Jan. 2022), has **three** main functions：

  1. #### Extracting high frequency words

     ###### Why I developed it

     The ordinary teaching process in Chinese high schools involves a large amount of text-comprehension exercises,  which will expose the students to a great many of words and phrases. Therefore it provides the students with a precious opportunity to expand their vocabulary at the same time as they go through the texts, which means lower time cost than doing vocabulary building and text-comprehension separately. However, in view of the heavy schoolwork the students are bearing, they tend to go through the homework at the maximum speed, which means they always let the new words go, losing the chance to expand their vocabulary.

     Nevertheless, it's a pity to lose such a precious opportunity, which is actually time-saving in the long run. So some responsible English teachers may self-sacrifice to do the work for the students, extracting the key words by going through the text on their own, which is such a heavy and monotonous job! 

     So I developed this function, in order to ease their work. In fact, it's just a piece of cake from the perspective of a computer!

     ###### How it worked

     It's based upon a `Python` script, which goes through the text (txt or doc or docx), counts the frequency of every word, and finally prints them to an excel workbook.

     **It will ONLY take words in the high school syllabus into consideration.** Others are to be ignored.

     It will print the word list **in the same order as they first appear in the text**.

     

  2. #### Generating quizzes

     ###### Why I developed it

     Whatever method is adopted, building vocabulary requires constant repetition. And the teacher would control the rhythm of the task better if they know the students' mastery of the words. So it comes to quizzes. Just as the word extracting job above, typesetting the quizzes is another boring job. So why not employ the computer to do that for us?

     ###### How it worked

     Still `Python`, this time it's a text document. The software will allow you to choose the word range (1 for the first word in the excel), and choose whether you want a quiz asking students the translation of the English words, or the English words of the translation. You can also control the number of the questions in each quiz.

     The sampling process is random. If you choose more than one version, Wordinary will offer you different samples in different orders.

     

  3. #### Generating standard pronunciation audios

     ###### Why I developed it

     Oral English is the weak point of the English education in most schools in China. The root cause is that the students listen too little, and speak too little. However, it's hard to have access to standard pronunciation. (Truly there are plenty of listening materials, but few of them are personalized)

     ###### How it worked

     Still again `Python`, audio segmentations this time. The script will download the audio files from [有道翻译](https://youdao.com/) , and store them for future use. Actually I've already downloaded all the words in the syllabus in advance, which will improve the time efficiency of generating audio clips.



## Environment Requirements

* **Windows**

  Wordinary 2.1.1 can **only** run on **Windows**. Sorry for Linux or Mac users.

* **.NET Framework 4.7.2** or above 

  Windows 10 April 2018 Update, 10.0.17134 (1803) or newer system will preinstall the required running environment.

  Older systems, such as Win7 or Win XP do not include, you have to download and install it by yourself.



## Operating Instructions

To start the program, double click upon the main executing file: `Wordinary 2.1.1.exe`

<img src=".\data\READMESource\main.png" alt="main" style="zoom: 33%;" />

1. #### Extracting high frequency words (tab 1)

   <img src=".\data\READMESource\tab1.png" alt="tab1" style="zoom:33%;" />
   
   

+ Click on the button "选择文件", and choose any text files (.txt or .doc or .docx). Or in a more convenient way, **drag** the text files directly upon the box in the middle. **Multiple files are NOT supported in this new version**.

+ ###### New feature!

   + **The new version allows you to choose the benchmark of the words. Only the words in the benchmark list will be included in the final word frequency list.** This allows you to apply this software to **any application scenarios**, such as preparing for CET-4, 6, TOEFL or GRE.
   + The benchmark workbook only requires that the words and translations stays in different columns, and the first word starts at the second row.
   + If you want to stick to the word list of the older version 2.1.1, just choose the `高考考纲词汇.xlsx` in the `.\source` folder.

+ The box will show the paths of the text files you chose. Click on "提取" to do the extracting work. 
   + A dialog will show up, allowing you to choose the path and the filename you want to save the word list excel workbook as.

+ Click on “保存”, and then a message box will pop up, telling you whether the job is done or not. If it is successful, a file explorer will pop up, selecting the excel workbook the program has just generated.

    

2. #### Generating quizzes (tab 2)

  <img src=".\data\READMESource\tab2.png" alt="tab2" style="zoom: 33%;" />

  + The choosing operation is almost the same as above. The only difference is that when the program successfully read in the excel workbook, it will pop up a message box. **Cautious: Only one excel workbook is accepted at a time.**

  + Choose the count of the versions, the words range, dictation mode, and the count of questions. **Be careful not to put too many questions into one quiz**, otherwise the sheet may *burst*.

  + When the text boxes turned *red*, it means that your input is **invalid**. Check if the range you input is correct. The upper bound should be under the total counts of the word list. Meanwhile, the counts of questions should be no more than the length of the word range. 

  + When all the inputs are valid, the ”生成“ button is activated. *(In other words, if it is not enabled, your inputs are invalid)* Click on it, and you can choose the *bin path* in a dialog. The *bin path* means the directory into which the program is gonna put the quizzes. 

  + When it's all done, also a file explorer will pop up, selecting one of the quizzes, the answers are generated by the way.

  + The quizzes' filename contains the word list name, the version number, the date and the time.

    Sample: `默写纸_英语高频词_版本2_2022-01-30 11.49.docx` 

  + **About the excel workbook's format**: the English words should be in a column, the translation should be in another. The first row is for the title, the main contents starts from the second row. **That's it. As for which column they should stay, it doesn't matter at all.**

  

3. #### Generating standard pronunciation audios (tab 3)

   <img src=".\data\READMESource\tab3.png" alt="tab3" style="zoom:33%;" />
   
   + The choosing operation is almost the same as above. **Only one excel workbook is accepted at a time.**
   
   + Input the word range.
   
   + Pick the repeat times.
   
   + Pick the interval.
   
   + Click on "生成", choose a bin path. Then it will generate a `.wav` file. 
   
   + The excel workbook's format is the same as above.
   
     **PS: It may cause a little time. If the program looks as if it's not responding, just wait patiently.** *If you chose too many words, and the words are not cached before, it may take very long to generate, even break down. So bear in mind that never do it to a mountain of words!*

## Samples

Here you may see the result of the sample text. The sample text is in the `.\source\sample.docx`

1. #### Extracting high frequency words (sample)

   <img src=".\data\READMESource\sample1.png" alt="sample1" style="zoom:33%;" />

2. #### Generating quizzes (sample)

   <img src=".\data\READMESource\sample2.png" alt="sample2" style="zoom: 30%;" />

   <img src=".\data\READMESource\sample2_2.png" alt="sample2_2" style="zoom:25%;" />

3. #### Generating standard pronunciation audios (sample)

   <img src=".\data\READMESource\sample3.png" alt="sample3" style="zoom:25%;" />

## Author

Author: Chris Zuo

E-mail: zuojw21@mails.tsinghua.edu.cn

GitHub Account: [Dr-Left](https://github.com/Dr-Left)   (*Star me!!*)

## Acknowledgements

I've forked a piece of script and did some change in the third function. The author might be QQ: 403096966. Thanks a lot. This function should not work but for him/her.
