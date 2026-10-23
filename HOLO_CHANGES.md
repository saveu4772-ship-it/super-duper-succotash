# Tengerium: Holo skin

Approach: the app keeps its AppCompat/Material3 widgets (about 40 layouts, viewBinding, Navigation),
but every widget is re-themed to look like Android Holo. Framework `Theme.Holo` can't be used here
because AppCompatActivity and the Material widgets require AppCompat/Material themes and would crash.

## Changed
- values/colors.xml, values/themes.xml, values-night/themes.xml: Holo palette
  (light: #0099CC / #33B5E5 on white; dark: #33B5E5 on black / #111111), Holo light and dark variants.
- values-v23/themes.xml: solid black system bars with light icons.
- values/styles_holo.xml (new): square shapes, flat gray Holo buttons, blue primary buttons,
  borderless buttons, hairline-border flat cards, action bar with 2dp blue line,
  uppercase tabs with blue underline, underline text fields, circular FAB, square dialogs/sheets.
- 26 layouts: hard-coded Material3 styles swapped for the Holo ones, card radii/elevation set to 0.
- drawables: bg_assdlang_glass, bg_badge, bg_modal_profile, bg_oobe_card, bg_placeholder_bubble flattened;
  holo_actionbar_bg and holo_tab_indicator added.
- TengeriumApp.kt: dynamic colors (Material You) disabled.
- BubbleStyleHelper.kt: bubbles 3dp radius, no elevation.
- ThemePreset.kt: "Standard" preset uses Holo blue / gray bubbles.
- styles_assdlang.xml removed (it was empty).

## Not done (needs assets or device testing)
- Icons are still the Material vector icons (Holo icon pack not available offline).
- MaterialSwitch keeps its Material3 shape (only recolored).
- Not compiled or run here (no Android SDK): build once and check screens.
