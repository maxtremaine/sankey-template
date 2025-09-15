# sankey-template

A good place to start for making [Sankey Diagrams](https://en.wikipedia.org/wiki/Sankey_diagram).

## Income Statement Template

Take a look at [the Income Statement Template](https://github.com/maxtremaine/sankey-template/blob/main/income-statement-template.html) with inline documentation, also below.

```JavaScript

document.addEventListener('DOMContentLoaded', function() {

    // Set the number and positioning of columns, to be referenced by Accounts.
    const [col1, col2, col3, col4] = [20, 155, 290, 425]

    // This is a helper function, so you can size boxes relative to a reference Account.
    const relativeToRevenue = relativeBoxHeight(75, 100) 

    // This is the simplest account, with no associated line.
    Account('Revenue', '$75M')
        .position(col2, 50)
        .size(100)
        .render()

    // This is an account with a relative size and a manually placed line.
    Account('Subscriptions', '$45M')
        .position(col1, 25)
        .size(relativeToRevenue(45))
        .addLine(col1 + 30, 72, col2, 97)
        .render();

    // An arbitrary number of Accounts can be added.

});

```