


				<h2>Polymorphism</h2>
				<p>From type theory is the provision of a single interface to entities of different types</p>
				<h3>Types</h3>
				<ul>
					<li>
						<strong>Ad hoc polymorphism:</strong> when a function denotes different and potentially heterogeneous implementations depending
						on a limited range of individually specified types and combinations. Ad hoc polymorphism is supported in many languages
						using function overloading.</li>
					<li>
						<strong>Parametric polymorphism:</strong> when code is written without mention of any specific type and thus can be used transparently
						with any number of new types. In the object-oriented programming community, this is often known as generics or generic
						programming. In the functional programming community, this is often shortened to polymorphism.</li>
					<li>
						<strong>Subtyping (also called subtype polymorphism or inclusion polymorphism):</strong> when a name denotes instances of many
						different classes related by some common superclass.
					</li>
				</ul>
				<h3>Implementations</h3>
				<p>Polymorphism can be distinguished by when the implementation is selected: statically (at compile time) or dynamically
					(at run time, typically via a virtual function). This is known respectively as static dispatch and dynamic dispatch,
					and the corresponding forms of polymorphism are accordingly called static polymorphism and dynamic polymorphism.</p>
				<ul>
					<li>Static polymorphism executes faster, because there is no dynamic dispatch overhead, but requires additional compiler
						support. Further, static polymorphism allows greater static analysis by compilers (notably for optimization), source
						code analysis tools, and human readers (programmers).</li>
					<li>Dynamic polymorphism is more flexible but slower—for example, dynamic polymorphism allows duck typing, and a dynamically
						linked library may operate on objects without knowing their full type.</li>
					<li>Static polymorphism typically occursy in ad hoc polymorphism and parametric polymorphism, whereas dynamic polymorphism
						is usual for subtype polymorphism. However, it is possible to achieve static polymorphism with subtyping through more
						sophisticated use of template metaprogramming, namely the curiously recurring template pattern.</li>

					<li>Examples static: templates/generics, function overloading, macros</li>
					<li>Examples dynamic: duck typing, dynamic dispatch with vtables (subtyping) </li>
				</ul>

				<h3>Duck typing for polymorphism without (static) types</h3>
				<ul>
					<li>Duck typing is concerned with establishing the suitability of an object for some purpose, using the principle, "If it
						walks like a duck and it quacks like a duck, then it must be a duck." With normal typing, suitability is assumed to
						be determined by an object's type only. In duck typing, an object's suitability is determined by the presence of certain
						methods and properties (with appropriate meaning), rather than the actual type of the object.</li>
				</ul>

				<h2>Testing</h2>

				<h2>Agile software development</h2>
				<ul>
					<li>TDD</li>
					<li>BDD</li>
					<li>SCRUM</li>
				</ul>

				<h2>Design Patterns</h2>
				<ul>
					<li>Behavioral</li>
					<li>Structural</li>
					<li>Creational</li>
					<li>Concurrency</li>
				</ul>

				<h2>SOLID principles</h2>
				<ul>
					<li>Single responsability principle</li>
					<li>Open/close principle</li>
					<li>Liskov substituion principle</li>
					<li>Interface segregation principle</li>
					<li>Dependency inversion principle</li>
					<li>bonus: YAGNI, KISS</li>
				</ul>
				<h2>Design smells</h2>
				<ul>
					<li>Rigidity is the tendency of software to be difficult to change. </li>
					<li>Fragility is the tendency of software to break in many places when a single change is made. </li>
					<li>Immobility A design is immobile when it contains parts that could be useful in other systems, but the effort and risk
						of separating them from the original system are too great.
					</li>
					<li>Viscosity When faced with a change, developers often have several ways to implement the desired change.</li>
					<li>Needless repetition In short copy and pasting code throughout the system. </li>
					<li>Opacity Opacity is the tendency of a module to be difficult to understand. </li>
					<li>Needless complexity This may very well be the most important smell of bad design. </li>
				</ul>