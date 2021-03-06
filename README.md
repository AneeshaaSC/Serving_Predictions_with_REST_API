# Serving_Predictions_with_REST_API

## Technical Exercise: The Tomato Classification Problem

Our Machine Learning research team has designed and trained a Machine Learning model that is able to successfully
categorize 3 different types of tomatoes based on 4 features that represent shape and form ratios.

There are hundreds of tomatoes varieties but the model only handles three types so far:

- Plum Tomatoes
- Cherry Tomatoes
- BeefSteak Tomatoes

Machine Learning research team presented the model to our product manager who was very impressed with the result. 
Hence, she would like to use this model in a new product feature where ingredients are auto populated when users create
new recipes. 

## Objective

Machine Learning team has provide you with this code base. 
Your task is to turn this into a production-ready service to serve predictions from the model.

The only **requirement** from product is that the predictions **should be served through a REST api**.

You are the Machine Learning Engineer, therefore, you must come up with any extra requirements for this
service to be considered "production ready". We are not asking you to implement all
of your considerations, but only once you consider the most crucial. 
Any other requirement that you identify but don't have time to implement or improvements proposed
to your current solution you can note down in [`IMPROVEMENTS.md`](./IMPROVEMENTS.md).

If you managed to get a running solution, write down some instructions in [`RUN_INSTRUCTIONS.md`](./RUN_INSTRUCTIONS.md)

## Guidance

- **Prioritise demonstrating an overall solution**, rather than devoting too much time to fixing
  little problems at runtime. In our evaluation, we are not focused on the code
  running correctly. We are more interested to see an end to end solution/scaffold focusing in aspects
  like code design, flexibility, extensibility, maintainability, etc.
- **Treat the codebase as your own**. Do not feel constrained in parts of the repository you can edit.
  You are welcome to make any changes to the code (or tooling or anything else) that you see is a
  priority.
- You can use **any open-source frameworks or tools** which would help you achieving the objective, but the main language should be Python. 


## Model trained

The model chosen by the researchers to solve the Tomatoes classification is a Neural Network implemented with Tensorflow 2.
Trained nodel is saved in [`model`](./model) folder.

Once the model is trained and fed an unlabeled example, it yields three predictions: the likelihood that this tomato is the given type. E.g:

If the prediction response from the model is [0.02, 0.95, 0.03] means:
- 2% for plum type
- 95% for cherry type
- 3% for beefsteak type  

# The Data

Although you should not need to re-train the model for this task, the dataset used to train the model is a plain text
file that stores tabular data formatted as comma-separated values (CSV). 
Here is an example of the first 5 rows in the dataset:

```bash
!head -n5 {train_dataset}

120,4,plum,cherry,beefsteak
6.4,2.8,5.6,2.2,2
5.0,2.3,3.3,1.0,1
4.9,2.5,4.5,1.7,2
4.9,3.1,1.5,0.1,0
```

From this view of the dataset, notice the following:

The first line is a header containing information about the dataset:
There are 120 total examples. Each example has four features and one of three possible label names.
Subsequent rows are data records, one example per line, where:
The first four fields are features: these are the characteristics of an example. Here, the fields hold float numbers representing shape ratios measurements.
The last column is the label: this is the value we want to predict. For this dataset, it's an integer value of 0, 1, or 2 that corresponds to a tomato type.

# Submission
This **private repository** was created for you. Your solution will be assessed based on the last commit in the PR with your solution (we encourage to create a draft PR immediatly). An incremental Git commit history is encouraged but not required. Let us know when you fininshed and your solution is ready to get assessed (Don't forget to push your final commit).

# What I did
Tried a few methods: using TF serving natively, using docker(after installing docker CE). 

# What they said I'm missing
Configurations, tests and logging
