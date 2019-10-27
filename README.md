Fine-Tuning a Pre-Trained Network

Task
Write a Python function to be used at the end of training that generates HTML output showing each test image and its classification scores. You could produce an HTML table output
for example. (You can convert the HTML output to PDF or use screen shots.)

Required Files
1. cifar_finetune.py
2. html_gen.py

Tools, Packages, Libraries
PyTorch: v 1.3.0
Torchvision: v 0.4.1

Python Version
3.7

Task Completion Details
A function named test(..) was added to the cifar_finetune.py file

	def test(model, testloader):
    """
    Args:
      model: trained model
      testloader: test data set
      
    Returns:
      test_image, predictions, probability, correct, total, precision
    """
  a) Takes a trained model and test data set as inputs
  b) Feeds the input data into the model, and retrieves the generated outputs
  c) Determines the class prediction, by retrieving the class with the highest output value, for a given test image
  d) Compares the predicted value with the expected label value, and calculates the number of correct predictions
  e) Applies the softmax function onto the outputs. Thsi will transform the output values into probabilities
  f) Calculates the precision of the network, by dividing the number of correct predictions by the total number of test images
	e) Returns the test_image class name, predictions, probabilities, correct predictions, total number of test images, network precision
  
A file named html_gen.py was also created 
	
  a) Takes the return values of the test(..) function (inside cifar_pytune.py), as its inputs
  b) Creates table showing each test image and its classification
  c) Creates an additionaly table, showing the precision of the network for each epoch
	d) Generates an HTML as an output in the working directory of the program

Run instructions
1. Open cmd/terminal and set the current working directory to the directory where the python file is present.
2. Type python3 cifar_finetune.py
