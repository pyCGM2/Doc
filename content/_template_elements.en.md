---
title: "Elements"
date: 2018-12-29T11:02:05+06:00
weight: 5
draft: True
---

#### Heading example

Here is example of hedings. You can use this heading by following markdownify rules. For example: use `#` for heading 1 and use `######` for heading 6.

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

<hr>

##### Emphasis

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

<hr>

##### Link

[abs]({{< ref "CGM/CGM1.0" >}})
[rel]({{< relref "CGM/CGM1.0" >}})


[example with title]({{< relref "../Plots#emg-plot" >}})


[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

URLs and URLs in angle brackets will automatically get turned into links.
http://www.example.com or <http://www.example.com> and sometimes
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.themefisher.com
[1]: https://gethugothemes.com
[link text itself]: https://www.getjekyllthemes.com

<hr>

##### Paragraph

Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam nihil enim maxime corporis cumque totam aliquid nam sint inventore optio modi neque laborum officiis necessitatibus, facilis placeat pariatur! Voluptatem, sed harum pariatur adipisci voluptates voluptatum cumque, porro sint minima similique magni perferendis fuga! Optio vel ipsum excepturi tempore reiciendis id quidem? Vel in, doloribus debitis nesciunt fugit sequi magnam accusantium modi neque quis, vitae velit, pariatur harum autem a! Velit impedit atque maiores animi possimus asperiores natus repellendus excepturi sint architecto eligendi non, omnis nihil. Facilis, doloremque illum. Fugit optio laborum minus debitis natus illo perspiciatis corporis voluptatum rerum laboriosam.

<hr>

##### Ordered List

1. List item
2. List item
3. List item
4. List item
5. List item

<hr>

##### Unordered List

* List item
* List item
* List item
* List item
* List item

<hr>

#### Notice

{{< notice "note" >}}
  This is a simple note.
{{< /notice >}}

{{< notice "tip" >}}
  This is a simple tip.
{{< /notice >}}

{{< notice "info" >}}
  This is a simple info.
{{< /notice >}}

{{< notice "warning" >}}
  This is a simple info.
{{< /notice >}}



#### Notice bootswacth
<div class="container">
  <div class="alert alert-info" role="alert">
    
    Note `environment_37.yml` or `environment_38.yml` generates Python 3.7 (resp. 3.8) virtual environments named pycgm37 (resp. pycgm38)
  
  </div>
</div>


<hr>

#### Tab

{{< tabs >}}

  {{< tab "first" >}}
   This is first tab
  {{< /tab >}}

  {{< tab "second" >}}
  this is second tab
  {{< /tab >}}

  {{< tab "third" >}}
  this is third tab
  {{< /tab >}}

{{</ tabs >}}

<hr>

### Collapse

{{< collapse "collapse 1" >}}
  This is a simple collapse
{{< /collapse >}}

{{< collapse "collapse 2" >}}
  This is a simple collapse
{{< /collapse >}}

{{< collapse "collapse 3" >}}
  This is a simple collapse
{{< /collapse >}}

<hr>

##### Code and Syntax Highlighting

Inline `code` has `back-ticks around` it.

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```

```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```

<hr>

##### Blockquote

> This is a blockquote example.

<hr>

##### Inline HTML

You can also use raw HTML in your Markdown, and it'll mostly work pretty well.

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>


<hr>

##### Tables

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

<hr>

##### Image

![image](img-1.jpg)

<hr>

##### Youtube video

{{< youtube C0DPdy98e4c >}}



### Changelog label

{{< changelog "Added" >}}
{{</ changelog >}}

{{< changelog "Changed" >}}
{{</ changelog >}}

{{< changelog "Depricated" >}}
{{</ changelog >}}

{{< changelog "Removed" >}}
{{</ changelog >}}

{{< changelog "Fixed" >}}
{{</ changelog >}}

{{< changelog "Security" >}}
{{</ changelog >}}

{{< changelog "Unreleased" >}}
{{</ changelog >}}


### elements from bootwatch

<p class="text-danger">Notice the Calibration process, do not accept gap. Please crop or fill gaps of your trial</p>


<p class="text-primary">.text-primary</p>

<p class="text-secondary">.text-secondary</p>

<p class="text-success">.text-success</p>

<p class="text-danger">.text-danger</p>

<p class="text-warning bg-dark">.text-warning</p>

<p class="text-info bg-dark">.text-info</p>

<p class="text-light bg-dark">.text-light</p>

<p class="text-dark">.text-dark</p>

<p class="text-body">.text-body</p>

<p class="text-muted">.text-muted</p>

<p class="text-white bg-dark">.text-white</p>


<div class="alert alert-dismissible alert-warning">
  <button type="button" class="btn-close" data-bs-dismiss="alert"></button>
  <h4 class="alert-heading">Warning!</h4>
  <p class="mb-0">Best check yo self, you're not looking too good. Nulla vitae elit libero, a pharetra augue. Praesent commodo cursus magna, <a href="#" class="alert-link">vel scelerisque nisl consectetur et</a>.</p>
</div>