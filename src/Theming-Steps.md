# Modify themes using CSS variables in angular material.

- Configure your theme definition in your `src/styles.scss` file by removing any color definition from the $light-theme and remove the dark theme definition altogether. Then, define your light theme as follows:

```
use-system-variables: true
``` 
- ...add the typography configuration to the $light-theme
```
    typography: (
      use-system-variables: true
    )
```
In your `src/style.scss`, remove any reference to the dark theme definition from the ```html``` selector and background colors if any.

- In your `src/style.scss`, turn the `html` class into the `root` pseudo class and include mat.system-level-colors and mat.system-level-typography mixins.
```

:root {
  @include mat.all-component-themes($light-theme);
  @include layout-theme.theme($light-theme);
  @include mat.system-level-colors(light-theme); //added
  @include mat.system-level-typography(light-theme); // added
}
```

- Generate a theme on the [material theme builder website](https://material-foundation.github.io/material-theme-builder/)
or on [themes.angular-material.dev](https://themes.angular-material.dev/)

- Create the directory in which you want to store the theme files, and save the theme file in that directory. I create a directory called ```src/styles/themes/``` then save my light theme file as ```light.scss```. 
 the structure of the class is as follows:
```  scss
:root,
:host {
 --system-background: #hex;
...
}
```
- Add your theme file to your angular.json > "styles" array
```json
"src/styles/themes/light.scss"
```
