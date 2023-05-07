Download Link: https://assignmentchef.com/product/solved-mas3114-project-2
<br>
Each exercise has to begin with the line <strong>Exercise#</strong>

You should also mark down the parts such as (a), (b), (c), and etc. This makes grading easier. <strong><u>Important</u>: we use the default </strong>format short<strong> for the numbers in all exercises unless it is specified otherwise</strong>. We <u>do not employ</u> format rat since it may cause problems with running the codes and displaying matrices in Live Script. If format long has been used, please make sure to return to the default format in the next exercise.




<h1>Part I. Elementary Row-Operations</h1>

In this exercise you will write three functions that create the three types of elementary matrices and, then, perform elementary row-operations on a given matrix using the created functions.  <strong><u>Theory</u></strong>: To create an elementary <em>n n</em><sub>×</sub> matrix, we apply a row operation, such as, row replacement, row interchanging, or scaling, to the <em>n n</em><sub>×</sub> identity matrix. This will produce an elementary matrix of one of the three types, E1, E2, or E3, respectively. When an <em>n m</em><sub>×</sub> matrix A is left-multiplied by an elementary matrix E1, E2, or E3, it performs the same operation on the matrix A as was the operation that created that elementary matrix from the identity matrix.




**Create the three functions in MATLAB – each function outputs one of the three types of elementary <em>n n</em>× matrices E1, E2, or E3:

function E1=ele1(n,r,i,j) function E2=ele2(n,i,j) function E3=ele3(n,j,k)




**To generate these matrices, start with the identity matrix eye(n)and proceed as follows:

For ele1: matrix E1 is obtained from eye(n)by replacing (row <em>j</em>) with [(row <em>j</em>) + (row <em>i</em>)⋅<em>r</em>].

For ele2: matrix E2 is obtained from eye(n)by interchanging rows <em>i</em> and <em>j</em>.

For ele3: matrix E3 is obtained from eye(n)by multiplying row j by <em>k</em>.

(Here, <em>i j</em>,  are the indexes, each is in the range from 1 to <em>n</em>, and <em>k</em> is a scalar.) <em> </em>




**Print the created functions in your Live Script:

type ele1 type ele2 type ele3




**Next, type in the Live Script

format format compact

0 1 3 1<sub></sub>

and input the matrix <em>A</em>=<sup></sup><sub></sub>2 4 6 2− <sup></sup><sub></sub>.

<sub></sub>3 1 4 2<sub></sub>




First, reduce matrix A to the reduced echelon form <strong>by hand on paper</strong>.  After you completed hand calculations, go over the elementary row operations applied to the matrix A and, on each step, identify the variables, such as <em>n</em>, <em>i</em>, <em>j</em>, and etc., which are the inputs in the corresponding function ele1, ele2, or ele3.




**Then, return to the Live Script and start reducing matrix A to the reduced echelon form using functions ele1, ele2, and ele3.

Here is an example how you can proceed with this task: the first possible operation could be interchanging rows 1 and 2 in A – this will place a non-zero number into the pivot position. We are using here function ele2 on the variables n=3, i=1,j=2 (where n=3 is the number of rows in A, and rows i=1 and j=2 are interchanging). Then, we run the function ele2 to output the matrix E2:

E2=ele2(3,1,2);

(we output E2, but do not display it in the Live Script).

Next, we are left-multiplying matrix A by E2 – this will apply the row interchanging operation to the matrix A – the result has to be output (and <u>displayed</u>) as a new matrix A1:

A1=E2*A

After you are done with your first row operation, proceed with your second row operation (you will apply it to the new matrix A1): create the corresponding elementary matrix and leftmultiply A1 by the created elementary matrix to output (and display) a new matrix A2, which is the result of applying your second row operation.

You will continue this way and generate a sequence of the matrices A1, A2, … until you arrive at the reduced echelon form of A, matrix AN (N will be a specific number).  <u>Note</u>: make sure that you will output and <u>display</u> all matrices A1, A2,…,AN.




**Use a logical statement to check if your matrix AN matches the output of a built-in MATLAB function that produces the reduced echelon form of A, rref(A). If this is the case, output a corresponding message. If the message is not displayed after you run your logical statement, consider making a revision of the previous steps.




