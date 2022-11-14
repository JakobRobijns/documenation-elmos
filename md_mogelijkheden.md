(van https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

## Headings

To create a heading, add one to six <kbd>#</kbd> symbols before your heading text. The number of <kbd>#</kbd> you use will determine the size of the heading.

```markdown
# The largest heading
## The second largest heading
###### The smallest heading
```

When you use two or more headings, GitHub automatically generates a table of contents which you can access by clicking within the file header. Each heading title is listed in the table of contents and you can click a title to navigate to the selected section. 


## Styling text

You can indicate emphasis with bold, italic, strikethrough, subscript, or superscript text in comment fields and `.md` files.  

| Style | Syntax | Keyboard shortcut | Example | Output |
| --- | --- | --- | --- | --- |
| Bold | `** **` or `__ __`| <kbd>Command</kbd>+<kbd>B</kbd> (Mac) or <kbd>Ctrl</kbd>+<kbd>B</kbd> (Windows/Linux) | `**This is bold text**` | **This is bold text** |
| Italic | `* *` or `_ _`     | <kbd>Command</kbd>+<kbd>I</kbd> (Mac) or <kbd>Ctrl</kbd>+<kbd>I</kbd> (Windows/Linux) | `*This text is italicized*` | *This text is italicized* |
| Strikethrough | `~~ ~~` | | `~~This was mistaken text~~` | ~~This was mistaken text~~ |
| Bold and nested italic | `** **` and `_ _` | | `**This text is _extremely_ important**` | **This text is _extremely_ important** |
| All bold and italic | `*** ***` | | `***All this text is important***` | ***All this text is important*** |
| Subscript | `<sub> </sub>` | | `<sub>This is a subscript text</sub>` | <sub>This is a subscript text</sub> |
| Superscript | `<sup> </sup>` | | `<sup>This is a superscript text</sup>` | <sup>This is a superscript text</sup> |

## Quoting text

You can quote text with a <kbd>></kbd>.

```markdown
Text that is not a quote

> Text that is a quote
```

## Quoting code

You can call out code or a command within a sentence with single backticks. The text within the backticks will not be formatted. You can also press the <kbd>Command</kbd>+<kbd>E</kbd> (Mac) or <kbd>Ctrl</kbd>+<kbd>E</kbd> (Windows/Linux) keyboard shortcut to insert the backticks for a code block within a line of Markdown.

```markdown
Use `git status` to list all new or modified files that haven't yet been committed.
```


To format code or text into its own distinct block, use triple backticks.

<pre>
Some basic Git commands are:
```
git status
git add
git commit
```
</pre>


## Links

You can create an inline link by wrapping link text in brackets `[ ]`, and then wrapping the URL in parentheses `( )`. You can also use the keyboard shortcut <kbd>Command</kbd>+<kbd>K</kbd> to create a link.{% ifversion fpt or ghae > 3.3 or ghes > 3.3 or ghec %} When you have text selected, you can paste a URL from your clipboard to automatically create a link from the selection.{% endif %}

{% ifversion fpt or ghae > 3.5 or ghes > 3.5 or ghec %} You can also create a Markdown hyperlink by highlighting the text and using the keyboard shortcut <kbd>Command</kbd>+<kbd>V</kbd>. If you'd like to replace the text with the link, use the keyboard shortcut <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>V</kbd>.{% endif %}

`This site was built using [GitHub Pages](https://pages.github.com/).`


## Images

You can display an image by adding <kbd>!</kbd> and wrapping the alt text in `[ ]`. Then wrap the link for the image in parentheses `()`.

`![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)`

![Rendered Image](/assets/images/help/writing/image-rendered.png)


## Lists

You can make an unordered list by preceding one or more lines of text with <kbd>-</kbd> or <kbd>*</kbd>.

```markdown
- George Washington
- John Adams
- Thomas Jefferson
```


To order your list, precede each line with a number.

```markdown
1. James Madison
2. James Monroe
3. John Quincy Adams
```


### Nested Lists

You can create a nested list by indenting one or more list items below another item.

To create a nested list using the web editor on {% data variables.product.product_name %} or a text editor that uses a monospaced font, like [{% data variables.product.prodname_vscode %}](https://code.visualstudio.com/), you can align your list visually. Type space characters in front of your nested list item, until the list marker character (<kbd>-</kbd> or <kbd>*</kbd>) lies directly below the first character of the text in the item above it.

```markdown
1. First list item
   - First nested list item
     - Second nested list item
```


To create a nested list in the comment editor on {% data variables.product.product_name %}, which doesn't use a monospaced font, you can look at the list item immediately above the nested list and count the number of characters that appear before the content of the item. Then type that number of space characters in front of the nested list item.

In this example, you could add a nested list item under the list item `100. First list item` by indenting the nested list item a minimum of five spaces, since there are five characters (`100. `) before `First list item`.

```markdown
100. First list item
     - First nested list item
```


You can create multiple levels of nested lists using the same method. For example, because the first nested list item has seven characters (`␣␣␣␣␣-␣`) before the nested list content `First nested list item`, you would need to indent the second nested list item by seven spaces.

```markdown
100. First list item
     - First nested list item
       - Second nested list item
```


For more examples, see the [GitHub Flavored Markdown Spec](https://github.github.com/gfm/#example-265).

## Task lists


If a task list item description begins with a parenthesis, you'll need to escape it with <kbd>\\</kbd>:

`- [ ] \(Optional) Open a followup issue`

## Mentioning people and teams

You can mention a person or [team](/articles/setting-up-teams/) on {% data variables.product.product_name %} by typing <kbd>@</kbd> plus their username or team name. This will trigger a notification and bring their attention to the conversation. People will also receive a notification if you edit a comment to mention their username or team name. For more information about notifications, see "[About notifications](/github/managing-subscriptions-and-notifications-on-github/about-notifications)."

## Paragraphs

You can create a new paragraph by leaving a blank line between lines of text.


## Hiding content with comments

You can tell {% data variables.product.product_name %} to hide content from the rendered Markdown by placing the content in an HTML comment.

<pre>
&lt;!-- This content will not appear in the rendered Markdown --&gt;
</pre>

## Further reading

- [{% data variables.product.prodname_dotcom %} Flavored Markdown Spec](https://github.github.com/gfm/)
- "[About writing and formatting on GitHub](/articles/about-writing-and-formatting-on-github)"
- "[Working with advanced formatting](/articles/working-with-advanced-formatting)"
- "[Quickstart for writing on {% data variables.product.prodname_dotcom %}](/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)"
