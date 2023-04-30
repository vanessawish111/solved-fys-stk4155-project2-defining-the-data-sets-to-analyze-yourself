Download Link: https://assignmentchef.com/product/solved-fys-stk4155-project2-defining-the-data-sets-to-analyze-yourself
<br>
<h2>Defining the data sets to analyze yourself</h2>

For project 3, you can propose own data sets that relate to your research interests or just use existing data sets from say

<ol>

 <li><a href="https://www.kaggle.com/datasets">Kaggle</a></li>

 <li>The <a href="https://archive.ics.uci.edu/ml/index.php">University of California at Irvine (UCI) with its machine learning repository</a>.</li>

</ol>

The approach to the analysis of these new data sets should follow to a large extent what you did in projects 1 and 2. That is:

<ol>

 <li>Whether you end up with a regression or a classification problem, you should employ at least two of the methods we have discussed among <strong>linear regression (including Ridge and Lasso)</strong>, <strong>Logistic Regression</strong>, <strong>Neural Networks</strong>, <strong>Convolution Neural Networks</strong>, <strong>Recurrent Neural Networks</strong>, <strong>Support Vector Machines</strong> and <strong>Decision Trees, Random Forests</strong>, <strong>Bagging and Boosting</strong>. You could for example explore all of the approaches from decision trees, via bagging and voting classifiers, to random forests, boosting and finally XGboost. If you wish to venture into <strong>convolutional neural networks</strong> or <strong>recurrent neural networks</strong>, or extensions of neural networkds, feel free to do so.</li>

</ol>

For Boosting, feel also free to write your own codes.

<ol>

 <li>For project 3, you should feel free to use your own codes from projects 1 and 2, eventually write your own for SVMs and/or Decision trees/random forests/bagging/boosting’ or use the available functionality of <strong>Scikit-Learn</strong>, <strong>Tensorflow</strong>, etc.</li>

 <li>The estimates you used and tested in projects 1 and 2 should also be included, that is the <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi><mn>2</mn></math>">R</span></em>2R2-score, <strong>MSE</strong>, confusion matrix, accuracy score, information gain, ROC and Cumulative gains curves and other, cross-validation and/or bootstrap if these are relevant.</li>

 <li>Similarly, feel free to explore various activations functions in deep learning and various approachs to stochastic gradient descent approaches.</li>

 <li>If possible, you should link the data sets with exisiting research and analyses thereof. Scientific articles which have used Machine Learning algorithms to analyze the data are highly welcome. Perhaps you can improve previous analyses and even publish a new article?</li>

 <li>A critical assessment of the methods with ditto perspectives and recommendations is also something you need to include.</li>

</ol>

All in all, the report should follow the same pattern as the two previous ones, with abstract, introduction, methods, code, results, conclusions etc..

We propose also an alternative to the above. This is a project on using machine learning methods (neural networks mainly) to the solution of ordinary differential equations and partial differential equations, with a final twist on how to diagonalize a symmetric matrix with neural networks..

This is a field with a large interest recently, spanning from studies of turbulence in fluid mechanics and meteorology to the solution of quantum mechanical systems. As reading background you can use the slides <a href="https://compphysics.github.io/MachineLearning/doc/pub/week43/html/week43.html">from week 43</a> and/or the textbook by <a href="https://www.springer.com/gp/book/9789401798150">Yadav et al</a>.

<h2>The basic structure of your project</h2>

Here follows a set up on how to structure your report and analyze the data you have opted for.

<h3>Part a)</h3>

The first part deals with structuring and reading the data, much along the same lines as done in projects 1 and 2. Explain how the data are produced and place them in a proper context.

<h3>Part b)</h3>

You need to include at least two central algorithms, or as an alternative explore methods from decisions tree to bagging, random forests and boosting. Explain the basics of the methods you have chosen to work with. This would be your theory part.

<h3>Part c)</h3>

Then describe your algorithm and its implementation and tests you have performed.

<h3>Part d)</h3>

Then presents your results and findings, link with existing literature and more.

<h3>Part e)</h3>

Finally, here you should present a critical assessment of the methods you have studied and link your results with the existing literature.

<h2>Solving partial differential equations with neural networks</h2>

For this variant of project 3, we will assume that you have some background in the solution of partial differential equations using finite difference schemes. We will study the solution of the diffusion equation in one dimension using a standard explicit scheme and neural networks to solve the same equations.

