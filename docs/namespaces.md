# Namespaces
This page lists the available namespaces that can be used in your scripts.

## Fonts
- Classes
    - [`Font`](/classes?id=font)
- Functions
    - [`Font& getMenuTextFont()`](/functions?id=fonts::getmenutextfont)
    - [`Font& getMenuWindowTitleFont()`](/functions?id=fonts::getmenutextfont)
    - [`Font& getMenuTitleFont()`](/functions?id=fonts::getmenutextfont)
    - [`Font& getEspFont()`](/functions?id=fonts::getmenutextfont)

## Gui
- Classes
    - [`Groupbox`]()
    - [`Tab`]()
    - [`Window`]()
    - [`Checkbox`]()
    - [`Slider`]()
    - [`Combobox`]()
    - [`Listbox`]()
    - [`Textbox`]()
    - [`Button`]()
    - [`Text`]()
- Functions
    - [`Window& getMainWindow()`]()
    - [`Window& addWindow(const string& windowName, const string& statusBarText, const Vector2& pos, const Vector2& size)`]()

## Input
- Functions
    - [`bool keyDown(int key)`]()
    - [`bool keyPressed(int key)`]()

## Memory
- Functions
    - [`int8 readInt8(uint64 address)`]()
    - [`int16 readInt16(uint64 address)`]()
    - [`int readInt32(uint64 address)`]()
    - [`int64 readInt64(uint64 address)`]()
    - [`uint8 readUint8(uint64 address)`]()
    - [`uint16 readUint16(uint64 address)`]()
    - [`uint readUint32(uint64 address)`]()
    - [`uint64 readUint64(uint64 address)`]()
    - [`float readFloat(uint64 address)`]()
    - [`double readDouble(uint64 address)`]()
    - [`bool readBool(uint64 address)`]()

## Modules
- Classes
    - [`Address`]()
    - [`Module`]()
- Functions
    - [`Module& Main()`]()
    - [`Module& Get(const string& name)`]()

## Render
- Functions
    - [`Vector2 getScreenSize()`]()
    - [`void Text(const Fonts::Font& font, const Vector2& pos, const Color& color, int flags, const string& text)`]()
- Globals
    - [`int CENTER_X`]()
    - [`int CENTER_Y`]()
    - [`int ALIGN_RIGHT`]()
    - [`int OUTLINE`]()