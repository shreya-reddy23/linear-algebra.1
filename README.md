# linear algebra
 its a portfolio on linar algebra in enginnering applications
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Shreya — Linear Algebra Portfolio</title>
  <style>
    :root{
      --accent:#0b63ce; /* blue/white theme */
      --bg:#f6f9ff;
      --card:#ffffff;
      --muted:#6b7280;
      --maxw:980px;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{margin:0;background:var(--bg);color:#0f1724;line-height:1.5}
    .wrap{max-width:var(--maxw);margin:36px auto;padding:22px}
    header{display:flex;align-items:center;gap:18px}
    .brand{display:flex;flex-direction:column}
    .brand h1{margin:0;font-size:28px}
    .brand p{margin:0;color:var(--muted)}
    nav{margin-top:18px;display:flex;gap:10px;flex-wrap:wrap}
    .btn{padding:8px 12px;border-radius:8px;background:transparent;border:2px solid transparent;cursor:pointer;font-weight:600}
    .btn.primary{background:var(--accent);color:white}
    .card{transition:transform 0.3s ease, box-shadow 0.3s ease;/* existing animation */background:var(--card);padding:20px;border-radius:12px;box-shadow:0 6px 18px rgba(12,24,63,0.06);margin-top:18px}
    .grid{display:grid;grid-template-columns:1fr;gap:16px}
    @media(min-width:880px){.grid{grid-template-columns:1fr 320px}}
    .side{position:sticky;top:22px}
    h2{margin:0 0 10px 0}
    h3{margin:14px 0 8px 0}
    ul{padding-left:18px}
    .chapter{padding:14px;border-radius:10px;border:1px solid rgba(11,99,206,0.06);background:linear-gradient(180deg, rgba(11,99,206,0.02), transparent)}
    .code{font-family:monospace;background:#0b1220;color:#e6f0ff;padding:10px;border-radius:8px;overflow:auto}
    footer{margin-top:28px;text-align:center;color:var(--muted);font-size:14px}
    .tag{display:inline-block;padding:6px 10px;border-radius:999px;background:rgba(11,99,206,0.08);color:var(--accent);font-weight:600;margin-right:8px}
    .navlink{color:var(--accent);text-decoration:none;font-weight:600}
  @keyframes fadeIn{0%{opacity:0;transform:translateY(20px);}100%{opacity:1;transform:translateY(0);}}
    .card{animation:fadeIn 0.8s ease;transition:transform 0.3s ease, box-shadow 0.3s ease;} .card:hover{transform:translateY(-6px) scale(1.02);box-shadow:0 10px 24px rgba(12,24,63,0.12);}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div style="width:72px;height:72px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#3ca0ff);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:26px">SR</div>
      <div class="brand">
        <h1>Shreya — Automation & Robotics</h1>
        <p><strong>Linear Algebra — Shreya M</strong>, 3rd semester student pursuing Automation and Robotics. This portfolio covers core concepts from Chapter 1 to Chapter 3.</p>
        <nav>
          <a class="navlink" href="#chapter1">Chapter 1</a> ·
          <a class="navlink" href="#chapter2">Chapter 2</a> ·
          <a class="navlink" href="#chapter3">Chapter 3</a>
        </nav>
      </div>
    </header>

    <div class="grid">
      <main>
        <section id="chapter1" class="card chapter">
          <h2>Chapter 1 — Why Linear Algebra is Important for Engineering Students</h2>
          <p><strong>Overview:</strong> Linear algebra provides the language and tools for modeling and solving many engineering problems. It underpins systems that appear throughout automation and robotics: kinematics, control systems, signal processing, machine learning, computer vision, state estimation, and more.</p>

          <h3>Key reasons (short):</h3>
          <ul>
            <li><strong>Modeling with matrices:</strong> Systems of linear equations model networks, circuits, transformation of coordinates, and multi-variable systems.</li>
            <li><strong>Transforms & rotations:</strong> 2D/3D rotations, rigid-body transforms, and change of basis are matrix operations—essential in robotics kinematics and sensor fusion.</li>
            <li><strong>Efficient computation:</strong> Using vectors and matrices lets you write compact, fast code that leverages optimized linear algebra libraries (BLAS/LAPACK).</li>
            <li><strong>Optimization & estimation:</strong> Least-squares, Kalman filters, and many control algorithms are built on linear-algebraic foundations.</li>
            <li><strong>Machine learning:</strong> Models—from linear regression to neural networks—use vector spaces, dot-products, and matrix multiplications heavily.</li>
          </ul>

          <h3>Real‑world engineering examples</h3>
          <h3>Example: Solving a robotic arm position</h3>
          <p>Consider a 2‑joint robotic arm. If joint angles are θ₁ and θ₂ and link lengths are L₁ and L₂, the end‑effector position is:</p>
          <pre class="code">x = L1*cos(θ1) + L2*cos(θ1 + θ2)
y = L1*sin(θ1) + L2*sin(θ1 + θ2)</pre>
          <p>This can be written in matrix form, showing how linear algebra is used directly in kinematics.</p>
          <ul>
            <li><strong>Robot arm kinematics:</strong> Use matrices to represent joint rotations and compute end-effector positions.</li>
            <li><strong>State‑space control:</strong> Represent system dynamics with matrices and design controllers using eigenvalues/eigenvectors.</li>
            <li><strong>Computer vision:</strong> Image transforms, homographies and 3D reconstruction use linear algebra extensively.</li>
          </ul>

          <p class="code">Mini take-away: Practice solving linear systems, computing matrix factorizations, and visualizing vector geometry — they show up everywhere in automation & robotics.</p>
        </section>

        <section id="chapter2" class="card chapter">
          <h2>Chapter 2 — Gaussian Elimination & LU Decomposition</h2>
          <p><strong>Gaussian elimination (row reduction):</strong> A stepwise algorithm to solve linear systems A x = b by transforming the augmented matrix [A|b] to row‑echelon (and reduced row‑echelon) form using elementary row operations.</p>

          <h3>Algorithm steps (short)</h3>
          <ol>
            <li>Choose a pivot in the current column (ideally largest magnitude for numeric stability).</li>
            <li>Use the pivot row to eliminate entries below it in the same column.</li>
            <li>Repeat for the next column and row until triangular form is obtained.</li>
            <li>Back-substitute to find the solution vector x.</li>
          </ol>

          <h3>LU decomposition (why and how)</h3>
          <p>LU decomposition factors a matrix A into a product of a lower-triangular matrix L and an upper-triangular matrix U (A = L U), often with row permutation P such that P A = L U. Once A is decomposed, solving A x = b is faster because we solve L y = P b (forward substitution) then U x = y (back substitution).</p>

          <h3>Benefits for engineers</h3>
          <ul>
            <li>Solving multiple systems with the same A but different b becomes efficient.</li>
            <li>Many numerical libraries implement LU with partial pivoting for stability.</li>
            <li>Understanding factorization helps with numeric stability and error analysis in control and simulation.</li>
          </ul>

          <h3>Worked numerical example</h3>
          <p>Solve the system:</p>
          <pre class="code">2x + 3y -  z =  5
4x +  y + 5z = 10
-2x + 2y + 4z =  1</pre>
          <p>Using Gaussian elimination, we convert the augmented matrix into upper‑triangular form and then apply back‑substitution.</p>
          <p>LU decomposition produces:</p>
          <pre class="code">L = [[1,   0, 0],
     [2,   1, 0],
     [-1, -1, 1]]

U = [[2, 3, -1],
     [0, -5, 7],
     [0, 0, 2]]</pre>
          <h3>Short code example (conceptual)</h3>
          <pre class="code">// Solve A x = b via LU
// 1) compute P, L, U such that P A = L U
// 2) y = forward_solve(L, P*b)
// 3) x = back_solve(U, y)
</pre>

          <h3>Mini exercise</h3>
          <p>Solve a 3x3 system by hand using elimination, then compute its LU (with partial pivoting). Compare solutions to verify the decomposition.</p>
        </section>

        <section id="chapter3" class="card chapter">
          <h2>Chapter 3 — Vector Spaces & Linear Transformations</h2>
          <p><strong>Vector spaces:</strong> A vector space is a set of vectors closed under addition and scalar multiplication. Examples relevant to engineering: R^n (Euclidean vectors), polynomial spaces, and function spaces (signals).</p>

          <h3>Important concepts</h3>
          <ul>
            <li><strong>Basis & dimension:</strong> A set of linearly independent vectors that span the space. Dimension counts the minimum number of coordinates needed to describe any vector.</li>
            <li><strong>Subspace:</strong> Any subset that is itself a vector space (e.g., column space, null space of a matrix).</li>
            <li><strong>Rank & nullity:</strong> Rank = dimension of column space. Nullity = dimension of null space. Rank-nullity theorem links them.</li>
          </ul>

          <h3>Linear transformations</h3>
          <p>Linear transformations are functions T: V → W that preserve addition and scalar multiplication. In coordinates, every linear transformation corresponds to a matrix; composition corresponds to matrix multiplication.</p>

          <h3>Engineering intuition</h3>
          <h3>Example: Image transformation</h3>
          <p>A 2D image point (x, y) can be rotated by an angle θ using the transformation:</p>
          <pre class="code">[x']   [ cosθ  -sinθ ] [x]
[y'] = [ sinθ   cosθ ] [y]</pre>
          <p>This is a linear transformation represented by a matrix. Such transformations are used in computer vision, robotics mapping, and graphics.</p>
          <ul>
            <li>Change of basis simplifies problems: choose coordinates where the system is easier to analyze (diagonalization where possible).</li>
            <li>Eigenvalues/eigenvectors reveal modal behavior in dynamic systems (natural frequencies, principal directions).</li>
            <li>Projection onto subspaces is used in least-squares estimation and sensor fusion.</li>
          </ul>

          <p class="code">Practical tip: Visualize 2D vectors and linear maps to build geometric intuition — draw how a set of basis vectors transforms under a matrix.</p>
        </section>

      </main>

      <aside class="side">
        <div class="card">
          <h3>About</h3>
          <p><strong>Shreya</strong><br>Automation & Robotics student. This mini-portfolio covers core linear algebra topics you specified and includes conceptual explanations, small exercises, and pointers for practical use in engineering.</p>
          <p style="margin-top:8px"><span class="tag">Linear Algebra</span><span class="tag">Robotics</span></p>
        </div>

        <div class="card" style="margin-top:12px">
          <h3>How to use</h3>
          <ol>
            <li>Download this HTML file ("index.html").</li>
            <li>Open in a browser to preview locally.</li>
            <li>To publish: create a GitHub repo named <code>your-username.github.io</code> and upload this file as <code>index.html</code>.</li>
          </ol>
          <p style="font-size:13px;color:var(--muted);margin-top:8px">Need a PDF or separate slides for a presentation? Ask me and I will export versions.</p>
        </div>

        <div class="card" style="margin-top:12px">
          <h3>Contact</h3>
          <p style="margin:0">Email: <em>your-email@domain.com</em> (replace with yours)</p>
          <p style="margin-top:8px;color:var(--muted);font-size:13px">Want interactive demos (MATLAB/NumPy notebooks) or a GitHub-ready repo structure? I can generate them.</p>
        </div>
      </aside>
    </div>

    <footer>
      Created for <strong>Shreya</strong> — Automation & Robotics student. Good luck with your portfolio and viva!
    </footer>
  </div>
</body>
</html>
