# wp-admin-scheme-oklch

WordPress admin color scheme expressed as CSS variables using OKLCH values. Allows custom colors to the WP Admin Bar (Toolbar) and Admin Menu.

We use OKLCH since it allows subtle transformations, similar to how native WordPress color schemes use SCSS color functions.

## Install

```
npm install wp-admin-scheme-oklch
```

## Usage

Import the [admin.css](admin.css) file. Then, define the css variables, scoped to `#wpadminbar` and `#adminmenumain`.

```
@import 'wp-admin-scheme-oklch/admin.css';

#wpadminbar,
#adminmenumain {
  --base-color: oklch(0.359 0.144 278.697);
  --icon-color: oklch(0.785 0.115 274.713);
  --highlight-color: oklch(0.623 0.214 259.815);
  --notification-color: oklch(0.718 0.202 349.761);
  --menu-bubble-text: oklch(0.257 0.09 281.288);
}

```

Note: OKLCH values are expected, since other css variables inherit these and some make adjustments. It's possible to use other color formats (e.g. hex), but all variables would need to be defined.

### Using Tailwind (v4) Colors

In its version 4, Tailwind introduced css variables using OKLCH for its color palette. Importing tailwind will make all their color tokens available, along with its `--alpha()` helper function:

```
@import "tailwindcss";

@import 'wp-admin-scheme-oklch/admin.css';

#wpadminbar,
#adminmenumain {
  --text-color: var(--color-neutral-300);
  --base-color: var(--color-green-950);
  --icon-color: var(--color-stone-300);
  --highlight-color: var(--color-amber-500);
  --notification-color: var(--color-amber-400);

  --menu-text: --alpha(var(--color-green-50) / 80%);
  --menu-icon: --alpha(var(--color-green-50) / 40%);

  --menu-current-text: var(--color-green-950);
  --menu-current-icon: var(--color-green-950);

  --menu-highlight-text: var(--color-amber-500);
  --menu-highlight-icon: var(--color-amber-500);

  --menu-submenu-focus-text: var(--color-amber-500);

  --menu-bubble-text: var(--base-color);
}

```

## License

ISC
