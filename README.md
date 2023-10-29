# Network-Traffic-Classification
Deep Learning Based Optimal Traffic Classification Model for Modern Wireless Networks.

Network Traffic:
Amount of data moving across a computer network at any given time. 
Broken down into data packets and sent over a network.

Network Traffic Classification:
Aims to recognize different applications or traffic types.
Essential management with speedy growth of high speed internet.
Accurate classification is crucial to the Internet Service providers(ISPs)
For providing good Qos, Anamoly detection, pricing.

Encryption of Traffic:
Security protocols like HTTPS, SSH, SSL will encrypt internet traffic.
Encrypts user sensitive information from online attacks.
Easier for the Internet Service Providers in troubleshooting and managing the network.
Now this encrypted traffic has bought new challenges to the traditional way of traffic classification.

TLS:
One of the key cryptographic tools for providing communication security.
Today TLS is central to the internet services [1].
Protects user privacy & security, so the websites are using it.
Extensively used in HTTP, SMTP, FTP.
Websites using HTTP in TLS(HTTPS) have increased a lot.
Server and client first communicate through TLS handshake and communication starts[2].

SNI:
Extension to TLS protocol which holds the destination hostname.
Central component to HTTPS traffic inspection.
Acts as a filter during firewall inspection.
As HTTPS encrypts the traffic, SNI always runs on plaintext, which helps in filtering traffic [3].
Attacker can only sniff the domain name.


Basis of classification:
We’re here classify the traffic based on SNI attribute in HTTPS traffic.
So, we develop a novel deep learning model to classify the data.
Traffic leak can happen due to significant traffic and communication differences in web applications [4].
Accurate traffic classification can eliminate the information leaks [4].
Dataset details
This dataset is taken from top accessed HTTPS websites twice a day on Google Chrome and Firefox.[5]
This data was gathered over a two week period in 2016.
Dataset consists of almost 500,000 HTTPs flows from thousands of different services and websites [5].
We restrict our project to Google Chrome data only, which consisted of 301,018 HTTPS flows.

Preprocessing the dataset:
We use SSL filter on Wireshark to obtain only the HTTPS traffic[7].
SNI data, source IP, destination IP, source port number, and destination port number are taken.
 We unify the TCP connections which have their source and destination IP/port reversed.
 We then filter out all unknown SNIs and clean the remaining labels.

Random Forest Result:
The first model developed and used with great accuracy which deep learning models too unable to surpass.
We remove all least used website’s SNI tuples with a threshold of 100.
K-Fold cross validation is used with the value of K = 10.
Run the model with 100 epochs & early stopping.
The final average accuracy noted is around 93%.
 
Preliminary CNN model:
We first develop a basic CNN model and check it’s accuracy.
This model has CNN layer followed by a non linear activation function and max pooling. 
Above three layers become one module. 
We use any no of modules and end with fully connected layers followed by a softmax layer.
Training accuracy is 85% and testing accuracy is 78%.
 This model is under performing with ML model.

Double Deep Learning model:
This model is a hybrid model of CNN and ANN combined.
Our proposed model has additional layers in between layers of CNN.
Here each module composed of a CNN layer, non-linear activation function and then a MLP network.
Every module adopts a micro network after each CNN layer to enhance local modeling and abstraction.
There can be an number of modules depending on our dataset size and accuracy.


Results
We conclude with the following results:
The accuracy of the standard Random forest model is 93%.
 Our preliminary CNN model has been trained and tested and the accuracies are 85% and 78% respectively.
There has been numerous attempts in developing a novel model with higher accuracy than ML model.
Our final model’s training and testing accuracy reached 99% and 99.6% respectively.


Conclusion
The double deep learning method is used for the first time in traffic classification.
We can identify SNI by considering the sequence of encrypted TCP traffic.
Our model consists of convolutional layers and a micro-network between these layers.
The results of our model outperforms all the similar models with this dataset.
The best classification accuracy with this HTTPS traffic is resulted.
Future Scope
Further development and modification can be done to handle even more complex tasks.
Tasks like multi-channel classification includes different traffics like chat, voice call, and video call traffic in the skype application. 
The classification of TOR traffic is also a complex task to accomplish. 
We can use real-time traffic to test its effectiveness in predicting internet services. 
![image](https://github.com/HemanthkumarPutta/Network-Traffic-Classification/assets/40890488/d073b774-d000-4f6f-96a1-94b886372f64)