<h1>Part II. Basic Operations</h1>




In this part of the project, you will create a function that utilizes the row reduction algorithm to calculate and output the inverse matrix of an invertible matrix A.

function F=inverses(A) which takes as input an <em>n n</em><sub>×</sub> matrix A. All of the below have to be included into the function. **First, the function has to determine whether A is invertible – use a built-in MATLAB function <strong>rank</strong>.

<u>If A is not invertible</u>, the function returns an empty matrix

F=[];

and outputs a message “matrix A is not invertible”. After that, the program <u>terminates</u>.




<u>If A is invertible</u>, the function <u>continues</u> with calculating the matrix F, which is the inverse of the matrix A.

**To calculate F, we reduce matrix [A eye(n)] into the reduced echelon form and output (and <u>display)</u> the last <em>n n</em><sub>×</sub> block of the reduced echelon form – it is the inverse matrix F. You will need to use a MATLAB built-in function <strong>rref</strong> for this part.

**Then, we calculate the inverse matrix using a built-in MATLAB function <strong>inv</strong>:

P=inv(A)

Output (and <u>display</u>) the matrix P with a message that P is the inverse of A calculated using a MATLAB function.

**Finally, we use a logical statement to determine if the matrices F and P match. You will need to employ <em>closetozeroroundoff</em> function in your code with p=5. If F and P match, output a corresponding message. Make sure that you will receive this message, otherwise, consider making corrections in your code.

<strong>This is the end of your function</strong> inverses.




**Type the function inverses and closetozeroroundoff in your Live Script.

**Run the function F=inverses(A) on the matrices in parts (a)-(e). Notice that some inputs are suppressed.

<ul>

 <li>A=[4 0 -7 -7;-6 1 11 9;7 -5 10 19;-1 2 3 -1]</li>

 <li>A=[1 -3 2 -4;-3 9 -1 5;2 -6 4 -3;-4 12 2 7]</li>

 <li>A=magic(3);</li>

 <li>A=hilb(5);</li>

 <li>A=magic(6);</li>

</ul>




<h1>Part III. Solving Equations</h1>

<strong>                                     </strong>

In this part of the project, you will learn the basics on solving equations <em>A</em><strong>x b</strong>= when A is an invertible matrix. You should read the content carefully and perform the indicated tasks in

MATLAB.

<strong>Solving Matrix Equations.</strong> Suppose A is an invertible <em>n n</em><sub>×</sub> matrix and you are solving equation A<strong>x </strong>= <strong>b</strong>. By the invertible matrix Theorem, there exists a unique solution for every <strong>b </strong>in¡<em><sup>n </sup></em>. We have several methods of finding the solution. Three of them are considered below.




<ul>

 <li>There is a special operator in MATLAB,  , called <strong>backslash</strong>, that usually gives an excellent result. To use it, store A and <strong>b</strong> and type A Backslash is the best of the methods. It works fast and minimizes a round-off error. It also checks the condition number on the coefficient matrix. If the condition number is large, it will warn you by printing message:</li>

</ul>

“Matrix is close to singular or badly scaled. Results may be inaccurate.”

For more information on condition number, please refer to MATLAB documentation:

<a href="https://www.mathworks.com/help/matlab/ref/cond.html?s_tid=doc_ta">https://www.mathworks.com/help/matlab/ref/cond.html?s_tid=doc_ta</a>

<ul>

 <li>The second method is using a built-in MATLAB function <strong>inv,</strong> which also checks the condition number, but calculating <strong>inv</strong>(A) requires a lot more arithmetic than backslash.</li>

</ul>




<ul>

 <li>The third method employs a MATLAB built-in function <strong>rref</strong>. This function was written to help students to learn Linear Algebra, so its algorithm is not accurate, and it will not warn you if your system is one of those for which it is hard to get an accurate solution. This function should not be used to solve real world problems. However, for the matrices with integer entries, you could use the command rref([A b]) to get the reduced echelon form of the augmented matrix and, then, output the last column as the solution.</li>

</ul>

<strong>Part 1. Solving a system</strong> A<strong>x </strong>= <strong>b</strong>                                                                   <strong> </strong>

