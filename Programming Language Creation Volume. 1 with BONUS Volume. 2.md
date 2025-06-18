---


---

<h1 id="programming-language-creation-volume.-1--introduction">Programming Language Creation Volume. 1:  Introduction</h1>
<h2 id="computers-language-binary">Computer’s Language: Binary</h2>
<p>Computers can’t understand the words we tell it. Like for example: You are an urdu speaker and you speak urdu in UK ( Funny moment btw ) The person you are talking to won’t understand what are we saying! Just like this, the computer can’t understand what we are saying, instead it uses a language known as <strong>Binary</strong>. It uses only 0s and 1s. Like, for example, 5 in Binary is is 101.</p>
<p>But, the problem comes over here! We, people, don’t usually talk in binary or we don’t usually understand binary! That is why <strong>Programming Languages</strong> are created! It translates our language, English, to Binary for the computer to understand!</p>
<p>But today, I am not going to explain about Programming Language. We are going to create our own so that we can Understand how they work!</p>
<h2 id="our-own-programming-language">Our Own Programming Language</h2>
<p>We will create a programming language named: <strong>GOL</strong> or <strong>G</strong> for short! This language will have a file with the end of <strong>name.gol</strong>. We will create a lot with this language!</p>
<pre class=" language-gol"><code class="prism  language-gol">VAR INT A 1
VAR INT B 3
SHOW A
SHOW B
</code></pre>
<p>This is a simple code to show two numbers 1 and 3. Very simple. Let’s implement this with C++!</p>
<h2 id="why-c">Why C++?</h2>
<p>C++ is a programming language, known for its speed! It is very great and is used worldwide! We will be using that language to create <strong>GOL</strong>.</p>
<h2 id="showing-text">1. Showing text!</h2>
<p>First we need a file structure!</p>
<pre><code>Programming Language/
  |
  |
  ----- main.cpp
  |
  ----- main.gol
</code></pre>
<p>Now that we can start, our code will always start like this!</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;vector&gt;</span></span>
<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	cout <span class="token operator">&lt;&lt;</span> <span class="token string">"Hello World!"</span><span class="token punctuation">;</span>
	<span class="token keyword">return</span> <span class="token number">0</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>This is a simple “Hello World!” Program which is used to test if your file is even working or not!</p>
<p>Let’s write some simple code in our .gol file like this:</p>
<pre class=" language-gol"><code class="prism  language-gol">SHOW HELLO WORLD
</code></pre>
<p>This is just a basic example of a simple “Hello World” Program. Our goal is to make this program work by the end of this volume!</p>
<p>Let’s start by erasing the <code>main()</code> code because we do not want that. Instead, we will read the file <code>main.gol</code> in our code. Let’s include another library in our file:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;fstream&gt;</span></span>
</code></pre>
<p>Now in our main function add this line:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">ifstream <span class="token function">File</span><span class="token punctuation">(</span><span class="token string">"main.gol"</span><span class="token punctuation">)</span>

