# Collapsible items

In Markdown, how to create _sections_ which can expand and collapse again like an accordion.


## Format

Here we use the `details` and `summary` HTML5 tags as HTML in Markdown, which works GitHub. No JavaScript or CSS needed.

```html
<details>
<summary>TITLE</summary>

BODY CONTENT

</details>
```


## Markdown and HTML

Here we use HTML in the title and Markdown in the body.

**HTML code:**

    <details>
    <summary><b>Preview title</b></summary>

    _Markdown is valid, but add empty lines to separate from the HTML tags._

    - Bullet
    - Points

    ```json
    {
        "codeblock": "demo"
    }
    ```

    </details>

<!-- Result omitted here as Jekyll can't handle it right. Though I can force it to HTML without Jekjyll and then add the result as HTML. -->


## Jekyll site

Example using [Jekyll][] templating. In particular, putting a codeblock inside the expandable section.

[Jekyll]: {% link cheatsheets/jekyll/index.md %}

**Sample Jekyll/Liquid code**

Here is the code:

{% raw %}

```liquid
<details>
<summary>Preview</summary>

{% highlight ruby %}
puts 'Expanded message'
{% endhighlight %}

</details>
```

{% endraw %}

**Sample rendered HTML**

_Using the code above in a Jekyll site, here is the result after building to plain HTML._

<details>
<summary>Preview</summary>
<figure class="highlight">
<pre><code class="language-ruby" data-lang="ruby">
<span class="nb">puts</span> <span class="s1">'Expanded message'</span>
</code></pre>
</figure>
</details>

<br>

**Sample HTML for displaying output**

_Here is the rendered result above shown in a code block below, for clarity. The only change was wrapping, for readability._

```html
<details>
<summary>Preview</summary>

<figure class="highlight">
    <pre>
        <code class="language-ruby" data-lang="ruby">
        <span class="nb">puts</span> <span class="s1">'Expanded message'</span>
        </code>
    </pre>
</figure>
```

**Note**

To explain the approach here - if you want to use Jekyll templating, Markdown does **not** get picked up here correctly. So if you want a codeblock in your expanded block, you need to use HTML or the `highlight` Liquid tag. Whether using triple backticks or indentation for a codeblock inside the details tag, those just end up being used literally.
