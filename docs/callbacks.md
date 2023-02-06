# Callbacks
There are a few callbacks that can be used in your scripts. These callbacks will be called by the application.

## Main
Called once whenever your script gets loaded.
```angelscript
void Main() {

}
```

## OnRender
Called every frame, you can only use the [Render](/namespaces?id=render) functions from within this callback.
```angelscript
void OnRender() {

}
```

## OnActor
Called for every [Actor](/classes?id=actor) that gets looped over by the application.
```angelscript
void OnActor(Actor& actor) {

}
```