**Create a function in MATLAB that begins with:

function [C,N]=solvesys(A,b)

[~,n]=size(A); format long




We are using format long to display a number in exponent format with 15 digit mantissas. If, later on, you will need to switch back to the default format, type and run format




The inputs are an <em>n n</em><sub>×</sub> matrix A and an <em>n</em><sub>×</sub>1 vector <strong>b</strong>. If A is invertible, the outputs are the matrix C, whose 3 columns <strong>x1, x2, x3 </strong>are the solutions obtained by the three methods described above, respectively, and N is the vector whose 3 entries are the 2-norms of the vectors of the differences between each two distinct solutions.




**First, check if A is invertible – use a MATLAB built-in function <em>rank</em>. <u>If A is not invertible</u>, output the message ‘A is not invertible’ and assign empty outputs:

C=[];

N=[];

Also, in this case, you will need to identify which of the two possibilities holds for the system A<strong>x </strong>= <strong>b </strong>when A is not invertible<strong>:</strong> ‘The system is inconsistent’ or ‘The system is consistent, but the solution is not unique’. Use the command <em>rank</em> to check the system on each of the two possible cases and program two possible output messages. After that, <u>terminate</u> the program.

<u>If A is invertible</u>, the function continues with solving equation A<strong>x </strong>= <strong>b</strong> by the three methods described above and outputs the solutions <strong>x1, x2, x3 </strong>for each of the methods (1)-(3), respectively. These solutions have to form the columns of the matrix C. Thus, we will assign  C=[x1,x2,x3] and <u>display</u> C with the message that ‘Solutions obtained by different methods are the columns of’

(<u>display</u> C)




**Next, the function has to return a <u>column</u> vector  N=[n1;n2;n3];  where  n1=norm(x1-x2); n2=norm(x2-x3); n3=norm(x3-x1);

which has to be <u>displayed</u> with a message ‘Norms of differences between solutions are the entries of’

(output N)




<u>Note</u>: The entries of the vector <strong>N</strong> are calculated by using a built-in MATLAB function norm, which, when applied to a vector, calculates the square root of the sum of squares of the entries of the vector – it is also called the 2-norm. The vector <strong>N</strong> gives an idea how “close” are the solutions obtained by various methods.




**Print the function solvesys in your Live Script.

**Run the function [C,N]=solvesys(A,b) for the following choices of the matrix A and vector <strong>b</strong>. Type the matrices and the vectors as they are displayed below – notice, some inputs are suppressed.

%(a)

A=magic(4);I=eye(size(A,1));b=I(:,end)

%(b)

A=magic(4),b=A(:,end)

%(c)

A=magic(5);b=fix(10*rand(size(A,1),1))

%(d)

A=eye(6);b=fix(10*rand(size(A,1),1))

%(e)

A=magic(7); b=fix(10*rand(size(A,1),1))

%(f)

A=hilb(7);

(in part (f), the vector b is the one that you stored for part (e)).




% Write a comment on the output for part (d) by comparing the solution with the vector <strong>b</strong>. % Analyze the output vector N throughout the choices (c)-(f). For which of them the solutions obtained by different methods are not really “close” to each other?

<strong> </strong>

<strong>Part 2.</strong> <u>Condition numbers</u>

**Calculate the condition numbers for the matrices A=magic(7) and  A=hilb(7).

c1=cond(magic(7)) c2=cond(hilb(7))

% Compare c1 and c2 with number 1 and comment in your Live Script why, on your opinion, the norms of the differences between the solutions for the coefficient matrix in part (f) are so large compared with the ones for the matrix in part (e).




**Explore sensitivity to perturbations of a badly conditioned matrix hilb(7): Input in the Live Script:

A=hilb(7);

Run the following code:

b=ones(7,1); x=Ab; b1=b+0.01; y=Ab1; norm(x-y) c3=rcond(A)

**Re-run the code above for:

A=magic(7);




%Comment on sensitivity to perturbations of magic(7)<sup> compared with </sup>hilb(7) by analyzing the corresponding outputs for the norm(x-y) and c3.




