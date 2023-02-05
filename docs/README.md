# Getting started

## Introduction
>The scripting engine being used in DropCheats' ARK product is AngelScript.<br>
You can read more about it [here](https://www.angelcode.com/angelscript/sdk/docs/manual/doc_script.html).

To use or create a script, create a file in `%appdata%` with the file extension `.sdc1`, such as `C:/Users/Unreal/AppData/Roaming/test.sdc1`
> ![Test script loaded in menu](https://i.imgur.com/tupEUx3.png)

After creating the file, refresh the scripts list in the menu, and your newly created script will appear.
Click `Load script` to load the script.

## Creating your first script
Lets render some text on the screen as our first script. To do so, there are so called `Callbacks` which the application will call to execute your code.
The most familiar one being `main`; it will get executed as soon as your script loads.<br>
However, DropCheats' ARK product also provides an `onRender` callback, which we will be using to render primitives on the screen. For more callbacks, take a look [here](/callbacks).

1. Let's get started by creating our script file `text.sdc1`.
2. Now, lets declare the `onRender` callback, which we will be putting our rendering code in later.
```clike
void onRender() {
    
}
```
3. To render text on the screen, lets invoke the `Render::Text` function. More about the arguments provided to the function here.
```clike
void onRender() {
    Render::Text(Fonts::getMenuTextFont(), Vector2(50, 50), Color(255, 255, 255, 255), Render::OUTLINE, "Hello World!");
}
```
4. Load the script and enjoy the fruits of it!
> ![First script loaded](https://i.imgur.com/KFCCBl2.png)

Obviously this is a very simple script, but hopefully it shows the potential. If you're interested, take a look around on this site. Everything the scripting engine supports is documented here.