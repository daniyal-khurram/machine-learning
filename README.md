Fine-Tuning a Pre-Trained Network

Task
Write a Python function to be used at the end of training that generates HTML output showing each test image and its classification scores. You could produce an HTML table output for example. (You can convert the HTML output to PDF or use screen shots.)

Required Files
1. cifar_finetune.py
2. html_gen.py

Packages
1. PyTorch: v 1.3.0
2. Torchvision: v 0.4.1

Python Version
3.7

Task Completion Details
A function named test(..) was added to the cifar_finetune.py file
      
  1) Takes a trained model and test data set as inputs
  2) Feeds the input data into the model, and retrieves the generated outputs
  3) Determines the class prediction, by choosing the class with the highest output value, for a given test image
  4) Compares the predicted value with the expected label value, and calculates the number of correct predictions
  5) Applies the softmax function onto the output values. Thsi will transform the output values into probabilities
  6) Calculates the precision of the network, by dividing the number of correct predictions by the total number of test images
  7) Returns the test_image class name, predictions, probabilities, correct predictions, total number of test images, network precision
  
A file named html_gen.py was also created
A function named html_gen(..) was added to this file
	
  1) Takes the return values of the test(..) function (inside cifar_pytune.py), as its inputs
  2) Creates table showing each test image and its classification
  3) Creates an additionaly table, showing the precision of the network for each epoch
  4) Returns the HTML code, for the above mentioned tasks 
  
A function named html_write(..) was added to this file

  1) Takes the return values of the html_gen(..) function, as its input. Along with a user specified filename
  2) Creates a HTML file in the working directory of the program, with the filename specified in the input

Run instructions
1. Open cmd/terminal and set the current working directory to the directory where the python file is present.
2. Type python3 cifar_finetune.py
