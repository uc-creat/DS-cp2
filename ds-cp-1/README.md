# Credit Card Fraud Detection:

## About:

Nowdays, security has become very important. In context of security, Data security have become a mojor 
discussion for all the companies. Companies, tries their best to secure people's data. Even people now, choose those companies
which provide them with the best security system.
We all know that, now almost all of us use our cards for purchasing or paying bills. It becomes very important that, credit card companies are able to 
recognize fraudulent credit card transactions so that customers are not charged for items that they did not pu
So, in this project, we aim to detect or find the probability of fraud transitions.

## Workflow:

The workflow or our approach as a team towards this project was as follows:

1. We needed data, in order to train our credi_card_fraud-detection model. So for that, we surfed the internet and from Kaggle we got a dataset.
   Dataset that we found had 31 features with around 284807 transactions. The dataset was quite imbalanced as fraud transactions were less.
   The datasets contains transactions made by credit cards in September 2013 by european cardholders.
   This dataset presents transactions that occurred in two days, where 492 frauds out of 284,807 transactions.

1. After gathering all the data, from online resources, we analysed the data, and implimented a model that best fit for the data.
   So their were couple of approaches, regarding the selection of the model for the given dataset, like - Logisitc Regression or Isolation Forest.
   
1. After the implimentation of the model, our aim was to project our model on web. Although there are various frameworks of python which allow us to 
   create a webpage through python like, Django and Flask, but to keep it simple, we used one of the python library called streamlit, which is considered to
   be the fastest way to share and build data apps.
   
   ### Steps to follow - to use Streamlit and build app: 
   
   1. Install Streamlit by - 
      ``` py
      
      pip install streamlit
      
      ```
   
   1. Open any python IDE, and create two python files, one for the app and other for the model.
   1. The major task is to connect our model with the web. So, for that, in the python file, which contains our model for the dataset, add the following lines of 
      code - 
      
      ``` py
      
      import pickle
      pickle.dump(linear,open('model.pkl','wb'))
      pickle_out = open("model.pkl","wb")
      pickle.dump(linear, pickle_out)
      pickle_out.close()
      
      ```
      
      Here, model.pkl is the model which is in the write mode -- 'wb'
      
   1. Now, to load this model on our app python file, insert the following lines of code -- 
   
      ``` py
      
      pickle_in = open("model.pkl","rb")
      model=pickle.load(pickle_in)

      ```
      
      Here, model.pkl is being loaded, in the app file, and is in the read mode. And, in the model variable we load the input.
      So, basically we take input from the user and read it here, in this file, and give this input to the model that we created.
      
   1. Now, create a function to take input and return the predicted output from the model.
   1. For, this project we will be focussing only on 3 major parameters, i.e.
     
      1. Time: Number of seconds elapsed between this transaction and the first transaction in the dataset.
      1. Amount: Transaction amount
      1. Class: 1 for fraudulent transactions, 0 otherwise
      
   1. So, we will be creating 3 variables for it, and for 2 variables, i.e -
      Time and Amount, we wil be creating text area in the app and one button for prediction.
      So, basically we will be taking input for time and amount and predict the output, in terms of probability.
      
   1. Because we are only considering only time and amount as the dependent variables, therefore, we used Logistic Regression for the final model, 
      although for better accuracy all the parameters could have been taken if they were properly defined, but for security reasons; apart from amount and time and class, 
      no other feature was clearly defined within the dataset itself. So, we choose to use only time and amount as the only dependent variables.
      
   1. Using HTML, we designed a simple webpage, with 2 input text features and 1 button. 
   
   
   
1. After all the above steps, run the following command in the terminal - 

``` py
streamlit run name_of_your_app-file.py

```
   ![url](https://user-images.githubusercontent.com/60755716/102591564-39492100-4138-11eb-8690-f6eb15dda8ba.png)
   

1. Open that link, you will followed to your app! 
   
   ![app](https://user-images.githubusercontent.com/60755716/102591804-a066d580-4138-11eb-9ae7-b49cc42faf52.png)
   
   ##### Fraud:
    
   ![fraud](https://user-images.githubusercontent.com/60755716/102591903-bd030d80-4138-11eb-83ee-afd5a9297e1f.png)

   ##### No Fraud:
   
   ![No fraud](https://user-images.githubusercontent.com/60755716/102591977-d5732800-4138-11eb-8570-c2e773032da7.png)


