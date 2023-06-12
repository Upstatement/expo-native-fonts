# expo-native-fonts

> Load fonts on iOS and Android using native code.

Traditionally, loading fonts in an Expo project requires using the `expo-fonts` library. While this has historically been a great solution, it has to load the fonts at runtime which necessitates you to show the splash screen.

With `expo-native-fonts`, font files are loaded via native code. What does that mean?

- Fonts will be available immediately at runtime (no more splash screen!)
- Fonts can be referred to using font weight and style, rather than a static name (no more `Raleway-BoldItalic`!)

## Installation

1. Install the package:

   ```bash
   yarn add expo-native-fonts
   ```

2. Add your `*.ttf` files to a directory (we recommend `assets/fonts`):

   ```bash
   app/
   assets/
   |- fonts/
      |- Raleway-Black.ttf
      |- Raleway-BlackItalic.ttf
      |- ...
   ```

3. Add the plugin to your `app.json` config:

   ```json
   {
     "expo": {
       "plugins": [
         [
           "expo-native-fonts",
           {
             "Raleway": [
               {
                 "path": "./assets/fonts/Raleway-Black.ttf",
                 "weight": 900
               },
               {
                 "path": "./assets/fonts/Raleway-BlackItalic.ttf",
                 "weight": 900,
                 "style": "italic"
               }
             ]
           }
         ]
       ]
     }
   }
   ```

4. Run your app!

## Gotchas

> 🚧 Under Construction 🚧

- Font files have to be ttf or otf (untested with others)
- Family name keys must match the font file family

## Contributing

> 🚧 Under Construction 🚧

### Testing

1. In this repo, link the project:

   ```bash
   yarn link
   ```

2. In your example project repo, link the dependency:

   ```bash
   yarn link expo-native-fonts
   ```

3. In your example project repo, run the prebuild command:

   ```bash
   yarn expo prebuild --clean
   ```

## Credits

Major props to [@jsamr](https://github.com/jsamr) for their documentation on supporting fonts natively: https://github.com/jsamr/react-native-font-demo
