## CafePlugGuardian Project
### Introduction
CafePlugGuardian is a capstone design project at the Chung-Ang University's Department of Software Engineering.

Please note that we will not be accepting contributions for CafePlugGuardian, as it is a Capstone Design Project.

#### The Goal of CafePlugGuardian Project
1. The pin number allows only cafe customers to use the plug, preventing unauthorized use of the plug.
2. Limit the amount of electricity to restrict customers who use excessive power or stay for long periods of time.
3. By analyzing the current patterns of devices in use, devices not permitted in the cafe, such as smartphones and laptop chargers, are automatically blocked through machine learning.

### Structure of CafePlugGuardian
<img width="80%" src="https://github.com/CAU-Capstone-PPL/CafePlugGuardian-Server/assets/55429793/74940115-831a-49f7-ab9a-3d5dc402089a"/>

### Sub Projects of CafePlugGuardian
* [CafePlugGuardian-Client](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-Client)
    * Cafe Manager App - flutter app
* [CafePlugGuardian-WebClient](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-WebClient)
    * Cafe Customer Web - flutter web
* [CafePlugGuardian-Server](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-Server)
    * Backend server - express.js
* [CafePlugGuardian-Hardware](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-Hardware)
    * SmartPlug embedded system - arduino(tasmota open source)
* [CafePlugGuardian-ML](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-ML)
    * AI model - pytorch, GRU model
* [CafePlugGuardian-ML_Server_Flask](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-ML_Server_Flask)
    * AI server - flask

## CafePlugGuardian-ML
This machine learning was created to learn current patterns. It was written at Google Collab using Python. GRU model was used and Optuna was used for hyper-parameters.

### How to learn current patterns
To learn the current pattern, you need to save the information of the current pattern in an excel file and the column name of the current pattern should be 'current'.

#### Example
![image](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-ML/assets/106421292/d3cd1616-fc0f-4b9c-9138-928b55b1db15)
#### Explain Example
The format should be as shown above and the length of the pattern should be 500 except for the name 'current'.

### How to feat your own data
Using 500 data, you can create 468 data features of length 33 for training. If you want to create features of different lengths, you can change the parameter length in the code.

### How to handle initial hyper parameter
batch_size, Gru_hidden_size, learning_rate, num_epochs can be modified by User. So if you want to feat hyper parameter to your data you can change them. We do not recommend changing 'train_ratio' and 'num_class', but if you want to change them, you can. train_ratio means that 90% of each data feature is randomly assigned as training data and the remaining 10% is assigned as test data. num_class means that it is divided into two classes: allowed and unallowed, and the number '1' is the allowed class.
