# Docs

## Usage

```svelte
<script>
  import { DateInput } from 'date-picker-svelte'
  let date = new Date()
</script>

<DateInput bind:value={date} />
```

## DateInput

### Props

| Prop          | Type   | Description |
| :------------ | :----- | :---------- |
| `value`       | Date   | Date value |
| `min`         | Date   | The earliest value the user can select |
| `max`         | Date   | The latest value the user can select |
| `placeholder` | string | Placeholder |
| `valid`       | bool   | Whether the text is valid |
| `format`      | string | Format string |
| `visible`     | bool   | Whether the date popup is visible |
| `locale`      | Locale | Locale object for internationalization |

#### Format string

Example format string: `yyyy-MM-dd HH:mm:ss`

| Pattern    | Result example
| :--------- | :-------------
| `yyyy`     | 2021
| `MM`       | 12
| `dd`       | 31
| `HH`       | 23
| `mm`       | 59
| `ss`       | 59

## DatePicker

### Props

| Prop          | Type   | Description |
| :------------ | :----- | :---------- |
| `value`       | Date   | Date value |
| `min`         | Date   | The earliest year the user can select |
| `max`         | Date   | The latest year the user can select |
| `locale`      | Locale | Locale object for internationalization |

## Internationalization

### `Locale`
Object to support internationalization. Properties (all are optional):
- `weekdays`: Array of weekdays in short form, Sunday to Monday. Default: `['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa']`
- `months`: Array of month names, January to December. Default: `['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December']`
- `weekStartsOn`: The day the week starts on, 0 = Sunday. Default: `1`

### `localeFromDateFnsLocale`
If you use [date-fns](https://date-fns.org/), you can create a Locale object by passing a date-fns locale to this function:
```js
<script>
  import { DateInput, localeFromDateFnsLocale } from 'date-picker-svelte'
  import { hy } from 'date-fns/locale'
  let date = new Date()
  let locale = localeFromDateFnsLocale(hy)
</script>

<DateInput bind:value={date} {locale} />
```

## CSS variables

Colors:
- `--date-picker-foreground`
- `--date-picker-background`
- `--date-picker-highlight-border`
- `--date-picker-highlight-shadow`
- `--date-picker-selected-color`
- `--date-picker-selected-background`

Lengths:
- `--date-input-width`

Dark theme example:
```css
:root {
  --date-picker-background: #1b1e27;
  --date-picker-foreground: #f7f7f7;
}
```