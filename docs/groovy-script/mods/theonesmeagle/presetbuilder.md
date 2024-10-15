---
title: "PresetBuilder"
titleTemplate: "TheOneSmeagle | CleanroomMC"
description: "Add or apply a 'Preset' that can change the look of the probes UI"
source_code_link: "https://github.com/strubium/TheOneSmeagle/blob/1.12/src/main/java/mcjty/theoneprobe/gui/PresetBuilder.java"
---

# PresetBuilder (TheOneSmeagle)

## Description
Add or apply a 'Preset' that can change the look of the probe's UI, Presets can be selectable in the Probe Note

:::::::::: info Warning {id="warning"}
Adding more that 8 (Including the default ones, will break the Probe Notes UI) 
::::::::::

## Identifier

Refer to this via any of the following:

```groovy:no-line-numbers {3}
mcjty.theoneprobe.gui.PresetBuilder/* Used as page default */ // [!code focus]
```

### Preset Builder

As the name would imply, PresetBuilder uses a builder.

Don't know what a builder is? Check [the builder info page](../../getting_started/builder.md) out.

:::::::::: mcjty.theoneprobe.gui.PresetBuilder() {open id="abstract"}
- `String`. Sets the name in the Probe Note UI (Default `null`).

    ```groovy:no-line-numbers
    setName(String)
    ```

- `int`. Sets the color of the box's border. (Default '0xFFFFFF').

    ```groovy:no-line-numbers
    setBoxBorderColor(int)
    ```

- `int`. Sets the color inside the box. (Default '0x000000').

    ```groovy:no-line-numbers
    setBoxFillColor(int)
    ```

- `int`. Sets the thickness of the box's border (Default '1')

    ```groovy:no-line-numbers
    setBoxThickness(int)
    ```

- `int`. Sets the box's offset from the edge of the screen  (Default '0')

    ```groovy:no-line-numbers
    setBoxOffset(int)
    ```

- `TextStyleClass, String`. Set a text style to a value 

    ```groovy:no-line-numbers
    addTextStyleClass(TextStyleClass, String)
    ```

- Adds creates a Preset with the data, and adds it to the presets ArrayList.

    ```groovy:no-line-numbers
    build()
    ```

::::::::: details Example {open id="example"}
```groovy:no-line-numbers
def newPreset =  new PresetBuilder()
    .setName("The Cool Example Preset")
    .setBoxBorderColor(0xff123456 as int)  // In Java, hex literals like 0xff123456 are integers, but in Groovy, they are "Long" unless cast to an int
    .setBoxFillColor(0xff654321 as int)   
    .setBoxThickness(2)
    .setBoxOffset(5)
    .addTextStyleClass(TextStyleClass.MODNAME, "blue,italic")
    .addTextStyleClass(TextStyleClass.NAME, "red,bold")
    .build()
```

:::::::::

::::::::::

## Removing Entries

- Remove all presets 

    ```groovy:no-line-numbers
    PresetBuilder.removeAll()
    ```

- Remove all presets 

    ```groovy:no-line-numbers
    PresetBuilder.removePresetByName(String)
    ```

:::::::::: details Example {open id="example"}
```groovy:no-line-numbers
PresetBuilder.removePresetByName("Default")
PresetBuilder.removeAll()
```

::::::::::
