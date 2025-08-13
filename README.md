# Expression Tools:

## [KBar3 (AE Plugin)](https://aescripts.com/kbar/)

>*Create custom toolbars unique to your workflows. Save time and clicks by putting your most used effects, presets and more at your fingertips. Multiple toolbars let you switch between different tasks and keep your productivity up. Focus on creativity, not digging through menus.*

---

## [AutoHotkey (Windows)](https://www.autohotkey.com/)

>*AutoHotkey is a free, open-source scripting language for Windows that allows users to easily create small to complex scripts for all kinds of tasks such as: form fillers, auto-clicking, macros, etc.*

---

## [Keyboard Maestro (Mac)](https://www.keyboardmaestro.com/main/)

>*Automate applications or web sites, text or images, simple or complex, on command or scheduled. You can automate virtually anything.*

### Follow these steps to quickly insert expressions

#### 1. **Save the expression to a directory of your choosing**

##### Example:

`~/Documents/After Effects/Expressions/name-of-expression.txt`

#### 2. **Create a new macro and give it a hotkey or hot string trigger**

- I like to use hot strings that use a hyphen as a leader (-) along with a 3 letter abbreviation of the desired expression:

##### Example: Invert Opacity

``
Abbreviation = inv
``
<br>
``
Final trigger = -inv
``

#### 3. **Add: *"Read a file"***

- Select the same path your expression is located: <br> `~/Documents/After Effects/Expressions/name-of-expression.txt`

- Set the file to `System Clipboard`

#### 4. **Add: *"Insert text by pasting"***

- Make sure you select `pasting` and **NOT** `typing`
    - Sometimes *insert text by typing* will move too fast for the command to keep up ending up in skipped letters and words. Pasting reduces the risk of something being missed

#### 5. Insert ***System Clipboard*** variable

- Follow this path `Insert Token > Clipboard > System Clipboard`
- This will insert a variable that looks like this: `%SystemClipboard%`

#### 6. **Add *"Delete Current System Clipboard"***
This will restore what was stored in the clipboard prior to inputing the expression. There are two ways you can achieve deleting the current clipboard:

##### Option 01

- Add `2` `Delete Current System Clipboard` actions
- Set both of the `Delete past clipboard` levels to `0`

##### Option 02 - More steps, but cleaner

- Add the `Repeat` action
- Add `1` `Delete Current System Clipboard` action inside the `Repeat`
- Set the `Delete past clipboard` level to `0`
- Set `Execute these actions [blank] times` to `2`

### ***That's it!***