More information on the reciprocal condition numbers can be found on the MATLAB page: <a href="https://www.mathworks.com/help/matlab/ref/rcond.html?s_tid=doc_ta">https://www.mathworks.com/help/matlab/ref/rcond.html?s_tid=doc_ta</a>

<strong> </strong>

<h1>Part IV. Area, Volume, and Graphics in MATLAB</h1>




GOAL: In this part, you will work with applications of matrices and determinants to Geometry and, specifically, to calculating area and volume. You will also touch a basis of graphics in MATLAB, while working with transformations of a plane.

<u>Theory</u>: The area of a parallelogram in ¡<sup>2</sup> built on non-parallel vectors <strong>v</strong><sub>1</sub>, <strong>v</strong><sub>2</sub>, and the volume of a parallelepiped in ¡<sup>3</sup> built on vectors <strong>v</strong><sub>1</sub>, <strong>v</strong><sub>2</sub>, <strong>v</strong><sub>3</sub>, which are not parallel to the same plane, is det <em>A</em> (or abs(det A)), where <em>A </em>=[<strong>v</strong><sub>1 </sub><strong>v</strong><sub>2</sub>] and <em>A </em>=[<strong>v</strong><sub>1 </sub><strong>v</strong><sub>2 </sub><strong>v</strong><sub>3</sub>], respectively.

(See Section 3.3 of the textbook for details.)

In this exercise, you will be given 2 vectors in ¡<sup>2 </sup>, <strong>v</strong><sub>1 </sub>and <strong>v</strong><sub>2 </sub>, and 3 vectors in ¡<sup>3</sup>, <strong>v</strong><sub>1</sub>, <strong>v</strong><sub>2</sub>, and <strong>v</strong><sub>3</sub>, on which a parallelogram and parallelepiped, respectively, may or may not be built.

**Create a function in MATLAB that begins with:

function D=areavol(A)




which takes as an input a matrix A, whose columns are the vectors on which a parallelogram or parallelepiped may possibly be built.

**First, your function has to check whether the given vectors are linearly independent – use the MATLAB built-in function <strong>rank </strong>to check if it is the case.

<u>If the vectors are not linearly independent</u>, a parallelogram in ¡<sup>2 </sup>or parallelepiped in ¡<sup>3</sup> cannot be built. In this case, the function outputs a corresponding message, which has to be specific to whether it is a parallelogram or a parallelepiped that cannot be built. It also assigns an empty output to D. Then, the program <u>terminates</u>.

<u>If the vectors are linearly independent</u>, the function calculates the area and the volume, D, and outputs each with the corresponding message:  “The area of the parallelogram is”

(output D) and

“The volume of the parallelepiped is”

(output D)

<u>Hint</u>: in order to display a correct message whether it is a parallelogram or parallelepiped, which can or cannot be built, and whether it is the area or the volume, you should keep a track on the number of rows (or columns) of A and use the conditional statement.

**Type in the Live Script format

**Print the function areavol:

type areavol




**Run the function D=areavol(A); on each of the following matrices (display the input matrices A):

<ul>

 <li>A=randi(10,2)</li>

 <li>A=fix(10*rand(3))</li>

 <li>A=magic(3)</li>

 <li>B=randi([-10,10],2,1); A = [B,3*B]</li>

 <li>X=randi([-10,10],3,1);Y=randi([-10,10],3,1);A=[X,Y,X-Y]</li>

</ul>

Notice: the matrices in (d) and (e) are created by using vectors.




In this exercise, you will be plotting figures in <em>x x</em><sub>1 2 </sub>-plane and consider their images under the transformations of a plane, such as, reflections and shear.




**First, create the standard matrices of the indicated transformations of the <em>x x</em><sub>1 2 </sub>-plane

(for help, please refer to the textbook, Section 1.9):

R1 (reflection across the <em>x</em><sub>1</sub>-axis) R2 (reflection across the <em>x</em><sub>2</sub>-axis)

VS (vertical shear with <em>k</em><sub>=</sub>2)

Output these matrices and <u>display</u> them in your Live Script<strong>.</strong>




**Create the function transf in MATLAB – the code is below:

