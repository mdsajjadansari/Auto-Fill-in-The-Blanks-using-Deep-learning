# Auto Fill-in-Blanck using Deep learning & FitBert

We are well familiar with the “fill in the blanks” homework where we choose the most suitable word from the given words and fill the blanks to complete the sentence. Suppose we have an image of the homework (Please refer attached images sample.jpeg). And you want to complete the homework (i.e.fill those blanks with a proper word from the keywords) using image processing and Deep Learning. doesn't it sounds cool!
So, here is an something to do so, 

<p>First,we will extract the given image with the help of pytesseract and OpenCV And erode away the noise in the image and enlarge image for better detection. After which we will get a text file with the extracted text, then we will save the keywords and the blank question statements in two different text file sand then we will add mask in the place of blank lines such that, </p>
<p><code>I read a __________.</code> will change to <code>I read a ***mask***.</code></p>
<p> Then we will pass the Keyword file along with the blank question statements file to FitBert which is  a  library  for  using BERT(Google’s  very  large  masked  language  model)to  fill  in  the blank(s) in a section of text from a list of options which will be our keywords.Because of the training  objective  for  BERT  (masked  language  modeling),  it  is  very  good  at  filling  in  the blanks. In fact, that is one of the two tasks that BERT is trained on.</p>

## Flowchat<image src=Flowchart.png></image>

## Objective 
<p> <b>Input:</b> An image of the “fill the blanks”Home Work..</p>
<p> <b>Output:</b> Completed assignmentin  .txt format. </p>

## Library & Language used:
Here I have used Following Libraries:
* FitBert- <i> for  using BERT </i> 
* Pillow- <i> For reading the input file </i>
* numpy- <i>For custom preprocessing </i>
* argparse- <i>For parsing the arguments </i>
* opencv-python- <i> For preprocessing </i>
* pytesseract-<i> For converting image to text </i>
* Regular Expression (re)- <i> Forwritingextracted stringin text file.</i>

Here I have used Following Languages:
* Python

## Instruction for Execution
1. First Run the <code>pyTest.py</code> file with the command : 
 <code>python3 pyTest.py -i {Location/image.jpg} </code>
2. It will convert the image.jpeg file into text and store it in result.txt file.
3. From the result.txt copy the statements (statement.txt) and Keywords (options.txt) in two different text files.
4. Now in <code>statements.txt</code> file replace the blank places with ***mask***.
5. Now open GoColab and open the Notbook <code>Final.ipyb</code> file.
6. Now Upload the <code>statements.txt</code> and <code>options.txt</code> file in that same directory so that it can be used for the code.
7. After running all the cells of Notebook it will produce a <code>outt.txt</code> with will out final distination where all the balnks ***mask*** will be filled with suitable words from keywords.


## SUGGESTION
Here, It takes an image and extract text from it then find the blanks and then puts a suitableword in that place from given keywords, I have used FitBert here which takes only single string at a time and puts the words from keywords on the basis of its ranking because There  is  no  way  to  do  this  in  a  fully  automated  fashion  without  further constraints. At least not with today’s AI.
For two reasons:
1. It is too hard to distinguishthe blank underline and the page borders because both are the horizontal lines.
2. Keywordsare  therein  abox and  alsowithoutbox without  any particularspecification.
3. There  is  no  computational  system  (yet)  that  is  capable  of  determiningallpossible meaning representations of an arbitrary input sentence.
4. We  do  not  have  a  computational  system  at  hand  (yet)  that  can  model  and representallpossible  contexts,  especially  when  information  integration, possibly from multiple modalities, is required.

The  key  challenge  is  that  the  meaning  of  a  sentence  is  strongly  context  dependent.  A semantically acceptable sentence is one whose meaning representation is logically compatible with that of its context.In future it should be better is FitBert developers allows to take more than one masked string but then still we have to put keywords and statements individually or put a condition for the keywords like “keywords must need to be bold” ot some other condition to identify it is differently from the statement.

<i> Author : Md Sajjad Ansari </i>
