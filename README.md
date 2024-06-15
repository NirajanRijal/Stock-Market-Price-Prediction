# Stock-Market-Price-Prediction
Using Normal ML way and by using ML pipeline

Random Forest :
Random forest algorthim is based on collection of decision tree and bagging technique. And Bagging is boostrap aggregation. Bootstrap means - We have multiple of models and we give subset of data to each model. How we provide data? - Random Row sampling, Column/Feature Sampling and Combined Sampling. Then we predict every model with the help of subset of data and then we use aggregation modeling to predict. 

EXAMPLE:

Let's consider a simple dataset of students trying to decide whether to study or play based on two features:
The weather (Sunny or Rainy)
The amount of homework (High or Low)
<img width="463" alt="image" src="https://github.com/NirajanRijal/Stock-Market-Price-Prediction/assets/160163175/9165c319-a6c8-41b0-b4f4-97d7f012509e">

Decision Tree
Is the weather Sunny?
Yes: Ask another question.
No: Study
Is the homework Low?
Yes: Play
No: Study
So, the decision tree looks like this:
       Is Weather Sunny?
       /          \
    Yes            No
   /                \
Is Homework Low?    Study
  /    \
Play   Study

Bagging (Bootstrap Aggregating)
Let’s simulate Bagging by creating multiple decision trees from random samples of the data:
<img width="475" alt="image" src="https://github.com/NirajanRijal/Stock-Market-Price-Prediction/assets/160163175/59e68a64-63e7-429d-91d0-d2563c7589e4">
Decision Tree:
       Is Weather Sunny?
       /          \
    Yes            No
   /                \
Is Homework Low?    Study
  /    \
Play   Study

<img width="465" alt="image" src="https://github.com/NirajanRijal/Stock-Market-Price-Prediction/assets/160163175/c9d17dd2-96a5-442d-99fc-c9bee5ec6c97">
Decision Tree:
       Is Weather Rainy?
       /          \
    Yes            No
 Study           Play

<img width="467" alt="image" src="https://github.com/NirajanRijal/Stock-Market-Price-Prediction/assets/160163175/32e9514b-4a70-4662-aad2-a8c9acc55a69">
Decision Tree:
       Is Weather Rainy?
       /          \
    Yes            No
 Study           Play

Random Forest
Now, let's create a Random Forest by combining these decision trees. Suppose we have a new data point:
Weather |	Homework
Sunny 	|  Low

Each tree will make a prediction:

Tree 1: Play (because weather is Sunny and homework is Low)
Tree 2: Play (because weather is Sunny, which is not Rainy)
Tree 3: Play (because weather is Sunny, which is not Rainy)

Final Decision by Random Forest: Since all trees voted for "Play," the Random Forest predicts "Play."

Visualizing the Process
Decision Trees:
Each tree is created from a different random sample of the data.
Each tree makes decisions based on the subset of the data it was trained on.

Bagging:
By using multiple trees (each a bit different), we reduce the chance that a single bad tree misguides the overall prediction.

Random Forest:
By taking the majority vote from all the trees, we make a more reliable decision.