function C=transf(A,E) C=A*E; x=C(1,:);y=C(2,:); plot(x,y) v=[-5 5 -5 5]; axis(v) end

%Analyze each line of the function transf and write comments in your Live Script.

**Print the function transf in your Live Script.

**Next, perform a sequence of the transformations starting with the unit square whose vertices are defined by the columns of the matrix E:

<em>E </em>=<sub></sub>00 10 11 01 00<sub></sub>

Proceed as follows:

**Type the set of commands given below and Run Section.

<table width="616">

 <tbody>

  <tr>

   <td width="616">E=[0 1 1 0 0;0 0 1 1 0];A=eye(2); hold on grid on</td>

  </tr>

 </tbody>

</table>

E=transf(A,E)

Your first outputs will be the original matrix E and the plot, which is the unit square with the vertices defined by the columns of E.




**Then, you will perform step-by-step a sequence of transformations – on each step, you will be assigning one of the matrices VS, R1, or R2 to the matrix A and running the function E=transf(A,E)until you obtain the figure below:

After you Run Section, you will receive the second figure, while the first one is held. The code will also output and display the new matrix E.




<u>Note</u>: make sure that you will have displayed in your Live Script all output matrices E and the final plot.




<h1>Part V. Cofactors, Determinants, and Inverse Matrices</h1>




In this part of the project, you will calculate a matrix of cofactors of a given <em>n n</em><sub>×</sub> matrix <strong>a </strong>and use it to compute the determinant and the inverse of an invertible matrix <strong>a</strong>.

<strong>Theory</strong>: 1) The determinant of a matrix <strong>a</strong> can be computed by using a cofactor expansion across any row or down any column of <strong>a</strong>. For the reference see Section 3.1 of the textbook and the lecture Module 13, Part II.

2) The inverse of an <em>n n</em><sub>×</sub> invertible matrix <strong>a</strong> can be computed by using a method based on the Cramer’s Rule. Specifically,

<strong>a</strong><sup>−</sup><sup>1 </sup><sub>= </sub><u><sup>1 </sup></u>adj <strong>a</strong>,  det<strong>a</strong>

where adj <strong>a</strong>denotes the <em>adjugate</em> (or classical <em>adjoint</em>) of a matrix <strong>a,</strong> which is the <u>transpose</u> of the matrix whose entries are cofactors of <strong>a </strong>.  (For the reference see Section 3.3 of the textbook.)




<strong>Exercise 6 </strong>(6 points)                                                                          <strong>Difficulty: Very Hard </strong>

<strong>Part 1 </strong>

** Create a function that begins with function C=cofactor(a) format compact




First, the function has to generate (<em>n</em><sub>−</sub>1)<sub>×</sub>(<em>n</em><sub>−</sub>1) matrices <em>A</em><em><sub>i j</sub></em> (<em>i </em><sub>=</sub>1:<em>n</em>, <em>j </em><sub>=</sub>1: )<em>n </em>: each <em>A</em><em><sub>i j</sub></em> is obtained from <strong>a</strong> by deleting row <em>i</em> and column <em>j</em>.

Then, it outputs an <em>n n</em><sub>×</sub> matrix

<em>C </em>=[<em>C i j</em>( , )](<em>i j</em>, =1:<em>n</em>),

whose entries are the cofactors calculated by the formulas <em>C i j</em>( , ) = −( 1)<em><sup>i</sup></em><sup>+ </sup><em><sup>j </sup></em>det(<em>A</em><em><sub>i j </sub></em>). <u>Note</u>: in this part, we use a MATLAB built-in function det on the matrices <em>A</em><em><sub>i j</sub></em> of the sizes

(<em>n</em>−1) (× <em>n</em>−1).

**Output and display the matrix C with the message ‘the matrix of cofactors is’  (display C).




<strong>Part 2 </strong>

** Create a function that will compute the determinant D of a matrix <strong>a</strong>.

The function begins with function D=determine(a,C) D=[]; n=size(a,1);




First, the function has to check if the determinant of <strong>a</strong> is a zero – use command <strong><em>rank</em></strong> – you cannot use a built-in MATLAB function <em>det</em> for this part.

**<u>If the determinant is a 0</u>  , the function outputs: ‘the determinant of the matrix is’

