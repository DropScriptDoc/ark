# Classes
This page lists the available classes that can be used in your scripts.

## Color
- Constructors
    - `Color()`
        - Constructs an empty Color object.
    - `Color(const uint8 r, const uint8 g, const uint8 b, const uint8 a)`
        - Constructs a Color object and sets the r, g, b and a fields.
    - `Color(const Vector2& other)`
        - Constructs a Color object from another Color object.
- Destructors
    - `~Color()`
        - Destructs a Color object.
- Fields
    - `uint8 r`
    - `uint8 g`
    - `uint8 b`
    - `uint8 a`

## Font
`In namespace: Fonts`
- Methods
    - `float GetSize()`
        - Returns the size of the font.
    - `float SetSize(float newSize)`
        - Sets the size of the font.
    - `float GetRowHeight()`
        - Returns the row height of the font.

## Groupbox
`In namespace: Gui`
- Methods
    - `Text& AddText(const string& text)`
        - Adds the specified text to the next free space in the GUI.
    - `Button& AddButton(const string& label, int width, Gui::GuiButtonClb @clb)`
        - Adds a button to the next free space in the GUI. Width is a percentage of the available horizontal space. Example:
        ```angelscript
        groupbox.AddButton("Click me!", 100, function() { 
            // this code gets executed when the user clicks the button
        })
        ```
    - `Textbox& AddTextbox(const string& label, const string& value)`
        - Adds a textbox to the next free space in the GUI.
    - `Listbox& AddListbox(const string& label, const array<string>& elements, int& selectedIndex, const Vector2& size)`
        - Adds a listbox to the next free space in the GUI. Size is a percentage of the available space.
    - `Combobox& AddCombobox(const string& label, const array<string>& elements, int& selectedIndex)`
        - Adds a combobox to the next free space in the GUI.
    - `Slider& AddSlider(const string& label, float& value, float min, float max)`
        - Adds a slider to the next free space in the GUI.
    - `Checkbox& AddCheckbox(const string& label, bool& checked)`
        - Adds a checkbox to the next free space in the GUI.
    - `Groupbox& AddGroupbox(const string& label, const Vector2& size)`
        - Adds a groupbox to the next free space in the GUI. Size is a percentage of the available space.
    - `Tab& AddTab(const string& label)`
        - Adds a tab to the next free space in the GUI.

## Tab
`In namespace: Gui`
- Methods
    - `Text& AddText(const string& text)`
        - Adds the specified text to the next free space in the GUI.
    - `Button& AddButton(const string& label, int width, Gui::GuiButtonClb @clb)`
        - Adds a button to the next free space in the GUI. Width is a percentage of the available horizontal space. Example:
        ```angelscript
        groupbox.AddButton("Click me!", 100, function() { 
            // this code gets executed when the user clicks the button
        })
        ```
    - `Textbox& AddTextbox(const string& label, const string& value)`
        - Adds a textbox to the next free space in the GUI.
    - `Listbox& AddListbox(const string& label, const array<string>& elements, int& selectedIndex, const Vector2& size)`
        - Adds a listbox to the next free space in the GUI. Size is a percentage of the available space.
    - `Combobox& AddCombobox(const string& label, const array<string>& elements, int& selectedIndex)`
        - Adds a combobox to the next free space in the GUI.
    - `Slider& AddSlider(const string& label, float& value, float min, float max)`
        - Adds a slider to the next free space in the GUI.
    - `Checkbox& AddCheckbox(const string& label, bool& checked)`
        - Adds a checkbox to the next free space in the GUI.
    - `Groupbox& AddGroupbox(const string& label, const Vector2& size)`
        - Adds a groupbox to the next free space in the GUI. Size is a percentage of the available space.
    - `Tab& AddTab(const string& label)`
        - Adds a tab to the next free space in the GUI.

## Window
`In namespace: Gui`
- Methods
    - `bool IsOpen()`
        - Returns whether or not the window is opened.
    - `Text& AddText(const string& text)`
        - Adds the specified text to the next free space in the GUI.
    - `Button& AddButton(const string& label, int width, Gui::GuiButtonClb @clb)`
        - Adds a button to the next free space in the GUI. Width is a percentage of the available horizontal space. Example:
        ```angelscript
        groupbox.AddButton("Click me!", 100, function() { 
            // this code gets executed when the user clicks the button
        })
        ```
    - `Textbox& AddTextbox(const string& label, const string& value)`
        - Adds a textbox to the next free space in the GUI.
    - `Listbox& AddListbox(const string& label, const array<string>& elements, int& selectedIndex, const Vector2& size)`
        - Adds a listbox to the next free space in the GUI. Size is a percentage of the available space.
    - `Combobox& AddCombobox(const string& label, const array<string>& elements, int& selectedIndex)`
        - Adds a combobox to the next free space in the GUI.
    - `Slider& AddSlider(const string& label, float& value, float min, float max)`
        - Adds a slider to the next free space in the GUI.
    - `Checkbox& AddCheckbox(const string& label, bool& checked)`
        - Adds a checkbox to the next free space in the GUI.
    - `Groupbox& AddGroupbox(const string& label, const Vector2& size)`
        - Adds a groupbox to the next free space in the GUI. Size is a percentage of the available space.
    - `Tab& AddTab(const string& label)`
        - Adds a tab to the next free space in the GUI.

## Checkbox
`In namespace: Gui`
- Methods
    - `void AddColorPicker(const string& label, Color& color)`
        - Adds a color picker to the checkbox.
    - `void AddKeyPicker(int& vKey)`
        - Adds a key picker to the checkbox. The available vKey codes are listed [here](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes).

