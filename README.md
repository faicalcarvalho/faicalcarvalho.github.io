# faicalcarvalho.github.io
Faical Carvalho's page

<header>
        <h1>faicalcarvalho.github.io</h1>
        <p>Faical Carvalho&#39;s page</p>


        <p class="view"><a href="https://github.com/faicalcarvalho">View My GitHub Profile</a></p>

      </header>
      <section>
        <h2>
<a id="welcome-to-github-pages" class="anchor" href="#welcome-to-github-pages" aria-hidden="true"><span class="octicon octicon-link"></span></a>About Myself</h2>

<p>I am a software architect, developer, manager, technical writer and teacher, with more than 30 years working for the IT industry. I have worked many years with the development and maintenance of remote operating centers, with applications in telecommunication, public and private transportation networks, mobility and emergency operation centers. I have also worked in the development and maintenance of firmware for embedded devices.</p>

<p>Currently, I am the Technology Manager of the Operations Center of Belo Horizonte (pop. 3 Million). Multiple public agencies work together at the Center to provide services such as mobility, security, emergency care, civil defense, public video surveillance, among others. As the CIO of this multi-agency Center, my responsibility is the maintenance and evolution of the systems and equipment which are the Center’s technological infrastructure, conducting technical and operational processes aiming at the dissemination and implementation of the characteristics of smart cities.</p>

<p>Parallel to my main activity, I've been studying and teaching (2 years+) JavaScript-related technologies:</p>
<ul>
    <li>Node.js</li>
    <li>Express.js</li>
	<li>MongoDB</li>
    <li>Mongoose</li>
	<li>Handlebars</li>
	<li>AngularJS</li>
</ul>
<p>The stack also includes <em>bootstrap</em> based html/css solutions.</p>

<h2>
<a id="designer-templates" class="anchor" href="#designer-templates" aria-hidden="true"><span class="octicon octicon-link"></span></a>An excerpt from <em>The Young Programmer</em></h2>

<p><small>This is an excerpt from my book, <em>The Young Programmer</em>. Original in Portuguese: <em>O Jovem Programador</em>. My intention here is to show some thoughts on teaching programming.</small></p>

<p>Programming and writing are similar tasks. The same attributes of a good text can also be used to characterize a good program. Clarity, accuracy, simplicity, objectivity, balance are principles that can be applied as quality criteria for both text production and programming.</p>

<p>Programming is a recent activity. Much of its learning is acquired through experience. Some practices are adopted and, over time, are considered inadequate. Others have been tested for years and are consolidated almost as principles. Among many fads and unnecessary complications, my experience confirms — through positive results — some practices which I present to you as recommendations or advices.</p>

<h3>Avoid using the compound statement</h3>
<p>All major programming languages have the compound statement — also called <em>block</em>. It uses the words <em>begin</em> and <em>end</em> to delimit two or more commands:</p>

<pre><code>begin
  <em>command1</em>;
  <em>command2</em>;
  ...
end
</code></pre>

<p>In the descendants of the C language, the commands are delimited by <em>{</em> and <em>}</em>:</p>

<pre><code>{
  <em>command1</em>;
  <em>command2</em>;
  ...
}
</code></pre>

<p>Obviously, I am not considering the compound statement or block that, in many languages, delimits the commands of a function or a procedure. I am referring to the command that is syntactically equivalent to any other, and, typically, is subordinated to other command. For example, one subordinated to an <em>if</em> statement:</p>

<pre><code>if (a < b) {
  <em>command1</em>;
  <em>command2</em>;
  ...
}
</code></pre>

<p>Or one subordinated to a <em>for</em> statement:</p>

<pre><code>for (i = 0; i < N; i++) {
  <em>command1</em>;
  <em>command2</em>;
  ...
}
</code></pre>

<p>Some authors recommend — in my opinion, mistakenly — that you should always use the compound statement, even if there is only one command inside of it. What I am recommending is just the opposite.</p>

<p>As far as I know, the use of the compound statement has never been questioned. So, here I am — perhaps for the first time — making this recommendation that, at first glance, may seem weird: avoid using the compound statement.</p>

<p>The compound statement gives us freedom. You cannot code without it — that is undeniable. I am, however, calling your attention to possible — and, in my experience, likely — overuses.</p>

<p>In this recommendation — as in others — I use the word "avoid". I am not rigid. In many cases, the best solution is to use the compound statement and period. However, if you, at the time of coding, have this recommendation in mind — avoid using the compound statement —, you will have the opportunity to verify, in that part where you are about to use a compound statement, if it would not be better to insert at that point a function call instead — a new function —, which you would create with the same commands, with the same functionality you would use inside the compound statement.<p>

