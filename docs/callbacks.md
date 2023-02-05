# Callbacks
There are a few callbacks that can be used in your scripts. These callbacks will be called by the application.

## main
Called once whenever your script gets loaded.
```clike
void main() {

}
```

## onRender
Called every frame, you can only use the [Render](/namespaces?id=render) functions from within this callback.
```clike
void onRender() {

}
```

## onActor
Called for every [Actor](/classes?id=actor) that gets looped over by the application.
```clike
void onActor(Actor& actor) {

}
```