string line <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span> <span class="token comment">// we will use it later!</span>
</code></pre>
<p>What this does is just read the file! Now we need to split this line in our <code>main.gol</code>. This splitting process is called <strong>Lexer</strong>.</p>
<h2 id="lexer">Lexer</h2>
<p>What is a Lexer, you might ask. Actually, it is the process in which we split a statement into a list of keywords! For example, for our <code>main.gol</code> program, the lexer will turn this:</p>
<pre class=" language-gol"><code class="prism  language-gol">SHOW HELLO WORLD
</code></pre>
<p>into:</p>
<pre class=" language-gol"><code class="prism  language-gol">{"SHOW", "HELLO", "WORLD"}
</code></pre>
<p>Let’s create this in C++. First we will create a new function outside of <code>main()</code>:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> <span class="token function">split</span><span class="token punctuation">(</span>string text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">// rest code is written below!</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Next let’s define this function! Let’s first start by adding a new string variable and also a new vector in it! Then we will use a for loop to iterate through the string!</p>
<pre class=" language-cpp"><code class="prism  language-cpp">vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> res <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
string i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">char</span> c <span class="token operator">:</span> text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">// code in next snippet</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Now, we have to see if our char <code>c</code> is a <code>" "</code> , if it is, we can just push the word and reset it back to <code>""</code>. We can do this by:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">	<span class="token keyword">if</span> <span class="token punctuation">(</span>c <span class="token operator">==</span> <span class="token string">' '</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
			i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		i <span class="token operator">+</span><span class="token operator">=</span> c<span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
</code></pre>
<p>And Lastly, we add:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">return</span> res<span class="token punctuation">;</span>
</code></pre>
<p>The full code for the functions is:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> <span class="token function">split</span><span class="token punctuation">(</span>string text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> res <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	string i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">char</span> c <span class="token operator">:</span> text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>c <span class="token operator">==</span> <span class="token string">' '</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
				i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
			i <span class="token operator">+</span><span class="token operator">=</span> c<span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">return</span> res<span class="token punctuation">;</span>	
<span class="token punctuation">}</span>
</code></pre>
<p>With this function, we are now able to split the statements in the file!!!</p>
<h2 id="final-thing-printing">Final Thing: Printing!</h2>
<p>Let’s do this final step. We now need to read each line step. Remember when we created a string <code>line</code>!  That is the trick here! We write this code to read each line!</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">while</span> <span class="token punctuation">(</span><span class="token function">getline</span><span class="token punctuation">(</span>File<span class="token punctuation">,</span> line<span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token comment">// now the function is reading line by line!</span>
<span class="token punctuation">}</span>
</code></pre>
<p>And now we will split each line into a list ( vector ) of strings!</p>
<pre class=" language-cpp"><code class="prism  language-cpp">vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> l <span class="token operator">=</span> <span class="token function">split</span><span class="token punctuation">(</span>line<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>And lastly we add some more logic to print what the user has written! We write:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"SHOW"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> l<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> l<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<p>And lastly, add this line!</p>
<pre class=" language-cpp"><code class="prism  language-cpp">cout <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
</code></pre>
<p>YAY! We have successfully created the <code>SHOW</code> in our language! The whole code is:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;vector&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;fstream&gt;</span></span>

<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>

vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> <span class="token function">split</span><span class="token punctuation">(</span>string text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> res <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	string i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">char</span> c <span class="token operator">:</span> text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>c <span class="token operator">==</span> <span class="token string">' '</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
				i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
			i <span class="token operator">+</span><span class="token operator">=</span> c<span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">return</span> res<span class="token punctuation">;</span>	
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	ifstream <span class="token function">File</span><span class="token punctuation">(</span><span class="token string">"main.gol"</span><span class="token punctuation">)</span>
	string line <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
	<span class="token keyword">while</span> <span class="token punctuation">(</span><span class="token function">getline</span><span class="token punctuation">(</span>File<span class="token punctuation">,</span> line<span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> l <span class="token operator">=</span> <span class="token function">split</span><span class="token punctuation">(</span>line<span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"SHOW"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> l<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				cout <span class="token operator">&lt;&lt;</span> l<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">&lt;&lt;</span> <span class="token string">" "</span><span class="token punctuation">;</span>	
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Now, if we run we will see:</p>
<pre class=" language-gol"><code class="prism  language-gol">HELLO WORLD
</code></pre>
<p>Noice! We have created a simple function for our programming language. Now we will meet in Volume. 2: <strong>Variables</strong>.</p>
<hr>
<h1 id="the-end-for-volume.-1">THE END FOR VOLUME. 1</h1>
<h1 id="programming-language-creation-volume.-2--variables">Programming Language Creation Volume. 2:  Variables</h1>
<h4 id="note-this-volume-will-be-produced-separately-when-the-bonus-event-is-completed.">Note: This volume will be produced separately when the BONUS event is completed.</h4>
<h2 id="a-little-recap">A Little Recap</h2>
<p>In the previous volume, we created a simple function to print some words! Now we will add the <strong>MOST BASIC</strong> and <strong>MOST USED</strong> feature which is Variables!</p>
<p>But before we do that, Let’s add something in our code. In the while loop add this logic under the Show one:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"//"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">continue</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>This is commenting, which is popular in many languages. It is easy to add.</p>
<h2 id="main-topic-variables">Main Topic: Variables</h2>
<p>Now let’s get to the main topic. Variables. It is used in all of the programs ( Almost ). Our language <strong>GOL</strong> has a very simple variable declaration method, which is:</p>
<pre class=" language-gol"><code class="prism  language-gol">VAR INT A 5	
</code></pre>
<p>It is easy to understand, right? But in case you don’t understand, let me explain:<br>
<code>VAR</code> tells our programming language that we are declaring a variable.<br>
<code>INT</code> tells the programming language that the variable we declare is a integer.<br>
<code>A</code> tells our programming language that the variable’s name is A.<br>
<code>5</code> tells our programming language that the value of the variable A is 5.</p>
<p>Very easy right? Now let’s program this! We will use a hashmap for this!</p>
<h2 id="what-is-a-hashmap">What is a HashMap?</h2>
<p>A hashmap is just like a vector, but the difference is that a vector store one value with 0-index. But a hashmap stores one value, but instead of 0-index it uses user’s indices. Let me tell you with an example:</p>
<p>This is a vector in C++:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">vector<span class="token operator">&lt;</span><span class="token keyword">int</span><span class="token operator">&gt;</span> example <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>And this is a Hashmap in C++:</p>
<pre class=" language-cpp"><code class="prism  language-cpp">unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">int</span><span class="token operator">&gt;</span> example <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">{</span><span class="token string">"One"</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token string">"Two"</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token string">"Three"</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">}</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p>A great example of this is an English dictionary book. It has every word with its meaning. Similarly, the map does the same thing.</p>
<h2 id="storing-the-variables">1. Storing the Variables</h2>
<p>First of all, let’s include the <code>unordered_map</code> library in our <code>main.cpp</code> file:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;vector&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;fstream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;unordered_map&gt;</span></span>
</code></pre>
<p>Next let’s make three <code>unordered_maps</code> named <code>storeInt</code>, <code>storeStr</code>, <code>storeBool</code> and one more <code>unordered_map</code> named <code>checking</code> in the start of the <code>main()</code> function:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">int</span><span class="token operator">&gt;</span> storeInt <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> string<span class="token operator">&gt;</span> storeStr <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">bool</span><span class="token operator">&gt;</span> storeBool <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">int</span><span class="token operator">&gt;</span> checking <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">{</span><span class="token string">"STR"</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token string">"INT"</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token string">"BOOL"</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">}</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Next, we need to check <code>VAR</code> detection in our while loop:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"VAR"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">int</span> check <span class="token operator">=</span> checking<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token comment">// rest of the code will be wriiten after some dialogue.</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Now we will switch cases for the check now!</p>
<h2 id="switch-cases">2. Switch Cases!</h2>
<p>Switch cases are just like if-else statements, but for only and ONLY integers.</p>
<p>So now let’s use those!</p>
<pre class=" language-cpp"><code class="prism  language-cpp">	<span class="token keyword">switch</span> <span class="token punctuation">(</span>check<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">case</span> <span class="token number">1</span><span class="token operator">:</span>
			storeStr<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">]</span> <span class="token operator">=</span> l<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token keyword">break</span><span class="token punctuation">;</span>
		<span class="token keyword">case</span> <span class="token number">2</span><span class="token operator">:</span>
			storeInt<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">]</span> <span class="token operator">=</span> l<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token keyword">break</span><span class="token punctuation">;</span>
		<span class="token keyword">case</span> <span class="token number">3</span><span class="token operator">:</span>
			storeBool<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">]</span> <span class="token operator">=</span> l<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
</code></pre>
<h2 id="changing-the-show-function">3. Changing the <code>SHOW</code> function</h2>
<p>Now we just change the <code>SHOW</code> function’s code that if the text in the argument is in the one of the <code>stores</code>:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"SHOW"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span>storeInt<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">!=</span> storeInt<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> storeInt<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>storeStr<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">!=</span> storeStr<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> storeStr<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>storeBool<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">!=</span> storeBool<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		cout <span class="token operator">&lt;&lt;</span> storeBool<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
		<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> l<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			cout <span class="token operator">&lt;&lt;</span> l<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">&lt;&lt;</span> <span class="token string">" "</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<p>And done!!!</p>
<p>It is very simple to implement. Now if we have variable to print we can do this by this now:</p>
<pre class=" language-gol"><code class="prism  language-gol">VAR INT A 5
SHOW A
</code></pre>
<p>And it should output:</p>
<pre><code>5
</code></pre>
<p>And done! Now here is the full code for it:</p>
<pre class=" language-cpp"><code class="prism  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;iostream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;vector&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;fstream&gt;</span></span>
<span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;unordered_map&gt;</span></span>

<span class="token keyword">using</span> <span class="token keyword">namespace</span> std<span class="token punctuation">;</span>

vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> <span class="token function">split</span><span class="token punctuation">(</span>string text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
	vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> res <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	string i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">char</span> c <span class="token operator">:</span> text<span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>c <span class="token operator">==</span> <span class="token string">' '</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
				i <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
			i <span class="token operator">+</span><span class="token operator">=</span> c<span class="token punctuation">;</span>
		<span class="token punctuation">}</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token operator">!</span>i<span class="token punctuation">.</span><span class="token function">empty</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		res<span class="token punctuation">.</span><span class="token function">push_back</span><span class="token punctuation">(</span>i<span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">return</span> res<span class="token punctuation">;</span>	
<span class="token punctuation">}</span>

<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">int</span><span class="token operator">&gt;</span> storeInt <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> string<span class="token operator">&gt;</span> storeStr <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">bool</span><span class="token operator">&gt;</span> storeBool <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	unordered_map<span class="token operator">&lt;</span>string<span class="token punctuation">,</span> <span class="token keyword">int</span><span class="token operator">&gt;</span> checking <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">{</span><span class="token string">"STR"</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token string">"INT"</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token string">"BOOL"</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">}</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
	ifstream <span class="token function">File</span><span class="token punctuation">(</span><span class="token string">"main.gol"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	string line <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">;</span>
	<span class="token keyword">while</span> <span class="token punctuation">(</span><span class="token function">getline</span><span class="token punctuation">(</span>File<span class="token punctuation">,</span> line<span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		vector<span class="token operator">&lt;</span>string<span class="token operator">&gt;</span> l <span class="token operator">=</span> <span class="token function">split</span><span class="token punctuation">(</span>line<span class="token punctuation">)</span><span class="token punctuation">;</span>
		<span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"SHOW"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			
			<span class="token keyword">if</span> <span class="token punctuation">(</span>storeInt<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">!=</span> storeInt<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				cout <span class="token operator">&lt;&lt;</span> storeInt<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>storeStr<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">!=</span> storeStr<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				cout <span class="token operator">&lt;&lt;</span> storeStr<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>storeBool<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">!=</span> storeBool<span class="token punctuation">.</span><span class="token function">end</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
				cout <span class="token operator">&lt;&lt;</span> storeBool<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
				<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">int</span> i <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> l<span class="token punctuation">.</span><span class="token function">size</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
					cout <span class="token operator">&lt;&lt;</span> l<span class="token punctuation">[</span>i<span class="token punctuation">]</span> <span class="token operator">&lt;&lt;</span> <span class="token string">" "</span><span class="token punctuation">;</span>
				<span class="token punctuation">}</span>
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"//"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">continue</span><span class="token punctuation">;</span>
		<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"VAR"</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
			<span class="token keyword">int</span> check <span class="token operator">=</span> checking<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
			<span class="token keyword">switch</span> <span class="token punctuation">(</span>check<span class="token punctuation">)</span> <span class="token punctuation">{</span>
				<span class="token keyword">case</span> <span class="token number">1</span><span class="token operator">:</span>
					storeStr<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">]</span> <span class="token operator">=</span> l<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
					<span class="token keyword">break</span><span class="token punctuation">;</span>
				<span class="token keyword">case</span> <span class="token number">2</span><span class="token operator">:</span>
					storeInt<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token function">stoi</span><span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
					<span class="token keyword">break</span><span class="token punctuation">;</span>
				<span class="token keyword">case</span> <span class="token number">3</span><span class="token operator">:</span>
					storeBool<span class="token punctuation">[</span>l<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token punctuation">(</span>l<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span> <span class="token operator">==</span> <span class="token string">"TRUE"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
					<span class="token keyword">break</span><span class="token punctuation">;</span>
			<span class="token punctuation">}</span>
		<span class="token punctuation">}</span>
		cout <span class="token operator">&lt;&lt;</span> <span class="token string">"\n"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<p>And that is it for the Volume. 2! We will meet again in Volume. 3: <strong>Advanced GOL Functions</strong>.</p>
<hr>
<h1 id="the-end-for-volume.-2">THE END FOR VOLUME. 2</h1>

