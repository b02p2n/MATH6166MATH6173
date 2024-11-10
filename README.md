java c
MATH6166/MATH6173 – Coursework 1 
Instructions for Coursework 
1.  This coursework assignment is worth 80% of the overall mark for the module MATH6166, and 40% of the overall mark for the module MATH6173.
2.  The deadline is 15:00 on Thursday 21st November 2024, and your completed work must be submitted electronically via Blackboard.
3.  All  of your  answers  to  the  coursework  are  to  be  written  in  the  R  Markdown  file  “Coursework- template.Rmd”, which can be found under the Coursework heading in the Assessment panel on Black- board. Download this file and write all of your answers to the coursework questions in this file only.
4.  The file “Coursework-template.Rmd” is a template answer sheet that is used to write your answers to all of the coursework questions. This is the only file that you need to use to write down your answers. You must not delete any of the content from this file; for example, do not change the names or options of code chunks, or change the layout of the file.  The layout of the file has been designed specifically so that the correctness of the R functions that you write can be systematically assessed.
5. You must write all of your coding answers to each question in the corresponding empty R Markdown code chunk within the file.  Do not create any new code chunks.  Each code chunk has a name that matches the corresponding coursework question, and there are comments that signpost where to provide an answer for a specific question.  For example, for  Question 1 (a), you will see the comment Write your  code  for  Q1  (a)  in  the  code  chunk  below:  and below this comment will be a code chunk with the label Q1a. Any changes you make outside of the designated code chunks will likely result in your assessment not being able to be marked. All the coding answers must be carried out through R commands (do not use comments to give your answers).
6. Where relevant,  report  your  answers in the designated section below the R code chunks for each question in the R Markdown file.  For example, for Question 1 (a), you will see the comment Report your  answer  for  Q1  (a)  below:, below which you can write your answer in standard R Markdown formatting.
7. When writing an R function, the
•  function name,
•  argument names and data type, and
• output names and data typemust be exactly the same as those specified in the questions; otherwise a heavy penalty will be applied. Please note that uppercase and lowercase of the same alphabet are not the same character, so if the question asks to write a function/argument called, apple, but a function/argument called applE is presented in your answer, then that would be wrong.
8. Your submission must consist of exactly two files; the R Markdown file and its associated html file that is created by knitting/rendering the R Markdown file. The R Markdown file is the “Coursework- template.Rmd” file with your answers added in the appropriate places.   Using  this  file, you must generate a html output file using the knit functionality in R Markdown, and submit this along with the R Markdown file.
9. Your R Markdown file must be renamed, and have the file name .Rmd. For example, if your student ID is 12345678, then your script. must have the file name 12345678.Rmd.
10.  Similarly, the associated html file should be named .html.  For example, if your student ID is 12345678, then your html file must have the file name 12345678.html.  (This should be correctly named by default provided that you have named the R Markdown file correctly.)
11.  Missing  R code will be penalised.   Please  ensure  the  submitted  files  have  the  correct  file  format; otherwise it cannot be marked. Note that an R Markdown file is a different format to an R script. file.
12. Your entire R Markdown file must be reproducible and run without any errors.
13. You must informatively comment your R code where appropriate.
14.  Unless specifically stated otherwise, you do not have to include error handling in your code.
15.  Ensure  that  all  required  plots  are  informative,   including  the  use  of  appropriate  plotting  areas, points/lines sizes and colours, as well as including meaningful labels, titles and legends.
16.  Except for ggplot2, you must not load any add-on packages, i.e., using functions library or require etc.
17.  All data files required to complete the Coursework can be downloaded from Blackboard, under the Coursework panel.
18.  To help you with the completion of the Coursework, there is an example Coursework question and related files on Blackboard for reference. You can find the following files under the Coursework Example Question panel:
•  An example Coursework question, in the file Coursework-example.pdf,
•  A template R Markdown file Coursework-example-template .Rmd in which to write your answers to the example Coursework question,
•  A model solution R Markdown file Coursework-example-solutions.Rmd, which contains solu- tions to the Coursework example question and shows you the way you are expected to fill in the Coursework-example-template .Rmd file with your answers.
•  The model solution output html file Coursework-example-solutions.html, which is simply the rendered output of the Coursework-example-solutions .Rmd file.
•  all-ad-sales .txt and youtube-ad-sales .txt: the data files needed for the example question.
19. When asked to import a data file into your R workspace, you should first set the working directory to the location of the file on your local computer using the command setwd, and then read the file in using the appropriate R command  (e.g. read .csv or read.table).  You should set the working directory every time you have to import a data file. For an example of how to do this, see Question 1 (a) in the example Coursework solutions file.
20.  The  standard  Faculty rules on  late  submissions  apply:   for  every  day,  or  part  of a  day,  that  the coursework is late, the mark will be reduced by a factor of 10%.  No credit will be given for work which is more than five days late.
21.  All  coursework  must  be  carried  out independently,  without  collaborating  with  other  students. You  are  reminded  of  the  University’s  Academic  Responsibility  and   Conduct  Policy,   see https: //www.southampton.ac.uk/about/governance/regulations-policies/student-regulations/academic-responsibility-conduct. 
22. In the interests of fairness,  queries which relate directly to the coursework must be made via the Coursework Discussion Forum on Blackboard.  This ensures that everybody has access to the same information.
Total marks available:  80
Question 1: Exploratory analysis of Melbourne house price data set 
[21 marks]
The data set in the file melbourne_house_price .csv contains information on properties sold in Melbourne, Australia in 2016 and 2017. The data consists of the following seven columns:
1.  Suburb: a character variable, giving the name of the Melbourne suburb the property is in.
2. Address: a character variable, giving the street address of the property.
3. Rooms: a numeric variable, giving the number of bedrooms in the property.
4. Type:  a character variable, giving the type of the property.   This  can be either  "h"  (house),  "t" (townhouse), or "u" (unit or duplex).
5. Price: a numeric variable, giving the price that the property was sold for (in AU$).
6. BuildingArea: a numeric variable, giving the area (in m2 ) of the property.
7. YearBuilt: a numeric variable, giving the year the property was built.Not all of the entries in the melbourne_house_price .csv data set file have been observed.  Some values in the BuildingArea and YearBuilt columns are missing, and these are represented by the value NA. For example, in the YearBuilt column, the 3rd entry has been observed, and has value 2008. However, the 1st and 2nd entries are missing, and have value NA.
(a)  [2 marks] Import the data set from the melbourne_house_prices .csv file into the R workspace in a variable named house_data. How many properties in the data set have more than 4 bedrooms?  Store this in a variable named more4_rooms.
(b)  [2  marks]  Convert the  Suburb,  Rooms, and Type columns into factor variables.   How many unique
categories are there for the Suburb variable? Store the number in a variable named num_suburbs.
(c)  [2 marks] Calculate the median building area for properties built in the year 1980 or before.  Make sure to remove any missing data (from both variables) from your calculations.  Store it in a variable named median_area.
(d)  [2 marks] What is the address of the most expensive townhouse sold in the Brunswick suburb?  Store this in a variable named brunswick_t_max_address.
(e)  [3 marks] Create a new column, named FullyObserved, that contains the value TRUE if all observations in a single row have been observed, and FALSE otherwise.  What is the name of the column with the most missing values? Store it in a variable named col_miss.
(f)  [3 marks]  Create a side-by-side box plot of Price for the three Suburb values  "Bentleigh  East", "Preston", and "Reservoir".
(g)  [3 marks] On a single figure, plot two histograms of the BuildingArea variable on the probability scale, with one histogram for properties with 1 bedroom, and the other for properties with 4 bedrooms, using x-axis limits of 0 and 300.
Hint: you can add one histogram plot to another by supplying the argument add  =  TRUE to the hist() function.
(h)  [4  marks] For the columns containing numeric variables, one approach to dealing with NA values is to replace the NA values with the mean value of the observed variables in the column according to some rule.Replace NA values in the BuildingArea variable with the mean value of the BuildingArea values that have the same number of Rooms variable. If all data for a given number of b代 写MATH6166/MATH6173 – Coursework 1
代做程序编程语言edrooms is missing, then use the mean of all of the BuildingArea values instead.  For example, observation  1 has an NA value in the BuildingArea column, and 2 in the Rooms column, so the NA value should be replaced by the mean BuildingArea of all 2 bedroom properties.
Question 2:  Classifying data using k-nearest neighbours 
[27 marks]Scientists use measurements collected from radar signals in order to detect objects in the Earth’s ionosphere (a region of the Earth’s atmosphere stretching from a height of about 50km to more than 1000km).  The scientists record data consisting of the radar measurements from a signal sent to a specific target location in the Earth’s ionosphere.Given new radar readings from a target location in the ionosphere, the scientists are interested in classifying whether or not the radar measurements give evidence of an object being present at that location.  Each data observation therefore comes from one of two classes, 1 or 2, with 1 representing an object being present, and 2 representing no object being present. The scientists aim to predict, given a new observation of radar measurements, if the observation should be classified as coming from class 1 (object detected) or class 2 (no object detected).Mathematically, suppose we observe p-dimensional data that comes from one of two classes, 1 or 2.  The scientists have access to a training data set of n pairs of data points (x1 , y1 ), (x2 , y2 ), . . . , (xn , yn ), where for each 1 ≤ i ≤ n, xi  ∈ Rp  and yi   ∈ {1, 2}.  The value yi  is the class label of xi , so that in the training data set, the class membership of each observation is known.
The  k-nearest  neighbours  algorithm  can  be  used  to  predict  which  class  a  new  observation x be- longs  to.     For  a  given  distance  function   f (·, ·)   :   Rp   × Rp    →   [0, ∞ ),   we  order  the  data  points  as(x(1) , y(1) ), (x(2) , y(2) ), . . . , (x(n), y(n)) according to the distance of the point to x with respect to f , so thatf (x(1), x) ≤ f (x(2), x) ≤ · · · ≤ f (x(n), x).                                                 (1)
Then, the predicted class of x, , is given by the majority class of the k-nearest data points (neighbours) to x:
where I is the indicator function.
(a)  [5 marks]  Write  a  function,   called  classify_point,   that  classifies  a  new  observation x ac- cording  to  the k-nearest  neighbours  rule  in  Equation   (2)  given  a  set  of  training  observations (x1 , y1 ), (x2 , y2 ), . . . , (xn , yn ) and a user-specified distance function f. The classify_point function
should have the following features: Arguments:
1. x: a numeric vector of length p, giving the new observation x ∈ Rp  that is to be classified.
2. training_data:  a numeric matrix with n columns and p + 1 rows, consisting of training data. Each column corresponds to an observation (xi , yi ).  The first p rows contain the p variables from the n vectors x1 , . . . , xn. The last row contains entries equal to either 1 or 2, that depicts which of the two classes the observation belongs to.
3. k: a single numeric value, a positive integer k representing how many nearest neighbours to use.
4.  dist_func:  a function object, giving the distance function f to use as in Equation  (1), that will be provided by the user.  You do not need to create your own distance function, but you should assume that dist_func has two arguments, a and b, representing the two observations whose distance is being computed.  For example, for 1-dimensional data, one possible choice is dist_func  =  function(a,  b){abs(a  -  b)}, the absolute value of the difference between a and b.
Computation:
The function should compute the ordered distances with respect to a new observation x as given in Equation (1). Then, the function should compute the predicted class of x according to Equation (2).
If there is no majority class, i.e. if k is an even number and Σi(k)=1 I(y(i)  = 1) = Σi(k)=1 I(y(i)  = 2) = k/2, then x should be predicted as belonging to the class of the (k + 1)-th nearest neighbour instead.
Return:
• predicted_class: a single numeric value, equal to either 1 or 2, giving the predicted class of the new observation x.
(b)  [2  marks]  Write  a  function,  called  classify_data,  that  classifies  a  new  set  of  m  observations x(1) , x(2) . . . , x(m)   according to the  k-nearest  neighbours  rule  given  a  set  of training  observations (x1 , y1 ), (x2 , y2 ), . . . , (xn , yn ).   Your function should call the function you wrote in part  (a) where appropriate. The classify_data function should have the following features: Arguments: 
1. test_data: a numeric matrix with m columns and p rows, giving the new observations {x(i) 
that are to be classified.
2. training_data:  a numeric matrix with n columns and p + 1 rows, consisting of training data. The argument has the same specifications as in part (a).
3. k: a single numeric value, a positive integer k representing how many nearest neighbours to use. The argument has the same specifications as in part (a).
4.  dist_func:  a  function object, giving the distance function  f to use as in Equation  (1).   The argument has the same specifications as in part (a).
Computation:
The function should classify each of the m observations in test_data as belonging to the class 1 or 2, using the classify_obs function that you wrote in part (a).
Return:
• predicted_classes: a numeric vector of length m, with entries equal to either 1 or 2, whose i-th entry corresponds to the predicted class (i)  of the new observation x(i) .
(c)  [4 marks] Import the data sets ion_train .txt and ion_test .txt into your R workspace into vari- ables named ion_train and ion_test respectively.  Using the training data set, compute the pre- dicted classes from the test data set for k  ∈  {1, 2, . . . , 13}, using the Euclidean distance f (a, b) =√Σi(p)=1 (ai − bi )2 .  Store the predicted classes in a data frame. object predicted_classes of dimen-
sions m × 13, where m is the number of new observations to predict, and where the columns consist of the predictions for the 13 different values of k.
(d)  [3 marks] By comparing the predicted classes (1) , (2) , . . . , (m)  to the true classes y (1) , y (2) , . . . , y (m) , a 2 × 2 confusion matrix C can be computed with entries given by:
1 ≤ i, j ≤ 2. (3)Write a function, called  calc_conf_mat, that calculates the confusion matrix C for a given set of predicted classes (1) , (2) , . . . , (m)  and true classes y (1) , y (2) , . . . , y (m) .  The calc_conf_mat function should have the following features:
Arguments:
1. predicted_classes:  a numeric vector of length m, giving the values of the predicted classes (1) , (2) , . . . , (m) .
2. true_classes:     a   numeric   vector   of  length   m,   giving   the   values   of   the   true   classes y (1) , y (2) , . . . , y (m) .
Computation:
The function should compute the 2×2 confusion matrix C given in Equation (3). The confusion matrix should have meaningful row and column names distinguishing the entries of the matrix.
Return:
conf_mat: a matrix object, giving the 2 × 2 confusion matrix C given in Equation (3).
(e)  [3 marks] Further analysis by the scientists finds that the first  15 observations (i.e. those in columns 1–15) in the ion_test data set belong to class 1, whilst the last 15 observations (those in columns 16–30) belong to class 2.  Using the calc_conf_mat function you wrote in part (d), plot the proportion of incorrectly classified data points for the classifications computed in part (c) over the given range of k ∈ {1, 2, . . . , 13}.
(f)  [3 marks] Run the classify_data function on the test data set with k = 13 for the following 3 distance functions:



Which  distance  function  yields  the  highest  proportion  of  correctly  classified  data  points  for  the ion_test data? Store the name of the function ( "f1", "f2", or "f3") in a variable called best_func.
(g)  [4 marks] Using the predicted classes from the classification in part (f) that yielded the highest pro- portion of correctly classified points, plot dimensions 6 and 7 of the ion_test data on a scatter plot, with the two (true) classes distinguished from one another by colour, and with incorrectly classified points given by cross (x) symbols.
Hint:  Several of the data points have identical values.  To better visualise the data, use the  jitter function to add random noise to the data.
(h)  [3 marks] In this question, you will write a function, called classify_data2, that improves upon the function classify_data that you wrote in part (b), by including checks to ensure that some of the arguments passed to the function satisfy certain requirements.  First, copy and paste the code you wrote for part (b) into your answer for part (h), and rename the function name to classify_data2 in part (h).
The function classify_data2 should check that the arguments satisfy the following three require- ments:
1.  The last row of training_data should only contain numeric values equal to 1 or 2.
2.  The dimension of observations in test_data and training_data match up, i.e. the number of rows of test_data should be 1 less than the number of rows of training_data.
3.  The argument dist_func should be a function object.
If invalid inputs are passed to this function, it should stop prematurely by using the appropriate R function and print out the associated relevant error message exactly as written below:
1.  Last  row  of  training_data  should  only  contain  numeric  values  equal  to  1  or  2 .
2. Dimensions  of  test_data  and  training_data  do  not  agree .
3. Argument  dist_func  should  be  a  function  object .
For example, if requirement 2 is not satisfied, then the function should stop and print the error message 2.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
