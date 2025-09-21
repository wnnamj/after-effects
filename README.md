# Create Expression Shortcuts:

#### Notes:
	- Save all expressions to a directory of your choosing
	- I like to create hot strings using a hyphen as a leader `(-)` along with a 3 letter abbreviation of the desired expression

##### Directory Examples:

`Mac - ~/Documents/After Effects/Expressions/name-of-expression.txt`
<br>
`Windows - E:\projects\github\after-effects\expressions`

##### Example: Invert Opacity

`Abbreviation = inv`<br>`Final trigger = -inv`

## [AutoHotkey (Windows)](https://www.autohotkey.com/)

>*AutoHotkey is a free, open-source scripting language for Windows that allows users to easily create small to complex scripts for all kinds of tasks such as: form fillers, auto-clicking, macros, etc.*

#### Create a new script and use the following *[function](https://www.autohotkey.com/docs/v2/Functions.htm)* to make adding new expressions much easier
> Make sure to replace the directory to where you have your expressions saved. Mine are saved in my [After Effects GitHub](https://github.com/wnnamj/after-effects/tree/main/expressions) folder

#### Breakdown

- `FileRead` - *[FileRead](https://www.autohotkey.com/docs/v2/lib/FileRead.htm)* does exactly what it sounds like. It reads the contents of a file (a text file in our case)
- `expressionName` - This is the name of the expression text file excluding the `.txt` file extention

```
expression(expressionName) {
	Send FileRead("E:\projects\github\after-effects\expressions\" expressionName ".txt")
	Return
}
```

#### To add new expressions

- Create a hot string to call the function
	- Add the `x` character to make the action automatically fire and `c` to make the hot string case sensitive
- Inside double quotation marks, add the name of your expression file

##### Example:

```
:xc:-atf::expression("autofade")
```

### That's it!

Save and reload your new script and you are good to begin executing expressions wiith just a few keystrokes!

---

## [Keyboard Maestro (Mac)](https://www.keyboardmaestro.com/main/)

>*Automate applications or web sites, text or images, simple or complex, on command or scheduled. You can automate virtually anything.*


#### 1. Create a new macro

- No need to add a trigger yet

#### 2. Add: *"Read a file"*

- In the `Read file` property, create a variable named `expPath` by typing the following<br>`%Variable%expPath%`
- Set the file "to" property to  `Variable` and name the new variable `expression`

#### 3. Add: *"Insert text by pasting"*

- Make sure you select `pasting` and **NOT** `typing`
    - Pasting reduces the risk of something being missed. Inserting text by typing often moves too fast for the command to keep up. This ends up in skipped letters and words.

#### 4. Insert the *expression* variable

- Input in the following `%Variable%expression%`
- You can also follow this path `Insert Token > Variable > expression`

#### 5. Delete and exit
- **Add *"Delete Current System Clipboard"***
	- Set the `delete past clipboard` level to `0`
		- This will restore what was stored in the clipboard prior to inputing the expression.
- **Add *"Type a keystroke"***
	- Click the small drop down arrow and select `{ENTER}`.
	- This will simulate `{ENTER}` from a numpad to exit the expression editor

### How to add a new expression

#### 1. Create a new macro and give it a hotkey or hot string trigger

#### 2. Add: *"Set Variable to Text"*

- In the `set variable` field, add the `expPath` variable from before.
	- The variable should look like this `expPath` not this `%Variable%expPath%`
- In the box below,  input the same path to where your expression is located: <br> `~/Documents/After Effects/Expressions/name-of-expression.txt`

#### 3. Add: *"Execute Macro"*
- Find and select the macro we made above
	- To make things easier to find, I like to prepend macros I will use again with `func`, which stands for `function`

##### Example:

`func_newExpression`

### That's it!

---

## [KBar3 (AE Plugin)](https://aescripts.com/kbar/) - *Instructions coming soon!*

>*Create custom toolbars unique to your workflows. Save time and clicks by putting your most used effects, presets and more at your fingertips. Multiple toolbars let you switch between different tasks and keep your productivity up. Focus on creativity, not digging through menus.*
