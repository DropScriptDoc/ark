# Namespaces
This page lists the available namespaces that can be used in your scripts.

## Fonts
- Classes
    - [`Font`](/classes?id=font)
- Functions
    - `Font& GetMenuTextFont()`
        - Returns the font that's used for text in the menu.
    - `Font& GetMenuWindowTitleFont()`
        - Returns the font that's used for the menu window title.
    - `Font& GetMenuTitleFont()`
        - Returns the font that's used for the menu title.
    - `Font& GetEspFont()`
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
    - `Window& GetMainWindow()`
        - Returns the main GUI window.
    - `Window& AddWindow(const string& windowName, const string& statusBarText, const Vector2& pos, const Vector2& size)`
        - Adds a window to the GUI. Position and size are in absolute screen pixels.
    - `void SetWindowOpened(const Window& in, const bool opened)`
        - Opens or closes the specified window. Brings it to the foreground if opened.

## Input
- Functions
    - `bool KeyDown(int vKey)`
        - Returns whether or not the specified key is being held down. The available vKey codes are listed [here](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes).
    - `bool KeyPressed(int vKey)`
        - Returns whether or not the specified key was pressed. The available vKey codes are listed [here](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes).

## Memory
- Functions
    - The functions below dereference the specified address as the specified type.
        - `int8 ReadInt8(uint64 address)`
        - `int16 ReadInt16(uint64 address)`
        - `int ReadInt32(uint64 address)`
        - `int64 ReadInt64(uint64 address)`
        - `uint8 ReadUint8(uint64 address)`
        - `uint16 ReadUint16(uint64 address)`
        - `uint ReadUint32(uint64 address)`
        - `uint64 ReadUint64(uint64 address)`
        - `float ReadFloat(uint64 address)`
        - `double ReadDouble(uint64 address)`
        - `bool ReadBool(uint64 address)`
    - The functions below set the value at the specified address with the specified type.
        - `void WriteInt8(uint64 address, int8 value)`
        - `void WriteInt16(uint64 address, int16 value)`
        - `void WriteInt32(uint64 address, int value)`
        - `void WriteInt64(uint64 address, int64 value)`
        - `void WriteUint8(uint64 address, uint8 value)`
        - `void WriteUint16(uint64 address, uint16 value)`
        - `void WriteUint32(uint64 address, uint32 value)`
        - `void WriteUint64(uint64 address, uint64 value)`
        - `void WriteFloat(uint64 address, float value)`
        - `void WriteDouble(uint64 address, double value)`
        - `void WriteBool(uint64 address, bool value)`

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
    - `void PushClipRect(const Vector2& min, const Vector2& max, bool intersect = false)`
        - Pushes a new clipping rectangle. Every render call after this will be rendered inside of the rectangle. If intersect is true, the function will automatically clamp the new clipping rect to be inside the previous clipping rect.
    - `void PopClipRect()`
        - Pops the last clipping rectangle. The rendering rectangle is restored to what it was before the last clipping rectangle got pushed.
    - `void GetClipRect(float& x, float& y, float& w, float& h)`
        - Gets the currently active clipping rectangle.
    - `void Line(const Vector2& p1, const Vector2& p2, const Color& color, const float thickness = 1.f)`
        - Renders a line from point 1 to point 2, with the specified color and thickness.
    - `void Rectangle(const Vector2& min, const Vector2& max, const Color& color, const float rounding = 0.f, const int drawFlags = 0, const float thickness = 1.f)`
        - Renders a rectangle between the min and max points. Can optionally render a rounded rectangle. Example:
        ```angelscript
        Render::Rectangle(Vector2(100, 100), Vector2(200, 200), Color(255, 255, 255, 255), 8.f, Render::ROUND_CORNERS_TOP_LEFT | Render::ROUND_CORNERS_TOP_RIGHT | Render::ROUND_CORNERS_BOT_LEFT | Render::ROUND_CORNERS_BOT_RIGHT);
        ```
    - `void RectangleFilled(const Vector2& min, const Vector2& max, const Color& color, const float rounding = 0.f, const int drawFlags = 0)`
        - Renders a filled rectangle between the min and max points. Can optionally render a rounded rectangle.
    - `void RectangleFilledMultiColor(const Vector2& min, const Vector2& max, const Color& colorTopLeft, const Color& colorTopRight, const Color& colorBotLeft, const Color& colorBotRight)`
        - Renders a filled gradient rectangle between the min and max points. Can optionally render a rounded rectangle.
    - `void ShadowRectangle(const Vector2& min, const Vector2& max, const Color& color, const float thickness, const Vector2& offset, const float rounding = 0, const int drawFlags = 0)`
        - Renders a shadow rectangle between the min and max points.
    - `void TriangleFilled(const Vector2& p1, const Vector2& p2, const Vector2& p3, const Color& color)`
        - Renders a filled triangle with the specified points and color.
    - `void Circle(const Vector2& center, const float radius, const Color& color, const float thickness = 1.f)`
        - Renders a circle around the center point with the specified radius, color and thickness.
    - `void CircleFilled(const Vector2& center, const float radius, const Color& color)`
        - Renders a filled circle around the center point with the specified radius and color.
    - `void Arc(const Vector2& center, const float radius, const float arcMin, const float arcMax, const Color& color, float thickness = 1.f)`
        - Renders an arc around the center point with the specified radius, color and thickness. The arcs curvature can be controlled with arcMin and arcMax.
    - `void Text(const Fonts::Font& font, const Vector2& pos, const Color& color, int flags, const string& text)`
        - Renders text at the specified position with the specified color, using the specified font. The globals listed below can be used as flags. Example:
        ```angelscript
        Render::Text(Fonts::GetMenuTextFont(), Vector(100, 100), Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, "Hello World!");
        ```
    - `Vector2 TextSize(const Fonts::Font& font, const string& text)`
        - Returns the text size in pixels.
        ```angelscript
        Vector2 size = Render::TextSize(Fonts::GetMenuTextFont(), "Hello World!");
        ```
    - `Vector2 GetScreenSize()`
        - Returns the size of the screen in pixels.
    - `Texture& ImageToTexture(const array<uint8>& imageData)`
        - Creates a texture to render from an image byte array. Use [this](https://dropscriptdoc.github.io/image/) site to convert images to a byte array. Only JPG, PNG, TGA, BMP, PSD, HDR and PIC are supported. Take a look at [this](/examples?id=rendering-images) example.
    `void Texture(const Texture& texture, const Vector2& min, const Vector2& max, const Color& color, const float rounding = 0, const int flags = 0)`
        - Renders a texture within the specified bounds. Uses the same rounding flags as rectangles. Take a look at [this](/examples?id=rendering-images) example.
- Globals
    - `int CENTER_X`
        - Can be used with the `Render::Text` function. Centers the text horizontally.
    - `int CENTER_Y`
        - Can be used with the `Render::Text` function. Centers the text vertically.
    - `int ALIGN_RIGHT`
        - Can be used with the `Render::Text` function. Aligns the text to the right.
    - `int OUTLINE`
        - Can be used with the `Render::Text` function. Adds an outline to the text.
    - `int ROUND_CORNERS_TOP_LEFT`
        - Can be used with rectangles. Makes the top left corner rounded.
    - `int ROUND_CORNERS_TOP_RIGHT`
        - Can be used with rectangles. Makes the top right corner rounded.
    - `int ROUND_CORNERS_BOT_LEFT`
        - Can be used with rectangles. Makes the bot left corner rounded.
    - `int ROUND_CORNERS_BOT_RIGHT`
        - Can be used with rectangles. Makes the bot right corner rounded.

## Engine
- Functions
    - `uint64 FindObject(const string& fullObjectName)`
        - Returns a pointer to the static class casted as an uint64. Useful for actor filtering. Take a look at [this example](/examples?id=filtering-actors).