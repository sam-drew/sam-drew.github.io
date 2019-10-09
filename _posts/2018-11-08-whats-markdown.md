---
layout: post
title: "What is Markdown, and why is it useful?"
---

Markdown is a file format that makes it pretty easy to make nice looking documents with little more than plaintext. It allows you to add formatting that is very similar to the basic features of HTML, without the need for knowledge of how to write HTML itself.  

The goal of markdown in my eyes is to make it easier for a person to get ideas down quickly and format them well with very little effort.  

Markdown was created in 2004 by [John Gruber](https://daringfireball.net) as a tool for people who don't know how to write HTML to produce web pages from plain text. It was originally published as a [syntax definition](https://daringfireball.net/projects/markdown/syntax) and a Perl script that would convert markdown to HTML.

>Markdown is a text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML).

What makes Markdown so great is that it uses punctuation you're already familiar with when defining the formatting. You don't have to worry about opening and closing tags as with HTML. This does however mean that there is only a small subset of HTML tools available for you to use within Markdown, but when you consider that the purpose of Markdown is to be an easy *writing* format rather than publishing format, this actually plays to your advantage.  

The original Markdown specification was not unambiguous, and as the specification has been extended and new parsers developed multiple styles have developed, and it has become less and less standardised. In 2014 a group of Markdown enthusiasts with extensive experience supporting and deploying Markdown came together to standardise the specification.

>We propose a standard, unambiguous syntax specification for Markdown, along with a suite of comprehensive tests to validate Markdown implementations against this specification.

This specification is known as [**CommonMark**](https://commonmark.org).

As previously stated, markdown uses simple punctuation syntax to format text. The examples below are taken from the [CommonMark website](https://commonmark.org/help/).  

<table>
	<thead>
		<th><strong>Type this...</strong></th>
		<th><strong>...or this</strong></th>
		<th><strong>HTML Output</strong></th>
	</thead>
	<tbody>
       <tr>                        
       	<td class="preformatted">*Italic*</td>
			<td class="preformatted second-example">_Italic_</td>
			<td><em>Italic</em></td>
		</tr>
		<tr>                        
			<td class="preformatted">**Bold**</td>
			<td class="preformatted second-example">__Bold__</td>
			<td><strong>Bold</strong></td>
		</tr>
		<tr>
			<td class="preformatted"># Heading 1</td>
			<td class="preformatted second-example">
			Heading 1<br>
			=========
			</td>
			<td>
				<h1 class="smaller-h1">Heading 1</h1>
			</td>
		</tr>
		<tr>
			<td class="preformatted">
			## Heading 2
			</td>
			<td class="preformatted second-example">
			Heading 2<br>
			---------
			</td>
			<td>
				<h2 class="smaller-h2">Heading 2</h2>
			</td>
		</tr>
		<tr>                        
			<td class="preformatted">
			[Link](http://a.com)
			</td>
			<td class="preformatted second-example">
			[Link][1]<br>
			⋮<br>
			[1]: http://b.org
			</td>
			<td><a href="https://commonmark.org/">Link</a></td>
		</tr>
		<tr>
			<td class="preformatted">
			![Image](http://url/a.png)
			</td>
			<td class="preformatted second-example">
			![Image][1]<br>
			⋮<br>
			[1]: http://url/b.jpg
			</td>
			<td>
				<img src="https://commonmark.org/help/images/favicon.png" width="36" height="36" alt="Markdown">
			</td>
		</tr>
		<tr>
			<td class="preformatted">
			&gt; Blockquote
			</td>
			<td class="preformatted second-example">
			&nbsp;
			</td>
			<td>
				<blockquote>Blockquote</blockquote>
			</td>
		</tr>
		<tr>
			<td class="preformatted">
				<p>
					* List<br>
					* List<br>
					* List
				</p>
			</td>
			<td class="preformatted second-example">
				<p>
					- List<br>
					- List<br>
					- List<br>
				</p>
			</td>
			<td>
				<ul>
					<li>List</li>
					<li>List</li>
					<li>List</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td class="preformatted">
				<p>
					1. One<br>
					2. Two<br>
					3. Three
				</p>
			</td>
			<td class="preformatted second-example">
				<p>
					1) One<br>
					2) Two<br>
					3) Three
				</p>
			</td>
			<td>
				<ol>
					<li>One</li>
					<li>Two</li>
					<li>Three</li>
				</ol>
			</td>
		</tr>
		<tr>
			<td class="preformatted">
			Horizontal Rule<br>
			<br>
			---
			</td>
			<td class="preformatted second-example">
			Horizontal Rule<br>
			<br>
			***
			</td>
			<td>
			Horizontal Rule
			<hr class="custom-hr">
			</td>
		</tr>
		<tr>
			<td class="preformatted">
			`Inline code` with backticks
			</td>
			<td class="preformatted second-example">
			&nbsp;
			</td>
			<td>
				<code class="preformatted">Inline code</code> with backticks
			</td>
		</tr>
		<tr>
			<td class="preformatted">
			```<br>
			# code block<br>
			print '3 backticks or'<br>
			print 'indent 4 spaces'<br>
			```
			</td>
			<td class="preformatted second-example">
				<span class="spaces">····</span># code block<br>
				<span class="spaces">····</span>print '3 backticks or'<br>
				<span class="spaces">····</span>print 'indent 4 spaces'
			</td>
			<td>
				<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code># code block
print '3 backticks or'
print 'indent 4 spaces'
</code></pre></div></div>
			</td>
		</tr>
	</tbody>
</table>

Markdown also supports writing raw HTML into the document, and *should* render it as written (this can depend on the parser you're using).  

As you can see, with a few simple pieces of syntax, it's possible to quickly produce well formatted and very easy to read documents using Markdown.  

Markdown files use the extension `.md` or `.markdown`.  

Markdown is used by and integrated with many of the services you probably already use, such as [GitHub](https://github.com), [Read the Docs](https://readthedocs.org/), [Stack Overflow](https://stackoverflow.com), and static site generators such as [Jekyll](https://jekyllrb.com) and [Hugo](https://gohugo.io). Markdown is also used by journalists, and has led to the creation of tools such as [Hemingway](https://hemingwayapp.com).  

Markdown is a brilliant tool that removes the clutter and distraction of having to use a word processor, whilst retaining just enough of the formatting power to allow you to be a more focussed and effective writer.

*Sam*
