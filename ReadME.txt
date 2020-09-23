***************************************************
* Submitted By : Bhupati Bhupen Singh Mohanta	  *
* Roll no : 117CS0233				  *
***************************************************
Face Recognition using Principal Component Analysis
***************************************************

Note:   Dataset used: ATnT (extract "ATnT.rar" file for ATnT dataset)
	Program file: "Mohanta_Bhupati_117CS0233_Assign3_Graph.ipynb"

Step1. Load train dataset, calculate mean and subtract mean from each face image.

Step2. Calculate Co-variance of mean allined faces.(So that covariance  matrix will be p*p).
	Here p = no of training images.

Step3. Find the Eigen values (w) and Eigen vectors of above covariance matrix.

Step4. Sort the eigen vectors in dscending order of their eigen values.

Step5. Load test dataset, subtract mean from each face image.
-------------------------------------------------------------------------------------------------------------------------------

Step6. For K=50, choose 50 eigen vectors corresponding to highest 50 eigen values.
	Now, Generate the feature vector of shape (p*K)

Step7. Multiply the above feature vector with mean alligned face from step1 to generate eigenfaces.
	shape of eigenfaces (K * (m*n)).

Step8. Project mean alligned face to eigenfaces (i.e. multiply each eigenfaces from step7 with transpose(mean alligned face))
	to generate signature of each face (p * K)

Step9. Project mean alligned test faces from step5 (i.e. multiply each eigenfaces from step6 with transpose(mean alligned test faces from step5))
	to generate projected test faces of each face (t * K), where t = no. of test images.

Step10. Calculate Euclidean distance of each projected test faces from generatd signature faces.
	Assign the each test face to the class of their minimum Euclidean distance face.

Step11. Compare the actual class of the test face with assigned class and hence find the acuracy of classification.

-----------------------------------------------------------------------------------------------------------------------------------

Step12. Repeat step6 to step11 for K value range from 1 to p(no of training images).

Step13. Plot graph between ranging K value on X axis and corresponding obtained accuracy on Y axis.
	(Done in file: "Mohanta_Bhupati_117CS0233_Assign3_Graph.ipynb")

Note. File: "Mohanta_Bhupati_117CS0233_faceRecognition_K=50_.ipynb" contains K=50 principal components face rcognition.