D=0

and the program terminates.




**<u>If the determinant is not a 0</u>, you will calculate cofactor expansions across the rows and down the columns of the matrix <strong>a</strong>.

First, store in your code an <em>n</em><sub>×</sub>2 matrix E, for example,

E=zeros(n,2);

Then, recalculate the columns of the matrix E in the following way: the <em>n</em> entries of the first column of E are the cofactor expansions across <em>n</em> <strong>rows</strong> of <strong>a</strong>, respectively, and the <em>n</em> entries of the second column of E are the cofactor expansions down <em>n</em><strong> columns</strong> of <strong>a</strong>, respectively.




**According to the theory, all entries of the matrix E have to be the same number, and we will verify it in our code. To do that, we will take the first entry E(1,1)as a reference, and check if each entry of the matrix E matches the reference value. You should use the function closetozeroroundoff with p=7 on each of the differences  E(1,1) – E(i,j), where i runs from 1 to <em>n</em> and j runs from 1 to 2. If at least one of the entry E(i,j) does not match the reference value E(1,1), we output a message ‘Something went wrong! and <u>terminate</u> the program with an empty output for D (which has been assigned previously).




**<u>If all entries of</u><u> E match</u><u> E(1,1)</u> (within the given precision), your function will continue with one more task: it will calculate the determinant using a built-in MATLAB function d=det(a);

and, then, it will verify that d matches E(1,1) – you should use here the function closetozeroroundoff with p=7.




**If d and   E(1,1) match, output D with a message ‘the determinant is’

D=E(1,1)

If d and E(1,1) do not match, output a message ‘Check the code!’ and, in this case, the empty output for D  will stay.




<u>Important</u>: please make sure that you will not receive empty outputs after running the function determine on the variables given below. Notice that the non-empty value for D will be used in the function which you will create next.

<strong> </strong>

<strong>Part 3 </strong>

Create a function that computes the matrix <em>B</em><sub>=</sub><strong>a</strong><sup>−</sup><sup>1</sup> for an <u>invertible</u> matrix <strong>a</strong>. It accepts as inputs: matrix C, which is the output of the function cofactor, and the value D, which is the non-empty output of the function determine.




**The function begins with: function B=inverse(a,C,D) B=[];




**First, the function has to check if the matrix <strong>a </strong>is invertible. You can either use the command <strong><em>rank</em></strong> to verify it directly or you can employ the output D of the function determine. <u>If <strong>a</strong> is not invertible</u>, output the corresponding message and <u>terminate</u> the code – the empty output for B will stay.

<u>If <strong>a</strong> is invertible</u>, output the corresponding message, and proceed with calculating the inverse of the matrix <strong>a</strong>, matrix B, by means of the formula

<em>B</em><sub>= </sub><u><sup>1 </sup></u>*transpose(<em>C</em>).

<em>D</em>

Here, D is a non-empty and non-zero output of the function determine and C is the matrix of cofactors, which is the output of the function cofactor.




Then, you will check whether your matrix B matches the output of the built-in MATLAB function <strong>inv.  </strong>

**First, output (<u>do not display</u>) the matrix F=inv(a);




**Next, use <em>closetozeroroundoff</em> function with the parameter p=7 to check if B and F match. If it is the case, output a message that ‘the inverse is calculated correctly and it is the matrix’

(display B).

If B and F do not match, output a message that can be something like ‘What is wrong?!’

<strong> </strong>

<strong>Part 4 </strong>

**Type the functions <em>closetozeroroundoff</em>, <em>cofactor</em><strong>, </strong><em>determine</em>, and <em>inverse</em> in the Live Script.




**For each of the matrices <strong>a</strong> in choices (a)-(e) below, run the functions in the following order:

C=cofactor(a)

D=determine(a,C)

B=inverse(a,C,D)




<table width="616">

 <tbody>

  <tr>

   <td width="616">(a)     a=diag([1,2,3,4])(b)     a=ones(4)(c)     a=magic(5) (d) a=magic(6) (e) a=hilb(4)</td>

  </tr>

 </tbody>

</table>

(Display the input matrices in your Live Script.)