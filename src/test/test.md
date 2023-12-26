# Example Page


## Admonish

*See repo for code*

```admonish warning title="Attention"
This is an example of the mdbook-admonish plugin.
```

## Katex/Latex

This is an example of the mdbook-katex plugin.
```
$$\int_{0}^{\infty}\cos(x^2)dx$$
```
$$\int_{0}^{\infty}\cos(x^2)dx$$

## Collapsible blocks

```html
<details>
<summary><i><b>Collapse :</b></i></summary>
<div>
You can place any html here including pdf files. Markdown won't work though.
</div>
</details>
```
<details>
<summary><i><b>Collapse :</b></i></summary>
<div>
You can place any html here including pdf files. Markdown won't work though.
</div>
</details>

## Tables

```
| Tables  | Are     | Cool    |
|---------|---------|---------|
| Aren't  | They    | ?       |
```
| Tables  | Are     | Cool    |
|---------|---------|---------|
| Aren't  | They    | ?       |

## Links

```
Internal Links : [welcome](./welcome.md).

External Links : [mdBook](https://rust-lang.github.io/mdBook/).

Bare Links : <https://rust-lang.github.io/mdBook/>.

```

Internal Links : [welcome](./welcome.md).

External Links : [mdBook](https://rust-lang.github.io/mdBook/).

Bare Links : <https://rust-lang.github.io/mdBook/>.

## PDFs

This is an example of how to display pdf files.
```html
<div>
<object data="./sample.pdf" type="application/pdf" style="height:100vh;width:100%">
</object>
</div>
```

<div>
<object data="./sample.pdf" type="application/pdf" style="height:100vh;width:100%">
</object>
</div>

<details>
<summary><a href="./sample.pdf">Sample PDF</a></summary>
<div>
<object data="./sample.pdf" type="application/pdf" style="height:100vh;width:100%">
</object>
</div>
</details>

## Images

```html
![The Rust Logo](images/rust-logo-blk.svg)
```

![The Rust Logo](images/rust-logo-blk.svg)

