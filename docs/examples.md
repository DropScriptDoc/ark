# Example scripts
This page provides a few example scripts. If you've made a useful script and think it can help people understand the scripting language, let Unreal know and it might be added here.

## GUI Elements
```clike
bool drawText = false;
Color textColor = Color(255, 255, 255, 255);

void onRender() {
    if (drawText) {
        Fonts::Font@ menuTextFont = Fonts::getMenuTextFont();

        // Changing the size of an existing font
        float originalSize = menuTextFont.setSize(50.f);
        Render::Text(menuTextFont, Vector2(100, 100), textColor, Render::OUTLINE, "Example text");
        menuTextFont.setSize(originalSize);
    }
}

void main() {
    Gui::Tab@ scriptTab = Gui::getMainWindow().addTab("Script");
    Gui::Groupbox@ groupbox = scriptTab.addGroupbox("Script groupbox", Vector2(100, 100));
    Gui::Checkbox@ checkbox = groupbox.addCheckbox("Draw text", drawText);
    checkbox.addColorPicker("Text color", textColor);
}
```
> ![Creating and using GUI elements image](https://i.imgur.com/em6xkYT.png)

## Rendering Actors
```clike
void onActor(Actor& actor) { 
    Vector2 screenPos;
    if (actor.getLocation().toScreen(screenPos)) {
        Render::Text(Fonts::getEspFont(), screenPos, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, actor.getObjectName()); 
    }
}
```
> ![Rendering Actors](https://i.imgur.com/ipi5q5g.png)