For the explicit scheme, you can study for example chapter 10 of the lecture notes in <a href="https://github.com/CompPhysics/ComputationalPhysics/blob/master/doc/Lectures/lectures2015.pdf">Computational Physics</a> or alternative sources. For the solution of ordinary and partial differential equations using neural networks, the lectures by <a href="https://compphysics.github.io/MachineLearning/doc/pub/odenn/html/odenn-bs.html">Kristine Baluka Hein</a> at this course are highly recommended.

For the machine learning part you can use your own code from project 2 or the functionality of for example <strong>Tensorflow/Keras</strong>..

<h3>Part a), setting up the problem</h3>

The physical problem can be that of the temperature gradient in a rod of length <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>L</mi><mo>=</mo><mn>1</mn></math>">L</span></em>=1L=1 at <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi><mo>=</mo><mn>0</mn></math>">x</span></em>=0x=0 and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi><mo>=</mo><mn>1</mn></math>">x</span></em>=1x=1. We are looking at a one-dimensional problem

<span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mfrac><mrow><msup><mi mathvariant=&quot;normal&quot;>&amp;#x2202;</mi><mn>2</mn></msup><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo></mrow><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x2202;</mi><msup><mi>x</mi><mn>2</mn></msup></mrow></mfrac><mo>=</mo><mfrac><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x2202;</mi><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo></mrow><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x2202;</mi><mi>t</mi></mrow></mfrac><mo>,</mo><mi>t</mi><mo>&amp;gt;</mo><mn>0</mn><mo>,</mo><mi>x</mi><mo>&amp;#x2208;</mo><mo stretchy=&quot;false&quot;>[</mo><mn>0</mn><mo>,</mo><mi>L</mi><mo stretchy=&quot;false&quot;>]</mo></math>">∂2u(<em>x</em>,<em>t</em>)∂<em>x</em>2</span>=∂<em>u</em>(<em>x</em>,<em>t</em>)∂<em>t</em>,<em>t</em>&gt;0,<em>x</em>∈[0,<em>L</em>]∂2u(x,t)∂x2=∂u(x,t)∂t,t&gt;0,x∈[0,L]

or

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><msub><mi>u</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>x</mi><mi>x</mi></mrow></msub><mo>=</mo><msub><mi>u</mi><mi>t</mi></msub><mo>,</mo></math>">u</span></em><em>xx</em>=<em>u</em><em>t</em>,uxx=ut,

with initial conditions, i.e., the conditions at <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>t</mi><mo>=</mo><mn>0</mn></math>">t</span></em>=0t=0,

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mn>0</mn><mo stretchy=&quot;false&quot;>)</mo><mo>=</mo><mi>sin</mi><mo>&amp;#x2061;</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>(</mo><mi>&amp;#x03C0;</mi><mi>x</mi><mo stretchy=&quot;false&quot;>)</mo></mrow><mspace width=&quot;0.5cm&quot; /><mn>0</mn><mo>&amp;lt;</mo><mi>x</mi><mo>&amp;lt;</mo><mi>L</mi><mo>,</mo></math>">u</span></em>(<em>x</em>,0)=sin(<em>πx</em>)0&lt;<em>x</em>&lt;<em>L</em>,u(x,0)=sin⁡(πx)0&lt;x&lt;L,

with <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>L</mi><mo>=</mo><mn>1</mn></math>">L</span></em>=1L=1 the length of the <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi></math>">x</span></em>x-region of interest. The boundary conditions are

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mn>0</mn><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>=</mo><mn>0</mn><mspace width=&quot;0.5cm&quot; /><mi>t</mi><mo>&amp;#x2265;</mo><mn>0</mn><mo>,</mo></math>">u</span></em>(0,<em>t</em>)=0<em>t</em>≥0,u(0,t)=0t≥0,

and

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>L</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>=</mo><mn>0</mn><mspace width=&quot;0.5cm&quot; /><mi>t</mi><mo>&amp;#x2265;</mo><mn>0.</mn></math>">u</span></em>(<em>L</em>,<em>t</em>)=0<em>t</em>≥0.u(L,t)=0t≥0.

The function <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo></math>">u</span></em>(<em>x</em>,<em>t</em>)u(x,t) can be the temperature gradient of a rod. As time increases, the velocity approaches a linear variation with <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi></math>">x</span></em>x.