<p>What I consider specially important is that halt, the pause, the moment you ask yourself: wouldn’t it be better to insert here, where I am writing this compound statement, a procedure or function call? This is what really matters. In most cases, calling a new routine instead of using a compound statement makes the code much more balanced, easier to read and maintain.</p>

<p>Here is an example, applied to the main part of the <em>random_figures</em> program, which we constructed in Chapter 4:</p>

<pre><code>{
  for (i = 0; i < NFIGS; i++) {
    set_brush_color(screen, any_color());
    x = random(SIDE);
    y = random(SIDE);
    z = random(SIDE div 10);
    switch (random(3)) {
      case 0: draw_rect(screen, x, y, x+z, y+z); break;
      case 1: draw_circle(screen, x, y, x+z, y+z); break;
      case 2: draw_triang(screen, x, y, x+z, y+z); break;
    }
  }
}
</code></pre>

<p>The compound statement associated to the <em>for</em> statement can be replaced by a new function — for example, one called <em>any_figure</em> — which draws a figure with randomly chosen shape and size. That is, the new routine would have the same functionality as the compound statement. The new main program would be as follows:

<pre><code>{
  for (i := 0; i < NFIGS; i++)
    any_figure(SIZE);
}
</code></pre>

<p>Note that reading the main program is easier. And the new function would be added to the program:</p>

<pre><code>function any_figure(size: integer) {
  var x, y, z: integer; 
  set_brush_color(screen, any_color()); 
  x := random(size); 
  y := random(size); 
  z := random(size div 10);
  switch (random(3)) {
    case 0: draw_rect(screen, x, y, x+z, y+z); 
    case 1: draw_circle(screen, x, y, x+z, y+z); 
    case 2: draw_triang(screen, x, y, x+z, y+z);
  }
}
</code></pre>

<p>This new procedure, now detached from the <em>for</em> statement, has certain autonomy, and may also be used in other parts of the program or in other programs.</p>

<p>Considering this small example you can infer the multiple applications of this recommendation.</p>

<h3>Avoid using a loop inside another loop</h3>

<p>This recommendation is a synthesis which brings many other benefits that improves program quality. The necessity of using a loop inside another loop happens very often. Naturally, it is something that is required by the solution of the problem. In other words, there is no way to avoid it. But we can solve such problems avoiding <em>explicitly</em> writing the code of a loop inside another one.</p>

<p>The basic idea is similar to the one to avoid using the compound statement. Whenever you are about to insert a loop inside another one, stop and think if it would not be more appropriate to transform the inner loop into a routine.</p>

<p>For example, you can transform this:</p>

<pre><code>lst := list_new(); 
while (anl_get_token() != TK_END) {
  // handle id list
  list_clear(lst);
  get_id_list(lst);
	
  // insert the fields 
  for (i = 0; i < list_size(lst); i++) {
    item = list_item_at(lst, i);
    lst_ins_field(item);
    symtab_ins(item);
    tam_ts(item); 
    tip_ts(item);
    smb_ts(item);
  }
}
</code></pre>

<p>into this:</p>

<pre><code>lst = list_new();
while (anl_get_token() != TK_END) {
  // handle id
  list list_clear(lst); 
  get_id_list(lst);
  
  // insert the field
  insert_fields(lst);
}
</code></pre>

<p>Note that this code is easier to read than the one with the two loops. The new routine, <em>insert_fields</em>, has the functionality of the previous inner loop:</p>

<pre><code>function insert_fields(var lst: list) {
  var i: integer; 
  var item: item_list;
  // insert the fields 
  for (i = 0; i < list_size(lst); i++) {
    item := list_item_at(lst, i);
    lst_ins_field(item);
    symtab_ins(item);
    tam_ts(item);
    tip_ts(item);
    smb_ts(item);
  }
}
</code></pre>

<p>As in the previous recommendation, the new routine should be created carefully, and you should determine which parameters are most suitable for it. Generally, the new routine fits as a natural division of the problem and the result is a better structured program.</p>

<p><small>(Full article, in Portuguese, can be seen at <a href="http://www.ojovemprogramador.com.br" class="user-mention">The Young Programmer</a>)</small></p>

<h3>
<a id="support-or-contact" class="anchor" href="#support-or-contact" aria-hidden="true"><span class="octicon octicon-link"></span></a>Contact</h3>

<p><a href="mailto:faicalcarvalho@gmail.com">faicalcarvalho@gmail.com</a><br/>Phone: +55 31 9116-5350</p>

