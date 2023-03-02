# MIT Course 18.065/18.0651, Spring 2023

This is a repository for the course [18.065: Matrix Methods in Data Analysis, Signal Processing, and Machine Learning](http://student.mit.edu/catalog/m18a.html#18.065) at MIT in Spring 2023.   See also [18.065 from spring 2018](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/) (MIT OpenCourseWare) for a previous version of this class.

**Instructor**: [Prof. Steven G. Johnson](http://math.mit.edu/~stevenj).

**Lectures**: MWF1 in 2-190. Handwritten [notes are posted](https://www.dropbox.com/s/zny0l2njkhe5a8c/18.065%20Spring%202023.pdf?dl=0), along with [video recordings (MIT only)](https://canvas.mit.edu/courses/18680/external_tools/595).

**Office hours (virtual):** Thursdays at 4pm [via Zoom](https://mit.zoom.us/j/95322064681?pwd=ZzB3eHllMXpuWnNqc0NaeXZvUXF2dz09).

**Textbook**: [*Linear Algebra and Learning from Data*](https://math.mit.edu/~gs/learningfromdata/) by Gilbert Strang (2019).  (Additional readings will be posted in lecture summaries below.)

**Resources**: [Piazza discussion forum](https://piazza.com/mit/spring2023/18065), [pset partners](https://psetpartners.mit.edu/).

**Grading**: 50% homework, 50% final project.

**Homework**: Biweekly, due Fridays (2/17, 3/3, 3/17, 4/7, 4/21, 5/5) [on Canvas](https://canvas.mit.edu/courses/18680).  You may consult with other students or any other resources you want, but must write up your solutions *on your own*.

**Exams**: None.

**Final project**: Due **May 15** [on Canvas](https://canvas.mit.edu/courses/18680).  You can work in **groups of 1–3** ([sign up on Canvas](https://community.canvaslms.com/t5/Student-Guide/How-do-I-join-a-group-as-a-student/ta-p/468)).
* **1-page** proposal **due Monday April 3** [on Canvas](https://canvas.mit.edu/courses/18680) (right after spring break), but you are encouraged to discuss it with Prof. Johnson earlier to get feedback.
* Pick a problem involving "learning from data" (in the style of the course, but not *exactly* the same as what's covered in lecture), and take it further: to numerical examples, to applications, to testing one or more solution algorithms.  Must include computations (using any language).
* Final report **due May 15**, as an 8–15 page academic paper in the [style template](https://template-selector.ieee.org/secure/templateSelector/format?publicationTypeId=1&titleId=154&articleId=1) of [IEEE Transactions on Pattern Analysis and Machine Intelligence](https://www.computer.org/csdl/journal/tp).
* Like a good academic paper, you should **thoroughly reference** the published literature (citing both original articles and authoritative reviews/books where appropriate \[rarely web pages\]), tracing the historical development of the ideas and giving the reader pointers on where to go for more information and related work and later refinements, with references cited throughout the text (enough to make it clear what references go with what results). (Note: you may re-use diagrams from other sources, but all such usage must be _explicitly credited_; not doing so is [plagiarism](http://writing.mit.edu/wcc/avoidingplagiarism).) See some [previous topic areas](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/pages/final-project/).

What followes is a *brief* summary of what was covered in each lecture, along with links and suggestions for further reading.  It is
*not* a good substitute for attending lecture, but may provide a
useful study guide.

## Lecture 1 (Feb 6)

* Syllabus (above) and introduction.
* ![18.065 overview diagram](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/d6b9603509fe7de36c57a0ed8ebd92d2_chart_300.jpg)
* Column space, basis, rank, rank-1 matrices, A=CR, and AB=∑(col)(row)
* See handwritten notes and lecture video linked above.

**Further reading**: Textbook 1.1–1.3. [OCW lecture 1](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-1-the-column-space-of-a-contains-all-vectors-ax/)


## Lecture 2 (Feb 8)

* Matrix multiplication by blocks and columns-times-rows.  Complexity: standard algorithm for (m×p)⋅(p×n) is [Θ(mnp): roughly proportional](https://en.wikipedia.org/wiki/Big_O_notation) to mnp for large m,n,p, regardless of how we rearrange it into blocks. (There also [exist theoretically better](https://en.wikipedia.org/wiki/Computational_complexity_of_matrix_multiplication), but highly impractical, algorithms.)
* Briefly reviewed the "famous four" matrix factorizations: [LU](https://en.wikipedia.org/wiki/LU_decomposition), [diagonalization XΛX⁻¹ or QΛQᵀ](https://en.wikipedia.org/wiki/Eigendecomposition_of_a_matrix), [QR](https://en.wikipedia.org/wiki/QR_decomposition), and the [SVD UΣVᵀ](https://en.wikipedia.org/wiki/Singular_value_decomposition).  QR and QΛQᵀ in the columns-times-rows picture, especially QΛQᵀ (diagonalization for real A=Aᵀ) as a sum of symmetric rank-1 projections.
* The [four fundamental subspaces](https://web.mit.edu/18.06/www/Essays/newpaper_ver3.pdf) for an m×n matrix A of rank r, mapping "inputs" x∈ℝⁿ to "outputs" Ax∈ℝᵐ: the "input" subspaces C(Aᵀ) (row space, dimension r) and its [orthogonal complement](https://en.wikipedia.org/wiki/Orthogonal_complement) N(A) (nullspace, dimension n–r); and the "output" subspaces C(A) (column space, dimension r) and its orthogonal complement N(Aᵀ) (left nullspace, dimension m–r).
* [pset 1](psets/pset1.ipynb), due Friday Feb 17

**Further reading**: Textbook 1.3–1.6. [OCW lecture 2](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-2-multiplying-and-factoring-matrices/).  If you haven't seen [matrix multiplication by blocks](https://www.math.ucdavis.edu/~linear/old/notes9.pdf) before, [here is a nice video](https://www.youtube.com/watch?v=KCUgWj5nhYc).

## *Optional* Julia Tutorial: Wed Feb 8 @ 5pm via Zoom

* Virtually via Zoom.  See [the recording](https://mit.zoom.us/rec/share/n2B1-t0NoGd5pr9gNBLgDYme159TstNttH5PLMcYPsEFEThCohKIJPsLrZXRhaZZ.LMM65H-ATiUFXkPf?startTime=1675893372000) (MIT only).

A basic overview of the Julia programming environment for numerical computations that we will use in 18.06 for simple computational exploration.   This (Zoom-based) tutorial will cover what Julia is and the basics of interaction, scalar/vector/matrix arithmetic, and plotting — we'll be using it as just a "fancy calculator" and no "real programming" will be required.

* [Tutorial materials](https://github.com/mitmath/julia-mit) (and links to other resources)

If possible, try to install Julia on your laptop beforehand using the instructions at the above link.  Failing that, you can run Julia in the cloud (see instructions above).

## Lecture 3 (Feb 10)

* Orthogonal bases and unitary matrices "Q".

Choosing the right "coordinate system" (= "right basis" for linear transformations) is a key aspect of data science, in order to reveal and simplify information.  The "nicest" bases are often orthonormal.  (The opposite is a *nearly* linearly dependent "ill-conditioned" basis, which can greatly distort data.)

Orthonormal bases ⟺ QᵀQ=I, hence basis coefficients c=Qᵀx from dot products.  QQᵀ is orthogonal projection onto C(Q).  A square Q with orthonormal columns is known as a ["orthogonal matrix"](https://en.wikipedia.org/wiki/Orthogonal_matrix) or (more generally) as a ["unitary matrix"](https://en.wikipedia.org/wiki/Unitary_matrix): it has Qᵀ=Q⁻¹ (*both* its rows and columns are orthonormal).  Qx preserves length ‖x‖=‖Qx‖ and dot products (angles) x⋅y=(Qx)⋅(Qy).  Less obviously: *any* square matrix that preserves length must be unitary.

Some important examples of unitary matrices:
* [2×2 rotation matrices](https://en.wikipedia.org/wiki/Rotation_matrix)
* the identity matrix I
* any [permutation matrix](https://en.wikipedia.org/wiki/Permutation_matrix) P which re-orders a vector, and is simply a re-ordering of the rows/cols of I
* [Hadamard matrices](https://en.wikipedia.org/wiki/Hadamard_matrix): unitary matrices Hₙ/√n where Hₙ has entries of ±1 only.  For n=2ᵏ they are easy to construct recursively, and are known as [Walsh–Hadamard transforms](https://en.wikipedia.org/wiki/Hadamard_transform).  (See also the Julia [Hadamard package](https://github.com/JuliaMath/Hadamard.jl).)
* discrete [Haar wavelets](https://en.wikipedia.org/wiki/Haar_wavelet), which are unitary after a diagonal scaling and consist of entries ±1 and 0.  They are a form of ["time-frequency analysis"](https://en.wikipedia.org/wiki/Time%E2%80%93frequency_analysis) because they reveal information about *both* how oscillatory a vector is ("frequency domain") and *where* the oscillations occur ("time domain").
* orthonormal eigenvectors can be found for any real-symmetric ("Hermitian") matrix A=Aᵀ: A=QΛQᵀ
* the [SVD](https://en.wikipedia.org/wiki/Singular_value_decomposition) A=UΣVᵀ of *any* matrix A gives (arguably) the "best" orthonormal basis U for C(A) and the "best" orthonormal basis V for C(Aᵀ), which reveal a lot about A.
* orthonormal eigenvectors can *also* be found for any *unitary* matrix!  (The proof is similar to that for Hermitian matrices, but the eigenvalues |λ|=1 in this case.) Often, unitary matrices are used to describe *symmetries* of problems, and their eigenvectors can be thought of as a kind of "generalized Fourier transform".  (All of the familar Fourier transforms, including Fourier series, sine/cosine transforms, and discrete variants thereof, can be derived in this way. For example, the symmetry of a circle gives the Fourier series, and the symmetry of a sphere gives a "spherical-harmonic transform".)  For example, eigenvectors of a [cyclic shift permutation](https://en.wikipedia.org/wiki/Circular_shift) give the [discrete Fourier transform](https://en.wikipedia.org/wiki/Discrete_Fourier_transform), which is famously computed using [FFT algorithms](https://en.wikipedia.org/wiki/Fast_Fourier_transform).

**Further reading**: Textbook section 1.5 (orthogonality), 1.6 (eigenproblems), and 4.1 (Fourier); [OCW lecture 3](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-3-orthonormal-columns-in-q-give-q2019q-i/). The fact that preserving lengths implies unitarity is not obvious, but is proved in various textbooks; a concise summary is [found here](https://math.stackexchange.com/questions/3313702/does-preservation-of-induced-norm-imply-unitarity).  The relationship between symmetries and Fourier-like transforms can be most generally studied through the framework of "group representation theory"; see e.g. textbooks on "group theory in physics" like [Inui et al. (1996)](https://www.amazon.com/Applications-Physics-Springer-Solid-State-Sciences/dp/3540604456).  Of course, there are whole books *just* on the discrete Fourier transform (DFT), *just* on wavelet transforms, etcetera, and you can find lots of material online at many levels of sophistication.

## Lecture 4 (Feb 13)

* Eigenproblems, diagonalization, complex inner products, and the spectral theorem.

Reviewed eigenvectors/eigenvalues Ax=λx, which make a square matrix act like a scalar λ.   For an m×m matrix A, you get m eigenvalues λₖ from the roots (possibly repeated) of the [characteristic polynomial](https://en.wikipedia.org/wiki/Characteristic_polynomial) det(A-λΙ), and you almost always get m independent eigenvalues xₖ (except in the very rare case of a [defective matrix](https://en.wikipedia.org/wiki/Defective_matrix)).

Went through the example of the 4×4 cyclic-shift permutation P from last lecture, and showed that P⁴x=x ⥰ λ⁴=1 ⥰ λ=±1,±i.  We can then easily obtain the corresponding eigenvectors, and put them into the "discrete Fourier transform" matrix F.

I then claimed that the eigenvectors (properly scaled) are orthonormal, so that F is unitary, but there is a catch: we need to **generalize our definition of "dot"/inner product** for complex vectors and matrices.   For complex vectors, the dot product x⋅y is `conj`(xᵀ)y (`conj`=[complex conjugate](https://en.wikipedia.org/wiki/Complex_conjugate)), *not* xᵀy.   And the length of a vector is then  ‖x‖² = x⋅x = ∑ᵢ|xᵢ|², which is always ≥ 0 (and = 0 only for x=0).   The ["adjoint"](https://en.wikipedia.org/wiki/Conjugate_transpose) `conj`(xᵀ) is sometimes denoted "xᴴ" (or x<sup>*</sup> in math, or x<sup>†</sup> in physics).   A unitary matrix is now more generally one for which QᴴQ=I, and we see that our Fourier matrix F is indeed unitary.  And unitary matrices still preserve lengths (and inner products) with the complex inner product.

If we do a **change of basis** x=Bc, then Ax=λx is transformed to Cc=λc, where C=B⁻¹AB.  C and A are called [similar matrices](https://en.wikipedia.org/wiki/Matrix_similarity), and we see that they are just the same linear operator in different bases; similar matrices always have identical eigenvalues, and eigenvectors transformed by a factor of B.

The most important change of basis for eigenproblems is changing to the *basis of eigenvectors* X, and showed that this gives the [diagonalizaton](https://en.wikipedia.org/wiki/Diagonalizable_matrix) X⁻¹AX=Λ ⟺ **A = XΛX⁻¹**.  However, this basis may be problematic in a variety of ways if the eigenvectors are nearly dependent (X is nearly singular or "ill-conditioned", corresponding to A being *nearly defective*).

The *nice* case of diagonalization is when you have **orthonormal eigenvectors** X=Q, and it turns out that this arises **whenever A commutes with its conjugate-transpose Aᴴ** (these are called [normal matrices](https://en.wikipedia.org/wiki/Conjugate_transpose)), and give **A=QΛQᴴ**.  Two important cases are:
* [Hermitian matrices](https://en.wikipedia.org/wiki/Hermitian_matrix) A=Aᴴ, and especially the special case of **real-symmetric matrices** (real A=Aᵀ) — not only are their eigenvectors orthogonal, but their eigenvalues λ are **real**.  In fact, if A is real-symmetric, then its *eigenvectors* are real too, and we can work with a purely real diagonalization A=QΛQᵀ.
* Unitary matrices Aᴴ=A⁻¹.  In this case, we can easily show that |λ|=1, and then prove orthogonality of eigenvectors from the fact that unitary matrices preserve inner products.

**Further reading** [OCW lecture 4](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-4-eigenvalues-and-eigenvectors/) and textbook section I.6.
* Complex numbers and vectors: See [18.06 lecture 26](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-26-complex-matrices-fast-fourier-transform/) on complex matrices.  This [brief review of complex numbers](https://web.stanford.edu/~boyd/ee102/complex-primer.pdf) (from Stephen Boyd at Stanford) is at about the level we need.  There are many more basic reviews, e.g. from [Khan academy](https://www.khanacademy.org/math/algebra2/x2ec2f6f830c9fb89:complex), that you can find online.
* Similar matrices are discussed in [18.06 lecture 28](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-28-similar-matrices-and-jordan-form/), and diagonalization is in [18.06 lecture 22](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-22-diagonalization-and-powers-of-a/).
* Hermitian (real-symmetric) matrices: [18.06 lecture 25](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-25-symmetric-matrices-and-positive-definiteness/).

## Lecture 5 (Feb 15)

* (Symmetric/Hermitian) positive definite ("SPD") matrices A=Aᵀ: λ > 0 ⟺ xᵀAx > 0 (for x ≠ 0) ⟺ A = BᵀB (B full column rank) ⟺ pivots > 0 (in Gaussian elimination / LU or [Cholesky](https://en.wikipedia.org/wiki/Cholesky_decomposition) factorization) ⟺ ...  (but it does *not* mean all entries of A are necessarily positive or vice versa!)
* BᵀB matrices arise in SVDs, least-squares, statistics (covariance matrices), and many other problems.
* Positive-definiteness of the [Hessian matrix](https://en.wikipedia.org/wiki/Hessian_matrix) Hᵢⱼ=∂²f/∂xᵢ∂xⱼ is the key test for determining whether x∈ℝⁿ is a [local minimum](https://en.wikipedia.org/wiki/Maximum_and_minimum) of f(x), since f(x+δ)=f(x)+∇fᵀδ + ½δᵀHδ + (higher-order).   For example, H=2A for the [convex](https://en.wikipedia.org/wiki/Convex_function) [quadratic](https://en.wikipedia.org/wiki/Quadratic_form) "bowl" function f(x)=xᵀAx+bᵀx
* Analogous definitions of "positive semidefinite" (> 0 replaced by ≥ 0) and negative definite/semidefinite (< 0 / ≤ 0).

**Further reading** [OCW lecture 5](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-5-positive-definite-and-semidefinite-matrices/) and textbook section I.7.   In Julia, the [`isposdef`](https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/#LinearAlgebra.isposdef) function checks whether a matrix is positive definite, and does so using a Cholesky factorization (which is just Gaussian elimination speeded up 2× for SPD matrices, and fails if it encounters a negative pivot).   See also [these lecture slides from Stanford](http://www.seas.ucla.edu/~vandenbe/133A/lectures/chol.pdf) for more properties, examples, and applications of SPD matrices.  See the [matrix calculus course at MIT](https://github.com/mitmath/matrixcalc) for a more general presentation of derivatives, gradients, and second derivatives (Hessians) of functions with vector inputs/outputs.

## Lecture 6 (Feb 17)

* "Reduced"/"compact" SVD A=UᵣΣᵣVᵣᵀ=∑σₖuₖvₖᵀ, "full" SVD A=UΣVᵀ, and "thin" SVD (what computers actually return, with zero singular values replaced by tiny roundoff errors).
* Uᵣ and Vᵣ as the "right" bases for C(A) and C(Aᵀ). Avₖ=σₖvₖ
* SVD and eigenvalues: U and V as eigenvectors of AAᵀ and AᵀA, respectively, and σₖ² as the positive eigenvalues.
* Deriving the SVD from eigenvalues: the key step is showing that AAᵀ and AᵀA share the same positive eigenvalues, and λₖ=σₖ², with eigenvectors related by a factor of A. From there you can work backwards to the SVD.
* [pset 1 solutions](psets/pset1sol.ipynb)
* [pset 2](psets/pset2.ipynb): Due March 3 at 1pm

**Further reading**: [OCW lecture 6](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-6-singular-value-decomposition-svd/) and textbook section I.8.  The [Wikipedia SVD article](https://en.wikipedia.org/wiki/Singular_value_decomposition).

## Lecture 7 (Feb 21)

* [SVD demo with image "compression"](https://nbviewer.org/github/mitmath/1806/blob/fall22/notes/SVD-intro.ipynb)
* [Low-rank approximation](https://en.wikipedia.org/wiki/Low-rank_approximation) and the Eckart–Young theorem.
* Vector [norms](https://en.wikipedia.org/wiki/Norm_(mathematics)) (ℓ², ℓ¹, and ℓ∞) and [Matrix norms](https://en.wikipedia.org/wiki/Matrix_norm).  Unitarily invariant norms, and unitary invariance of singular values.
* [Matrix completion], the ["Netflix problem"](https://en.wikipedia.org/wiki/Netflix_Prize), and the nuclear norm.

**Further reading**: Textbook sections I.9, I.11, III.5. [OCW lecture 7](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-7-eckart-young-the-closest-rank-k-matrix-to-a/) and [lecture 8](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-8-norms-of-vectors-and-matrices/).

## Lecture 8 (Feb 22)
* Mean, variance, and covariance.
* Diagonalizing the covariance matrix: [Principal components analysis (PCA)](https://en.wikipedia.org/wiki/Principal_component_analysis).
* [PCA demo](https://nbviewer.org/github/mitmath/1806/blob/fall22/notes/Statistics-and-PCA.ipynb)

**Further reading**: Textbook sections I.9, V.1, V.4.  [OCW lecture 7](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-7-eckart-young-the-closest-rank-k-matrix-to-a/) and [OCW lecture 20](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-20-definitions-and-inequalities/).

## Lecture 9 (Feb 24)

* [pseudo-inverse](https://en.wikipedia.org/wiki/Moore%E2%80%93Penrose_inverse) A⁺=VΣ⁺Uᵀ
* Least-squares: solve Ax≈b by minimizing ‖b-Ax‖ ⟺ solving AᵀAx̂=Aᵀb
* 4 methods for least squares: (1) Normal equations AᵀAx̂=Aᵀb (the fastest method, but least robust to roundoff errors etc); (2) orthogonalization A=QR ⟹ Rx̂=Qᵀb (much more robust, this is essentially what `A \ b` does in Julia for non-square `A`); (3) pseudo-inverse x̂=A⁺b ([`pinv(A)*b`](https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/#LinearAlgebra.pinv) in Julia; this lets you "regularize" the problem by dropping tiny singular values); (4) ["ridge" or "Tikhonov" regularization](https://en.wikipedia.org/wiki/Ridge_regression) (AᵀA + δ²I)⁻¹Aᵀb ⟶ x̂ as δ→0 (δ≠0 is useful to "regularize" ill-conditioned fitting problems where A has nearly dependent columns, making the solutions more robust to errors).
* [Least-squares demo](https://nbviewer.org/github/mitmath/1806/blob/fall22/notes/Least-Square%20Fitting.ipynb)

**Further reading:** Textbook section II.2 and [OCW lecture 9](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-9-four-ways-to-solve-least-squares-problems/).  Many advanced linear-algebra texts talk about the practical aspects of roundoff errors in QR and least-squares, e.g. *Numerical Linear Algebra* by Trefethen and Bau (the 18.335 textbook). A nice historical review can be found in the article [Gram-Schmidt orthogonalization: 100 years and more](https://doi.org/10.1002/nla.1839).  Rarely (on a computer) explicitly form AᵀA or solve the normal equations: it turns out that this greatly exacerbates the sensitivity to numerical errors (in 18.335, you would learn that it squares the [condition number](https://en.wikipedia.org/wiki/Condition_number)). Instead, we typically use the A=QR factorization and solve Rx̂=Qᵀb.  Better yet, just do `A \ b` (in Julia or Matlab) or the equivalent in other languages (e.g. [`numpy.linalg.lstsq`](https://numpy.org/doc/stable/reference/generated/numpy.linalg.lstsq.html)), which will use a good algorithm.   (Even professionals can [get confused about this](https://discourse.julialang.org/t/efficient-way-of-doing-linear-regression/31232/33?u=stevengj).)

## Lecture 10 (Feb 27)

* Training vs test data: [VMLS slides p. 294](https://web.stanford.edu/~boyd/vmls/vmls-slides.pdf#page=294)
* Conditioning: κ(A) = (max σ)/(min σ) is the [condition number](https://en.wikipedia.org/wiki/Condition_number) of a matrix A, and gives us a bound on the "amplification" ‖Δx‖/‖x‖ ≤ κ(a) ‖Δb‖/‖b‖ of the relative error from inputs (b) to outputs (x) when solving Ax=b (including least-squares).   "Ill-conditioned problems" (κ≫1) magnify noise and other errors, and typically require some **regularization** (e.g. dropping smallest σ's) that **trades off robustness for accuracy** ‖b-Ax‖.
* Ridge/Tikhonov/ℓ² regularization: minimize ‖b-Ax‖₂² + δ²‖x‖₂² for some *penalty* δ≠0 to push the solution towards smaller x.  (More generally, δ²‖Dx‖₂² for some matrix D.)  This gives (AᵀA+δ²I)x̂=Aᵀb, which is similar to A⁺b but replaces 1/σ with σ/(σ²+δ²).  Effectively, this drops small σ's, but doesn't require an SVD and generalizes to other types of penalties.  (Example: [VMLS slides pg. 346](https://web.stanford.edu/~boyd/vmls/vmls-slides.pdf#page=346).)
* Under-determined problems: for "wide" matrices, Ax=b has many solutions (we can add any N(A) vector to a solution).  A common way to pick a solution is to pick the **minimum-norm** solution: minimize ‖x‖₂ subject to Ax=b.  (It turns out that this gives x̂=A⁺b!)

**Further reading**: Training/test data: [VMLS section 13.2](https://web.stanford.edu/~boyd/vmls/vmls.pdf#page=270). Condition numbers: Strang exercises II.3, [OCW video lecture 10](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-10-survey-of-difficulties-with-ax-b/), and [these 18.06 notes](https://github.com/mitmath/1806/blob/master/notes/Conditioning.ipynb); a more in-depth treatment can be found in e.g. *Numerical Linear Algebra* by Trefethen and Bau (the 18.335 textbook).  Tikhonov regularization: Strang section II.2, OCW video lecture 10, [VMLS section 15.3](https://web.stanford.edu/~boyd/vmls/vmls.pdf#page=326).  Underdetermined minimum-norm solutions: Strang section II.2, [OCW video lecture 11](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/resources/lecture-11-minimizing-2016x2016-subject-to-ax-b/), [UIUC *Nonlinear Programming* lecture notes](https://faculty.math.illinois.edu/~mlavrov/docs/484-spring-2019/ch4lec4.pdf).

## Lecture 11 (Mar 1)

* Minimum-norm solutions x̂=A⁺b=Aᵀ(AAᵀ)⁻¹: smallest ‖x‖₂ for underdetermined problems Ax=b for "wide" A.
* Other common norms: ℓ¹ and ℓ<sup>∞</sup>, and sparsity with ‖x‖₁ norm ([LASSO regularization](https://en.wikipedia.org/wiki/Lasso_(statistics))).
* Avoid AᵀA: it squares the condition number κ(AᵀA)=κ(A)²
* Gram–Schmidt orthogonalization and QR factorization.

**Further reading**: Strang II.2, II.4.
