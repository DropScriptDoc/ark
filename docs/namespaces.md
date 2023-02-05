# Namespaces
This page lists the available namespaces that can be used in your scripts.

## Fonts
- Classes
    - [`Font`](/classes?id=font)
- Functions
    - `Font& getMenuTextFont()`
        - Returns the font that's used for text in the menu.
    - `Font& getMenuWindowTitleFont()`
        - Returns the font that's used for the menu window title.
    - `Font& getMenuTitleFont()`
        - Returns the font that's used for the menu title.
    - `Font& getEspFont()`
        - Returns the font that's used for the esp.

## Gui
- Classes
    - [`Groupbox`](/classes?id=groupbox)
    - [`Tab`](/classes?id=tab)
    - [`Window`](/classes?id=window)
    - [`Checkbox`](/classes?id=checkbox)
    - [`Slider`](/classes?id=slider)
    - [`Combobox`](/classes?id=combobox)
    - [`Listbox`](/classes?id=listbox)
    - [`Textbox`](/classes?id=textbox)
    - [`Button`](/classes?id=button)
    - [`Text`](/classes?id=text)
- Functions
    - `Window& getMainWindow()`
        - Returns the main GUI window.
    - `Window& addWindow(const string& windowName, const string& statusBarText, const Vector2& pos, const Vector2& size)`
        - Adds a window to the GUI. Position and size are in absolute screen pixels.

## Input
- Functions
    - `bool keyDown(int vKey)`
        - Returns whether or not the specified key is being held down. The available vKey codes are listed [here](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes).
    - `bool keyPressed(int vKey)`
        - Returns whether or not the specified key was pressed. The available vKey codes are listed [here](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes).

## Memory
The functions below dereference the specified address as the specified type.
- Functions
    - `int8 readInt8(uint64 address)`
    - `int16 readInt16(uint64 address)`
    - `int readInt32(uint64 address)`
    - `int64 readInt64(uint64 address)`
    - `uint8 readUint8(uint64 address)`
    - `uint16 readUint16(uint64 address)`
    - `uint readUint32(uint64 address)`
    - `uint64 readUint64(uint64 address)`
    - `float readFloat(uint64 address)`
    - `double readDouble(uint64 address)`
    - `bool readBool(uint64 address)`

## Modules
- Classes
    - [`Address`](/classes?id=address)
    - [`Module`](/classes?id=module)
- Functions
    - `Module& Main()`
        - Returns the main module. Which is `ShooterGame.exe` in the case of ARK.
    - `Module& Get(const string& name)`
        - Returns the module that has the specified name.

## Render
- Functions
    - `Vector2 getScreenSize()`
        - Returns the size of the screen in pixels.
    - `void Text(const Fonts::Font& font, const Vector2& pos, const Color& color, int flags, const string& text)`
        - Renders text at the specified position with the specified color, using the specified font. The globals listed below can be used as flags. Example:
        ```clike
        Render::Text(Fonts::getMenuTextFont(), Vector(100, 100), Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, "Hello World!");
        ```
- Globals
    - `int CENTER_X`
        - Can be used with the `Render::Text` function. Centers the text horizontally.
    - `int CENTER_Y`
        - Can be used with the `Render::Text` function. Centers the text vertically.
    - `int ALIGN_RIGHT`
        - Can be used with the `Render::Text` function. Aligns the text to the right.
    - `int OUTLINE`
        - Can be used with the `Render::Text` function. Adds an outline to the text.