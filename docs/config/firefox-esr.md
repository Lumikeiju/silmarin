<!-- @format -->

# Firefox (ESR) Config

Firefox version: `140.6.0esr (64-bit)` (extended support release channel)

## Advanced Preferences (`about:config`)

1. Enable Custom Styling
    1. `toolkit.legacyUserProfileCustomizations.stylesheets` = `true`
2. Disable AI Features
    1. `browser.ml.enable` = `false`
    2. `browser.ml.chat.enabled` = `false`
3. Disable Tab Groups
    1. `browser.tabs.groups.enabled` = `false`
    2. `browser.tabs.groups.smart.userEnabled` = `false`

## UI Customization

### Prerequisites

1. Enable Custom Styling in `about:config`
    1. `toolkit.legacyUserProfileCustomizations.stylesheets` = `true`
2. Clone [MrOtherGuy](https://github.com/MrOtherGuy)'s [firefox-csshacks](https://github.com/MrOtherGuy/firefox-csshacks)
    1. `about:support` → `Profile Folder` → `Open Folder`
    2. `Right Click` → `Open in Terminal`
    3. PowerShell: `git clone https://github.com/MrOtherGuy/firefox-csshacks.git chrome`
3. Create `userChrome.css`
    1. PowerShell: `cd chrome`
    2. PowerShell: `copy userChrome_example.css userChrome.css`

### My userChrome.css FIle

```css
/**
 * Lumikeiju's userChrome.css File
 *
 * @format
 */

/* Imports */

@import url(chrome/compact_proton.css);
@import url(chrome/compact_extensions_panel.css);
@import url(chrome/tabs_on_bottom_v2.css);
@import url(chrome/non_floating_sharp_tabs.css);

/* Customizations */

/* Remove placeholder text in searchbar */
#urlbar-input::placeholder,
.searchbar-textbox::placeholder {
    opacity: 0 !important;
}

/* Remove back and forward buttons */
#back-button,
#forward-button {
    display: none;
}

/* Define window minimum width */
:root:not([chromehidden~="toolbar"]) {
    min-width: 327px !important;
}
```
