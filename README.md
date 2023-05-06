Download Link: https://assignmentchef.com/product/solved-ece523-homework-3
<br>
<ul>

 <li>The <em>`</em><sub>2 </sub>Support Vector Machine</li>

</ul>

In class, we discussed that if our data is not linearly separable, then we need to modify our optimization problem to include slack variables. The formulation that was used is known as the <em>`</em><sub>1</sub>-norm soft margin SVM. Now consider the formulation of the <em>`</em><sub>2</sub>-norm soft margin SVM, which squares the slack variables within the sum. Notice that non-negativity of the slack variables has been removed.

arg min <strong>w</strong>

s.t. <em>y<sub>i</sub></em>(<strong>w</strong><em><sup>T </sup></em><strong>x</strong><em><sub>i </sub></em>+ <em>b</em>) ≥ 1 − <em>ξ<sub>i                      </sub></em>∀<em>i </em>∈ [<em>n</em>]

Derive the dual form expression along with any constraints. Work must be shown. <em>Hints</em>: Refer to the methodology that was used in class to derive the dual form. The solution is given by:

<em>n                               n         n                                                                         n</em>

argmax

<em>i</em>=1                            <em>i</em>=1 <em>j</em>=1                                                                      <em>i</em>=1

s.t. <em>α<sub>i </sub></em>≥ 0 ∀<em>i </em>∈ [<em>n</em>]         and

<ul>

 <li>Domain Adaptation Support Vector Machines</li>

</ul>

We now look at a different type of SVM that is designed for domain adaptation and optimizes the hyperplanes given by <strong>w</strong><em><sub>S </sub></em>(source hyperplane) before optimizing <strong>w</strong><em><sub>T </sub></em>(target hyperplane). The process begins by training a support vector machine on source data then once data from the target are available, train a new SVM using the hyperplane from the first SVM and the data from the target to solve for a new “domain adaptation” SVM.

The primal optimization problem is given by arg min

<strong>w</strong><em><sub>T</sub></em><em>,ξ                                                         </em>2 <em>i</em>=1

s.t. <em>y<sub>i</sub></em>(<strong>w</strong><em><sub>T</sub><sup>T </sup></em><strong>x</strong><em><sub>i </sub></em>+ <em>b</em>) ≥ 1 − <em>ξ<sub>i </sub></em>∀<em>i </em>∈{1<em>,…,n</em>} <em>ξ<sub>i </sub></em>≥ 0        ∀<em>i </em>∈{1<em>,…,n</em>}

where <strong>w</strong><em><sub>S </sub></em>is hyperplane trained on the source data (<em>assumed to be known</em>), <strong>w</strong><em><sub>T </sub></em>is hyperplane for the target, <em>y<sub>i </sub></em>∈ {±1} is the label for instance <strong>x</strong><em><sub>i</sub></em>, <em>C </em>&amp; <em>B </em>are regularization parameters defined by the user and <em>ξ<sub>i </sub></em>is a slack variable for instance <strong>x</strong><em><sub>i</sub></em>. The problem becomes finding a hyperplane, <strong>w</strong><em><sub>T </sub></em>, that minimizes the above objective function subject to the constraints. Solve/derive the dual optimization problem.

<em>Note: I will give the class the solution to this problem prior to the due date because Problem #3 requires that you implement this algorithm in code.</em>

<ul>

 <li>Density Estimation (Code)</li>

</ul>

Implement the domain adaptation SVM from Problem #2. A data setfor the source and target domains (both training and testing) have been uploaded to D2L. There are several ways to implement this algorithm. If I were doing this for an assignment, I would implement the SVM (both the domain adaptation SVM and normal SVM) directly using quadratic programming. You do not need to build the classifier (i.e., solve for the bias term); however, you will need to find <strong>w</strong><em><sub>T </sub></em>and <strong>w</strong><em><sub>S</sub></em>. To find the weight vectors, you will need to solve a quadratic programming problem and look through the documentation to learn how to solve this optiization task. The following Python packages are recommended:

<ul>

 <li>CVXOPT(<a href="https://cvxopt.org/">https://cvxopt.org/</a><a href="https://cvxopt.org/">)</a></li>

 <li>PyCVX (<a href="https://www.cvxpy.org/install/">https://www.cvxpy.org/install/</a><a href="https://www.cvxpy.org/install/">)</a></li>

</ul>

<em>Note: Your solution can use any of the packages above.</em>