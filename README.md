# Hugo Shortcodes

[Hugo][hugo] provides a way to insert template snippets into Markdown to
support "rich content" better than plain markdown. By default, Hugo includes
[shortcodes][sc] for embedding tweets, youtube videos, and other content
without needing to add HTML snippets.

For tweets, you can add `{{< tweet 672818357582868480 >}}` into the post and
it'll render the HTML for the embed.

In this repo, I've got a few other shortcodes you can copy into the
`layouts/shortcodes/` directory to reference.


## The Docs

### code.html

Code highlighting through [highlight.js][hl] by adding the right CSS classes.

```
{{< code "python" >}}
import this
{{< /code >}}
```

```
<pre><code class="python">
import this
</code></pre>
```

### github.html

Auto-link to a github project, with the text of the link as the user/name.

```
{{< github "ryansb/hugo-shortcodes" >}}
```

```
<a href="https://github.com/ryansb/hugo-shortcodes">ruansb/hugo-shortcodes</a>
```

### stack.html

This one creates a "launch stack" button like this:
![](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png)
and links it to the template in a region you specify.

```
{{< stack
  name="StackOfCloudBlocks"
  bucket="files.mysite.com"
  key="infrastructure.template"
>}}
```

This code puts together the full URL, and can optionally take an AWS region to
launch templates worldwide. It outputs a button like this: 
<a style="text-decoration: none" href="https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=SelfCleaningStack&amp;templateURL=https://s3.amazonaws.com/demos.serverlesscode.com/2015-12-cloudformation-custom-resources%2fcfn-log-cleaner-stack.template">
  <img style="height: 1em" src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png" alt="Launch stack SelfCleaningStack">
</a>

[hugo]: http://gohugo.io/
[sc]: https://gohugo.io/extras/shortcodes/
[hl]: https://highlightjs.org/
