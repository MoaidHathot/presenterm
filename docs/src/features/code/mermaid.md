## Mermaid

[mermaid](https://mermaid.js.org/) snippets can be converted into images automatically in any code snippet tagged with 
the `mermaid` language and a `+render` tag:

~~~markdown
```mermaid +render
sequenceDiagram
    Mark --> Bob: Hello!
    Bob --> Mark: Oh, hi mark!
```
~~~

**This requires having [mermaid-cli](https://github.com/mermaid-js/mermaid-cli) installed**.

Note that because the mermaid CLI will spin up a browser under the hood, this may not work in all environments and can 
also be a bit slow (e.g. ~2 seconds to generate every image). Mermaid graphs are rendered asynchronously by a number of 
threads that can be configured in the [configuration file](../../configuration/settings.md#snippet-rendering-threads). 
This configuration value currently defaults to 2.

The size of the rendered image can be configured by changing:
* The `mermaid.scale` [configuration parameter](../../configuration/settings.md#mermaid-scaling).
* Using the `+width:<number>%` attribute in the code snippet.

For example, this diagram will take up 50% of the width of the window and will preserve its aspect ratio:

~~~markdown
```mermaid +render +width:50%
sequenceDiagram
    Mark --> Bob: Hello!
    Bob --> Mark: Oh, hi mark!
```
~~~

It is recommended to change the `mermaid.scale` parameter until images look big enough and then adjust on an image by 
image case if necessary using the `+width` attribute. Otherwise, using a small scale and then scaling via `+width` may 
cause the image to become blurry.

## Theme

The theme of the rendered mermaid diagrams can be changed through the following [theme](../themes/introduction.md) 
parameters:

* `mermaid.background` the background color passed to the CLI (e.g., `transparent`, `red`, `#F0F0F0`).
* `mermaid.theme` the [mermaid theme](https://mermaid.js.org/config/theming.html#available-themes) to use.

## Always render diagrams

If you don't want to use `+render` every time, you can configure which languages get this automatically via the [config 
file](../../configuration/settings.md#auto_render_languages).