We will limit ourselves to the so-called explicit forward Euler algorithm with discretized versions of time given by a forward formula and a centered difference in space resulting in

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><msub><mi>u</mi><mi>t</mi></msub><mo>&amp;#x2248;</mo><mfrac><mrow><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mi>t</mi><mo>+</mo><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>&amp;#x2212;</mo><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo></mrow><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><msub><mi>x</mi><mi>i</mi></msub><mo>,</mo><msub><mi>t</mi><mi>j</mi></msub><mo>+</mo><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>&amp;#x2212;</mo><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><msub><mi>x</mi><mi>i</mi></msub><mo>,</mo><msub><mi>t</mi><mi>j</mi></msub><mo stretchy=&quot;false&quot;>)</mo></mrow><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></mrow></mfrac></math>">u</span></em><em>t</em>≈<em>u</em>(<em>x</em>,<em>t</em>+Δ<em>t</em>)−<em>u</em>(<em>x</em>,<em>t</em>)Δ<em>t</em>=<em>u</em>(<em>x</em><em>i</em>,<em>t</em><em>j</em>+Δ<em>t</em>)−<em>u</em>(<em>x</em><em>i</em>,<em>t</em><em>j</em>)Δ<em>t</em>ut≈u(x,t+Δt)−u(x,t)Δt=u(xi,tj+Δt)−u(xi,tj)Δt

and

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><msub><mi>u</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>x</mi><mi>x</mi></mrow></msub><mo>&amp;#x2248;</mo><mfrac><mrow><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>+</mo><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>&amp;#x2212;</mo><mn>2</mn><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>+</mo><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>&amp;#x2212;</mo><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>x</mi><mo>,</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo></mrow><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><msup><mi>x</mi><mn>2</mn></msup></mrow></mfrac><mo>,</mo></math>">u</span></em><em>xx</em>≈<em>u</em>(<em>x</em>+Δ<em>x</em>,<em>t</em>)−2<em>u</em>(<em>x</em>,<em>t</em>)+<em>u</em>(<em>x</em>−Δ<em>x</em>,<em>t</em>)Δ<em>x</em>2,uxx≈u(x+Δx,t)−2u(x,t)+u(x−Δx,t)Δx2,

or

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><msub><mi>u</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>x</mi><mi>x</mi></mrow></msub><mo>&amp;#x2248;</mo><mfrac><mrow><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><msub><mi>x</mi><mi>i</mi></msub><mo>+</mo><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>x</mi><mo>,</mo><msub><mi>t</mi><mi>j</mi></msub><mo stretchy=&quot;false&quot;>)</mo><mo>&amp;#x2212;</mo><mn>2</mn><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><msub><mi>x</mi><mi>i</mi></msub><mo>,</mo><msub><mi>t</mi><mi>j</mi></msub><mo stretchy=&quot;false&quot;>)</mo><mo>+</mo><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><msub><mi>x</mi><mi>i</mi></msub><mo>&amp;#x2212;</mo><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>x</mi><mo>,</mo><msub><mi>t</mi><mi>j</mi></msub><mo stretchy=&quot;false&quot;>)</mo></mrow><mrow><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><msup><mi>x</mi><mn>2</mn></msup></mrow></mfrac><mo>.</mo></math>">u</span></em><em>xx</em>≈<em>u</em>(<em>x</em><em>i</em>+Δ<em>x</em>,<em>t</em><em>j</em>)−2<em>u</em>(<em>x</em><em>i</em>,<em>t</em><em>j</em>)+<em>u</em>(<em>x</em><em>i</em>−Δ<em>x</em>,<em>t</em><em>j</em>)Δ<em>x</em>2.uxx≈u(xi+Δx,tj)−2u(xi,tj)+u(xi−Δx,tj)Δx2.

Write down the algorithm and the equations you need to implement. Find also the analytical solution to the problem.

<h3>Part b)</h3>