## Text
`In namespace: Gui`
- Methods
    - `void AddColorPicker(const string& label, Color& color)`
        - Adds a color picker to the text.
    - `void AddKeyPicker(int& vKey)`
        - Adds a key picker to the text. The available vKey codes are listed [here](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes).

## Textbox
`In namespace: Gui`
- Methods
    - `void SetMaxStringLength(int length)`
        - Sets the maximum length of the string in the textbox.
    - `void SetStringNumericOnly(bool numericOnly)`
        - Sets whether or not only numeric characters are allowed in the string of the textbox.

## Slider
`In namespace: Gui`<br>
This class is not used for anything at the moment.

## Combobox
`In namespace: Gui`<br>
This class is not used for anything at the moment.

## Listbox
`In namespace: Gui`<br>
This class is not used for anything at the moment.

## Button
`In namespace: Gui`<br>
This class is not used for anything at the moment.

## Vector2
- Constructors
    - `Vector2()`
        - Constructs an empty Vector2 object.
    - `Vector2(const float x, const float y)`
        - Constructs a Vector2 object and sets the x and y fields.
    - `Vector2(const Vector2& other)`
        - Constructs a Vector2 object from another Vector2 object.
- Destructors
    - `~Vector2()`
        - Destructs a Vector2 object.
- Fields
    - `float x`
    - `float y`

## Vector3
- Constructors
    - `Vector3()`
        - Constructs an empty Vector3 object.
    - `Vector3(const float x, const float y, const float z)`
        - Constructs a Vector3 object and sets the x, y and z fields.
    - `Vector3(const Vector3& other)`
        - Constructs a Vector3 object from another Vector3 object.
- Destructors
    - `~Vector3()`
        - Destructs a Vector3 object.
- Methods
    - `bool ToScreen(Vector2& screenPosition)`
        - Converts the 3D world position to a position on the screen. Example:
        ```angelscript
        Vector2 screenPosition;
        if (worldPosition.ToScreen(screenPosition)) {
            // do something with the screen position
        }
        ```
- Fields
    - `float x`
    - `float y`
    - `float z`

## Address
`In namespace: Modules`
- Constructors
    - `Address()`
        - Constructs an empty Address object.
    - `Address(const uint64 address, const Module@ module)`
        - Constructs an Address object and sets the address and module fields.
    - `Address(const Address& other)`
        - Constructs an Address object from another Address object.
- Destructors
    - `~Address()`
        - Destructs an Address object.
- Methods
    - `Address Absolute(uint8 offset = 0)`
        - Adds a dereferenced signed integer at the specified offset to the address and returns it in a new Address object. Useful for pattern scanning. The responsible C++ code looks somewhat like this.
        ```angelscript
        int relative_offset = *(signed int*)(this->address + offset);
		this->address += offset + sizeof(signed int) + relative_offset;
        ```
    - `Address Add(int64 value)`
        - Adds the specified value to the address, and returns it in a new Address object.
    - `Address FindPattern(const string& idaStylePattern)`
        - Finds the specified IDA style pattern in memory, and returns it in a new Address object. Example:
        ```angelscript
        address = address.FindPattern("48 8D 05 ? ? ? ? 48 89 1D");
        ```
    - `Address Reference(int idx = 0)`
        - Finds a reference in memory to the address at the specified idx, and returns it in a new Address object.
    - `uint64 ToUint64()`
        - Returns the raw uint64 address.
    - `Module& GetModule()`
        - Returns the underlying module.

## Module
`In namespace: Modules`
- Methods
    - `Address FindPattern(const string& idaStylePattern, uint64 start = 0, uint64 end = 0)`
        - Finds the specified IDA style pattern in memory (within the start and end bounds if specified), and returns it in a new Address object. Example:
        ```angelscript
        Address address = Modules::Main().FindPattern("48 8D 05 ? ? ? ? 48 89 1D");
        ```
    - `uint64 GetStart()`
        - Returns the location in memory where the module starts.
    - `uint64 GetEnd()`
        - Returns the location in memory where the module ends.
    - `string GetName()`
        - Returns the name of the module.

## Actor
- Methods
    - `Vector3 GetLocation()`
        - Returns the 3D location of the actor in the worlds.
    - `bool IsA(const uint64 compareClass)`
        - Returns whether or not the actor inherits from the compare class. Useful for actor filtering. Take a look at [this example](/examples?id=filtering-actors).
    - `string GetString(const string& className, const string& fieldName)`
        - Returns the FString value stored at the specified field in the specified class. Use [this site](https://ark.dumps.host) to find the class and field names. (It expects the class name without the A or U prefix.) Example:
        ```angelscript
        string dinoName = dino.GetString("PrimalCharacter", "DescriptiveName");
        ```
    - `int GetInt(const string& className, const string& fieldName)`
        - Returns the integer value stored at the specified field in the specified class. Use [this site](https://ark.dumps.host) to find the class and field names. (It expects the class name without the A or U prefix.) Example:
        ```angelscript
        int targetingTeam = actor.GetInt("Actor", "TargetingTeam");
        ```
    - `string GetObjectName()`
        - Returns the Unreal Engine object name.
    - `string GetFullObjectName()`
        - Returns the full Unreal Engine object name.
    - `uint64 GetAddress()`
        - Returns the address of the Actor in memory. Useful to perform read and write operations on it.