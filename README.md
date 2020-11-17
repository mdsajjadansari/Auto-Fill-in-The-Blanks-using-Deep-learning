# Auto-Fill-in-Blanck-using-Deep-learning

We are well familiar with the “fill in the blanks” homework where we choose the most suitable word from the given words and fill the blanks to complete the sentence. Suppose you have an image of the homework (Please refer attached images). And you want to complete the homework (i.e.fill those blanks with a proper word from the box) using image processing and Deep Learning. Isn't it sounds cool!
So, here is an algorithm to do so, 


Input: An image of the “fill the blanks”Home Work..
Output: Completed assignmentin  .txt format.

First,we willextract the given image withthe help of pytesseractandOpenCVAnd Erosionto erode away the noise in the image and Dilationto enlarge image for better detectionAfter which we will get a text file with the extracted text, then we willsavethe keywords and the blankquestion statementsin two different text filesand then we willadd mask in the place of blank lines such that,I read a __________.will convert intoI read a ***mask***.Then we will pass the Keywordfile along with the blankquestion statementsfile to FitBert whichis  a  library  for  using BERT(Google’s  very  large  masked  language  model)to  fill  in  the blank(s) in a section of text from a list of optionswhich will be out keywords.Because of the training  objective  for  BERT  (masked  language  modeling),  it  is  very  good  at  filling  in  the blanks. In fact, that is one of the two tasks that BERT is trained on.

!<>
