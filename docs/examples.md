# Example scripts
This page provides a few example scripts. If you've made a useful script and think it can help people understand the scripting language, let Unreal know and it might be added here.

## GUI Elements
```angelscript
bool drawText = false;
Color textColor = Color(255, 255, 255, 255);

void OnRender() {
    if (drawText) {
        Fonts::Font@ menuTextFont = Fonts::GetMenuTextFont();

        // Changing the size of an existing font
        float originalSize = menuTextFont.SetSize(50.f);
        Render::Text(menuTextFont, Vector2(100, 100), textColor, Render::OUTLINE, "Example text");
        menuTextFont.SetSize(originalSize);
    }
}

void Main() {
    Gui::Tab@ scriptTab = Gui::GetMainWindow().AddTab("Script");
    Gui::Groupbox@ groupbox = scriptTab.AddGroupbox("Script groupbox", Vector2(100, 100));
    Gui::Checkbox@ checkbox = groupbox.AddCheckbox("Draw text", drawText);
    checkbox.AddColorPicker("Text color", textColor);
}
```
> ![Creating and using GUI elements image](https://i.imgur.com/em6xkYT.png)

## Creating a toggleable Window
```angelscript
Gui::Window@ scriptWindow = null;
void Main() {
    Vector2 windowSize = Vector2(600, 400);
    Vector2 windowPos = Render::GetScreenSize();
    windowPos.x = (windowPos.x - windowSize.x) / 2;
    windowPos.y = (windowPos.y - windowSize.y) / 2;

    @scriptWindow = Gui::AddWindow("Script window", "This window was created by a script.", windowPos, windowSize);
}

void OnRender() {
    // VK_F1 = 0x70
    if (Input::KeyPressed(0x70)) {
        Gui::SetWindowOpened(scriptWindow, !scriptWindow.IsOpen());
    }
}
```
> ![Creating a toggleable Window](https://i.imgur.com/KQvyYJm.png)

## Rendering Actors
```angelscript
void OnActor(Actor& actor) { 
    Vector2 screenPos;
    if (actor.GetLocation().ToScreen(screenPos)) {
        Render::Text(Fonts::GetEspFont(), screenPos, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, actor.GetObjectName()); 
    }
}
```
> ![Rendering Actors](https://i.imgur.com/ipi5q5g.png)

## Filtering Actors
This script shows how to filter actors, and renders a simple name esp.
```angelscript
uint64 playerClass = 0;
uint64 dinoClass = 0;

void Main() {
    // Initialize the actor classes, we do this in the main callback as we should only do this once.
    // Finding an Unreal Engine object can be inefficient.
    playerClass = Engine::FindObject("Class ShooterGame.ShooterCharacter");
    dinoClass = Engine::FindObject("Class ShooterGame.PrimalDinoCharacter");
}

void RenderPlayerEsp(Actor& player) {
    Vector2 screenPosition;
    if (player.GetLocation().ToScreen(screenPosition)) {
        // Because the actor inherits from the player class (ShooterCharacter) we can access the PlayerName field.
        string playerName = player.GetString("ShooterCharacter", "PlayerName");
        Render::Text(Fonts::GetEspFont(), screenPosition, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, playerName);
    }
}

void RenderDinoEsp(Actor& dino) {
    Vector2 screenPosition;
    if (dino.GetLocation().ToScreen(screenPosition)) {
        // Because the actor inherits from the dino class (PrimalDinoCharacter), which inherits from PrimalCharacter we can access the DescriptiveName field.
        string dinoName = dino.GetString("PrimalCharacter", "DescriptiveName");
        Render::Text(Fonts::GetEspFont(), screenPosition, Color(255, 255, 255, 255), Render::CENTER_X | Render::CENTER_Y | Render::OUTLINE, dinoName);
    }
}

void OnActor(Actor& actor) {
    // Using the isA function to check if the actor inherits from the specified class.
    if (actor.IsA(playerClass)) {
        // Actor inherits from the player class, so we can render the player esp.
        RenderPlayerEsp(actor);
    } else if (actor.IsA(dinoClass)) {
        // Actor inherits from the dino class, so we can render the dino esp.
        RenderDinoEsp(actor);
    }
}
```
> ![Filtering Actors](https://i.imgur.com/E01Dd0K.png)