Implement the explicit scheme algorithm and perform tests of the solution for <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>x</mi><mo>=</mo><mn>1</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>/</mo></mrow><mn>10</mn></math>">Δ<em>x</em>=1/10</span>Δx=1/10, <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>x</mi><mo>=</mo><mn>1</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>/</mo></mrow><mn>100</mn></math>">Δ<em>x</em>=1/100</span>Δx=1/100 using <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">Δ<em>t</em></span>Δt as dictated by the stability limit of the explicit scheme. The stability criterion for the explicit scheme requires that <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>/</mo></mrow><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><msup><mi>x</mi><mn>2</mn></msup><mo>&amp;#x2264;</mo><mn>1</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>/</mo></mrow><mn>2</mn></math>">Δ<em>t</em>/Δ<em>x</em>2≤1/2</span>Δt/Δx2≤1/2.

Study the solutions at two time points <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msub><mi>t</mi><mn>1</mn></msub></math>">t</span></em>1t1 and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msub><mi>t</mi><mn>2</mn></msub></math>">t</span></em>2t2 where <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><msub><mi>t</mi><mn>1</mn></msub><mo stretchy=&quot;false&quot;>)</mo></math>">u</span></em>(<em>x</em>,<em>t</em>1)u(x,t1) is smooth but still significantly curved and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>u</mi><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>,</mo><msub><mi>t</mi><mn>2</mn></msub><mo stretchy=&quot;false&quot;>)</mo></math>">u</span></em>(<em>x</em>,<em>t</em>2)u(x,t2) is almost linear, close to the stationary state.

<h3>Part c) Neural networks</h3>

Study now the lecture notes on solving ODEs and PDEs with neural network and use either your own code from project 2 or the functionality of tensorflow/keras to solve the same equation as in part b). Discuss your results and compare them with the standard explicit scheme. Include also the analytical solution and compare with that.

<h3>Part d) Solving eigenvalue problems</h3>

Follow the discussion in the work of Yi <em>et al.</em> in the article from <a href="https://www.sciencedirect.com/science/article/pii/S0898122104901101">Computers and Mathematics with Applications 47, 1155 (2004)</a>, and use your differential equation solver with neural networks, set up a simple square, real and symmetric <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mn>6</mn><mo>&amp;#x00D7;</mo><mn>6</mn></math>">6×6</span>6×6 matrix and find the eigenvalues. Compare with the solution from numerical diagonalization with standard eigenvalue solvers from linear algebra.

<h3>Part e)</h3>

Finally, present a critical assessment of the methods you have studied and discuss the potential for the solving differential equations and eigenvalue problems with machine learning methods.

<h2>Introduction to numerical projects</h2>

Here follows a brief recipe and recommendation on how to write a report for each project.

<ul>

 <li>Give a short description of the nature of the problem and the eventual numerical methods you have used.</li>

 <li>Describe the algorithm you have used and/or developed. Here you may find it convenient to use pseudocoding. In many cases you can describe the algorithm in the program itself.</li>

 <li>Include the source code of your program. Comment your program properly.</li>

 <li>If possible, try to find analytic solutions, or known limits in order to test your program when developing the code.</li>

 <li>Include your results either in figure form or in a table. Remember to label your results. All tables and figures should have relevant captions and labels on the axes.</li>

 <li>Try to evaluate the reliabilty and numerical stability/precision of your results. If possible, include a qualitative and/or quantitative discussion of the numerical stability, eventual loss of precision etc.</li>

 <li>Try to give an interpretation of you results in your answers to the problems.</li>

 <li>Critique: if possible include your comments and reflections about the exercise, whether you felt you learnt something, ideas for improvements and other thoughts you’ve made when solving the exercise. We wish to keep this course at the interactive level and your comments can help us improve it.</li>

 <li>Try to establish a practice where you log your work at the computerlab. You may find such a logbook very handy at later stages in your work, especially when you don’t properly remember what a previous test version of your program did. Here you could also record the time spent on solving the exercise, various algorithms you may have tested or other topics which you feel worthy of mentioning.</li>

</ul>

<h2>Introduction to numerical projects</h2>

Here follows a brief recipe and recommendation on how to write a report for each project.

