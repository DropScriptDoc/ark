# Example scripts
This page provides a few example scripts. If you've made a useful script and think it can help people understand the scripting language, let Unreal know and it might be added here.

## GUI Elements
```angelscript
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

## Creating a toggleable Window
```angelscript
Gui::Window@ scriptWindow = null;
void main() {
    Vector2 windowSize = Vector2(600, 400);
    Vector2 windowPos = Render::getScreenSize();
    windowPos.x = (windowPos.x - windowSize.x) / 2;
    windowPos.y = (windowPos.y - windowSize.y) / 2;

    @scriptWindow = Gui::addWindow("Script window", "This window was created by a script.", windowPos, windowSize);
}

void onRender() {
    // VK_F1 = 0x70
    if (Input::keyPressed(0x70)) {
        Gui::setWindowOpened(scriptWindow, !scriptWindow.isOpen());
    }
}
```
> ![Creating a toggleable Window](https://i.imgur.com/KQvyYJm.png)

## Rendering Actors
```angelscript
void onActor(Actor& actor) { 
    Vector2 screenPos;
    if (actor.getLocation().toScreen(screenPos)) {
        Render::Text(Fonts::getEspFont(), screenPos, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, actor.getObjectName()); 
    }
}
```
> ![Rendering Actors](https://i.imgur.com/ipi5q5g.png)

## Filtering Actors
This script shows how to filter actors, and renders a simple name esp.
```angelscript
uint64 playerClass = 0;
uint64 dinoClass = 0;

void main() {
    // Initialize the actor classes, we do this in the main callback as we should only do this once.
    // Finding an Unreal Engine object can be inefficient.
    playerClass = Engine::findObject("Class ShooterGame.ShooterCharacter");
    dinoClass = Engine::findObject("Class ShooterGame.PrimalDinoCharacter");
}

void renderPlayerEsp(Actor& player) {
    Vector2 screenPosition;
    if (player.getLocation().toScreen(screenPosition)) {
        // Because the actor inherits from the player class (ShooterCharacter) we can access the PlayerName field.
        string playerName = player.getString("ShooterCharacter", "PlayerName");
        Render::Text(Fonts::getEspFont(), screenPosition, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, playerName);
    }
}

void renderDinoEsp(Actor& dino) {
    Vector2 screenPosition;
    if (dino.getLocation().toScreen(screenPosition)) {
        // Because the actor inherits from the dino class (PrimalDinoCharacter), which inherits from PrimalCharacter we can access the DescriptiveName field.
        string dinoName = dino.getString("PrimalCharacter", "DescriptiveName");
        Render::Text(Fonts::getEspFont(), screenPosition, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, dinoName);
    }
}

void onActor(Actor& actor) {
    // Using the isA function to check if the actor inherits from the specified class.
    if (actor.isA(playerClass)) {
        // Actor inherits from the player class, so we can render the player esp.
        renderPlayerEsp(actor);
    } else if (actor.isA(dinoClass)) {
        // Actor inherits from the dino class, so we can render the dino esp.
        renderDinoEsp(actor);
    }
}
```
> ![Filtering Actors](https://i.imgur.com/E01Dd0K.png)