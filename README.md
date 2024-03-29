# HTML-Lists-Parser-with-Nesting
Command to test parser:
```
$ .\run.bat 
```
Make sure [flex](http://gnuwin32.sourceforge.net/packages/flex.htm) and [bison](http://gnuwin32.sourceforge.net/packages/bison.htm) are installed propery before running the command

## Handled Cases:
- `<ol>` `<li>` Combination: 
```
<ol>
    <li>This is list item1</li>
</ol>
```
``` 
Output: Accepted
```
- `<ul><li>` Combination:
```
<ul>
    <li>This is list item1</li>
    <li>This is list item2</li>
</ul>
```
```
Output: Accepted
```
- ` <li>` With Attribute:
```
<ol>
    <li value="50">This is list item1</li>
</ol>
```
``` 
Output: Accepted
```
- Nesting:
```
<ol>
    <li>
        <ul>
            <li>one thing</li>
            <li>two things</li>
            <li>three things</li>
        </ul>
    </li>
    <li>
        <ul>
            <li>one thing</li>
            <li>two things</li>
            <li>Three things</li>
        </ul>
    </li>
</ol>
```
```
Output: Accepted
```

- Non closing li tag ` `
```
<ol>
    <li value="50">This is list item1
</ol>
```
```
Output: Invalid Syntax
```

- Non closing ol tag in nesting
```
<ol>
    <li>
        <ul>
            <li>one thing</li>
            <li>two things</li>
            <li>three things</li>
        </ul>
    </li>
    <li>
        <ul>
            <li>one thing</li>
            <li>two things</li>
            <li>Three things</li>
        </ul>
    </li>
```
```
Output: Invalid Syntax
```

## Cases Unhandled
- Global Attributes like- id, class etc.