<ul>

 <li>Give a short description of the nature of the problem and the eventual numerical methods you have used.</li>

 <li>Describe the algorithm you have used and/or developed. Here you may find it convenient to use pseudocoding. In many cases you can describe the algorithm in the program itself.</li>

 <li>Include the source code of your program. Comment your program properly.</li>

 <li>If possible, try to find analytic solutions, or known limits in order to test your program when developing the code.</li>

 <li>Include your results either in figure form or in a table. Remember to label your results. All tables and figures should have relevant captions and labels on the axes.</li>

 <li>Try to evaluate the reliabilty and numerical stability/precision of your results. If possible, include a qualitative and/or quantitative discussion of the numerical stability, eventual loss of precision etc.</li>

 <li>Try to give an interpretation of you results in your answers to the problems.</li>

 <li>Critique: if possible include your comments and reflections about the exercise, whether you felt you learnt something, ideas for improvements and other thoughts you’ve made when solving the exercise. We wish to keep this course at the interactive level and your comments can help us improve it.</li>

 <li>Try to establish a practice where you log your work at the computerlab. You may find such a logbook very handy at later stages in your work, especially when you don’t properly remember what a previous test version of your program did. Here you could also record the time spent on solving the exercise, various algorithms you may have tested or other topics which you feel worthy of mentioning.</li>

</ul>

<h2>Format for electronic delivery of report and programs</h2>

The preferred format for the report is a PDF file. You can also use DOC or postscript formats or as an ipython notebook file. As programming language we prefer that you choose between C/C++, Fortran2008 or Python. The following prescription should be followed when preparing the report:

<ul>

 <li>Use Canvas to hand in your projects, log in at <a href="https://www.uio.no/english/services/it/education/canvas/">https://www.uio.no/english/services/it/education/canvas/</a> with your normal UiO username and password.</li>

 <li>Upload <strong>only</strong> the report file or the link to your GitHub/GitLab or similar typo of repos! For the source code file(s) you have developed please provide us with your link to your GitHub/GitLab or similar domain. The report file should include all of your discussions and a list of the codes you have developed. Do not include library files which are available at the course homepage, unless you have made specific changes to them.</li>

 <li>In your GitHub/GitLab or similar repository, please include a folder which contains selected results. These can be in the form of output from your code for a selected set of runs and input parameters.</li>

</ul>

Finally, we encourage you to collaborate. Optimal working groups consist of 2-3 students. You can then hand in a common report.

<h2>Software and needed installations</h2>

If you have Python installed (we recommend Python3) and you feel pretty familiar with installing different packages, we recommend that you install the following Python packages via <strong>pip</strong> as

<ol>

 <li>pip install numpy scipy matplotlib ipython scikit-learn tensorflow sympy pandas pillow</li>

</ol>

For Python3, replace <strong>pip</strong> with <strong>pip3</strong>.

See below for a discussion of <strong>tensorflow</strong> and <strong>scikit-learn</strong>.

For OSX users we recommend also, after having installed Xcode, to install <strong>brew</strong>. Brew allows for a seamless installation of additional software via for example

<ol>

 <li>brew install python3</li>

</ol>

For Linux users, with its variety of distributions like for example the widely popular Ubuntu distribution you can use <strong>pip</strong> as well and simply install Python as

<ol>

 <li>sudo apt-get install python3 (or python for python2.7)</li>

</ol>

etc etc.

If you don’t want to install various Python packages with their dependencies separately, we recommend two widely used distrubutions which set up all relevant dependencies for Python, namely

<ol>

 <li><a href="https://docs.anaconda.com/">Anaconda</a> Anaconda is an open source distribution of the Python and R programming languages for large-scale data processing, predictive analytics, and scientific computing, that aims to simplify package management and deployment. Package versions are managed by the package management system <strong>conda</strong></li>

 <li><a href="https://www.enthought.com/product/canopy/">Enthought canopy</a> is a Python distribution for scientific and analytic computing distribution and analysis environment, available for free and under a commercial license.</li>

</ol>

Popular software packages written in Python for ML are

<ul>

 <li><a href="http://scikit-learn.org/stable/">Scikit-learn</a>,</li>

 <li><a href="https://www.tensorflow.org/">Tensorflow</a>,</li>

 <li><a href="http://pytorch.org/">PyTorch</a> and</li>

 <li><a href="https://keras.io/">Keras</a>.</li>

</ul>

These are all freely available at their respective GitHub sites. They encompass communities of developers in the thousands or more. And the number of code developers and contributors keeps increasing.

© 1999-2020, “Data Analysis and Machine Learning FYS-STK3155/FYS4155″:”http://www.uio.no/studier/emner/matnat/fys/FYS3155/index-eng.html”. Released under CC Attribution-NonCommercial 4.0 license