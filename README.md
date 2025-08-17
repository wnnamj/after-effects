# Expression Tools:

## [AutoHotkey (Windows)](https://www.autohotkey.com/)

>*AutoHotkey is a free, open-source scripting language for Windows that allows users to easily create small to complex scripts for all kinds of tasks such as: form fillers, auto-clicking, macros, etc.*

---

## [Keyboard Maestro (Mac)](https://www.keyboardmaestro.com/main/)

>*Automate applications or web sites, text or images, simple or complex, on command or scheduled. You can automate virtually anything.*


### Save all expressions to a directory of your choosing

##### Example:

`~/Documents/After Effects/Expressions/name-of-expression.txt`

### **How to set things up**

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
- **Add *"Type a keystroke"*
	- Click the small drop down arrow and select `{ENTER}`.
	- This will simulate `{ENTER}` from a numpad to exit the expression editor

### How to add a new expression

#### 1. Create a new macro and give it a hotkey or hot string trigger
- I like to use hot strings that use a hyphen as a leader (-) along with a 3 letter abbreviation of the desired expression:

##### Example: Invert Opacity

``Abbreviation = inv``<br>``Final trigger = -inv``

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

## [KBar3 (AE Plugin)](https://aescripts.com/kbar/)

>*Create custom toolbars unique to your workflows. Save time and clicks by putting your most used effects, presets and more at your fingertips. Multiple toolbars let you switch between different tasks and keep your productivity up. Focus on creativity, not digging through menus.*

