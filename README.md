[![npm](https://img.shields.io/npm/v/@wojtekmaj/react-timerange-picker.svg)](https://www.npmjs.com/package/@wojtekmaj/react-timerange-picker) ![downloads](https://img.shields.io/npm/dt/@wojtekmaj/react-timerange-picker.svg) [![CI](https://github.com/wojtekmaj/react-timerange-picker/workflows/CI/badge.svg)](https://github.com/wojtekmaj/react-timerange-picker/actions)

# React-TimeRange-Picker

A time range picker for your React app.

- Supports virtually any language
- No moment.js needed

## tl;dr

- Install by executing `npm install @wojtekmaj/react-timerange-picker` or `yarn add @wojtekmaj/react-timerange-picker`.
- Import by adding `import TimeRangePicker from '@wojtekmaj/react-timerange-picker'`.
- Use by adding `<TimeRangePicker />`. Use `onChange` prop for getting new values.

## Demo

A minimal demo page can be found in `sample` directory.

[Online demo](http://projects.wojtekmaj.pl/react-timerange-picker/) is also available!

## Looking for a date range picker or a datetime range picker?

React-TimeRange-Picker will play nicely with [React-DateRange-Picker](https://github.com/wojtekmaj/react-daterange-picker) and [React-DateTimeRange-Picker](https://github.com/wojtekmaj/react-datetimerange-picker). Check them out!

## Getting started

### Compatibility

Your project needs to use React 16.3 or later. If you use an older version of React, please refer to the table below to find a suitable React-TimeRange-Picker version.

| React version | Newest compatible React-TimeRange-Picker version |
| ------------- | ------------------------------------------------ |
| ≥16.3         | latest                                           |
| ≥16.0         | 2.x                                              |

#### Legacy browsers

If you need to support legacy browsers like Internet Explorer 10, you will need to use [Intl.js](https://github.com/andyearnshaw/Intl.js/) or another Intl polyfill along with React-Date-Picker.

### Installation

Add React-TimeRange-Picker to your project by executing `npm install @wojtekmaj/react-timerange-picker` or `yarn add @wojtekmaj/react-timerange-picker`.

### Usage

Here's an example of basic usage:

```js
import React, { useState } from 'react';
import TimeRangePicker from '@wojtekmaj/react-timerange-picker';

function MyApp() {
  const [value, onChange] = useState(['10:00', '11:00']);

  return (
    <div>
      <TimeRangePicker onChange={onChange} value={value} />
    </div>
  );
}
```

### Custom styling

If you want to use default React-Date-Picker and React-Calendar styling to build upon it, you can import them by using:

```js
import '@wojtekmaj/react-timerange-picker/dist/TimeRangePicker.css';
import 'react-clock/dist/Clock.css';
```

### Next.js and Vite

Next.js and Vite do not allow components from `node_modules` to import styles. You'll need to follow instructions from [Custom styling](#custom-styling) to get going.

## User guide

### TimeRangePicker

Displays an input field complete with custom inputs, native input and a clock.

#### Props

| Prop name            | Description                                                                                                                                                                                                  | Default value           | Example values                                                                                                                                                                                                                        |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| amPmAriaLabel        | `aria-label` for the AM/PM select input.                                                                                                                                                                     | n/a                     | `"Select AM/PM"`                                                                                                                                                                                                                      |
| autoFocus            | Automatically focuses the input on mount.                                                                                                                                                                    | n/a                     | `true`                                                                                                                                                                                                                                |
| className            | Class name(s) that will be added along with `"react-timerange-picker"` to the main React-TimeRange-Picker `<div>` element.                                                                                   | n/a                     | <ul><li>String: `"class1 class2"`</li><li>Array of strings: `["class1", "class2 class3"]`</li></ul>                                                                                                                                   |
| clearAriaLabel       | `aria-label` for the clear button.                                                                                                                                                                           | n/a                     | `"Clear value"`                                                                                                                                                                                                                       |
| clearIcon            | Content of the clear button. Setting the value explicitly to `null` will hide the icon.                                                                                                                      | (default icon)          | <ul><li>String: `"Clear"`</li><li>React element: `<ClearIcon />`</li><li>React function: `ClearIcon`</li></ul>                                                                                                                        |
| clockAriaLabel       | `aria-label` for the clock button.                                                                                                                                                                           | n/a                     | `"Toggle clock"`                                                                                                                                                                                                                      |
| clockClassName       | Class name(s) that will be added along with `"react-clock"` to the main React-Clock `<time>` element.                                                                                                        | n/a                     | <ul><li>String: `"class1 class2"`</li><li>Array of strings: `["class1", "class2 class3"]`</li></ul>                                                                                                                                   |
| clockIcon            | Content of the clock button. Setting the value explicitly to `null` will hide the icon.                                                                                                                      | (default icon)          | <ul><li>String: `"Clock"`</li><li>React element: `<ClockIcon />`</li><li>React function: `ClockIcon`</li></ul>                                                                                                                        |
| closeClock           | Whether to close the clock on value selection.                                                                                                                                                               | `true`                  | `false`                                                                                                                                                                                                                               |
| data-testid          | `data-testid` attribute for the main React-TimeRange-Picker `<div>` element.                                                                                                                                 | n/a                     | `"date-picker"`                                                                                                                                                                                                                       |
| disabled             | Whether the time range picker should be disabled.                                                                                                                                                            | `false`                 | `true`                                                                                                                                                                                                                                |
| disableClock         | When set to `true`, will remove the clock and the button toggling its visibility.                                                                                                                            | `false`                 | `true`                                                                                                                                                                                                                                |
| format               | Input format based on [Unicode Technical Standard #35](https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table). Supported values are: `H`, `HH`, `h`, `hh`, `m`, `mm`, `s`, `ss`, `a`. | n/a                     | `"h:m:s a"`                                                                                                                                                                                                                           |
| hourAriaLabel        | `aria-label` for the hour input.                                                                                                                                                                             | n/a                     | `"Hour"`                                                                                                                                                                                                                              |
| hourPlaceholder      | `placeholder` for the hour input.                                                                                                                                                                            | `"--"`                  | `"hh"`                                                                                                                                                                                                                                |
| isOpen               | Whether the clock should be opened.                                                                                                                                                                          | `false`                 | `true`                                                                                                                                                                                                                                |
| locale               | Locale that should be used by the time range picker and the clock. Can be any [IETF language tag](https://en.wikipedia.org/wiki/IETF_language_tag).                                                          | User's browser settings | `"hu-HU"`                                                                                                                                                                                                                             |
| maxDetail            | How detailed time picking shall be. Can be `"hour"`, `"minute"` or `"second"`.                                                                                                                               | `"minute"`              | `"second"`                                                                                                                                                                                                                            |
| maxTime              | Maximum time that the user can select.                                                                                                                                                                       | n/a                     | <ul><li>Date: `new Date()`</li><li>String: `"22:15:00"`</li></ul>                                                                                                                                                                     |
| minTime              | Minimum date that the user can select.                                                                                                                                                                       | n/a                     | <ul><li>Date: `new Date()`</li><li>String: `"22:15:00"`</li></ul>                                                                                                                                                                     |
| minuteAriaLabel      | `aria-label` for the minute input.                                                                                                                                                                           | n/a                     | `"Minute"`                                                                                                                                                                                                                            |
| minutePlaceholder    | `placeholder` for the minute input.                                                                                                                                                                          | `"--"`                  | `"mm"`                                                                                                                                                                                                                                |
| name                 | Input name prefix. Time from/Time to fields will be named `"yourprefix_from"` and `"yourprefix_to"` respectively.                                                                                            | `"timerange"`           | `"myCustomName"`                                                                                                                                                                                                                      |
| nativeInputAriaLabel | `aria-label` for the native time input.                                                                                                                                                                      | n/a                     | `"Time"`                                                                                                                                                                                                                              |
| onChange             | Function called when the user picks a valid time.                                                                                                                                                            | n/a                     | `(value) => alert('New time is: ', value)`                                                                                                                                                                                            |
| onClockClose         | Function called when the clock closes.                                                                                                                                                                       | n/a                     | `() => alert('Clock closed')`                                                                                                                                                                                                         |
| onClockOpen          | Function called when the clock opens.                                                                                                                                                                        | n/a                     | `() => alert('Clock opened')`                                                                                                                                                                                                         |
| onFocus              | Function called when the focuses an input.                                                                                                                                                                   | n/a                     | `(event) => alert('Focused input: ', event.target.name)`                                                                                                                                                                              |
| openClockOnFocus     | Whether to open the clock on input focus.                                                                                                                                                                    | `true`                  | `false`                                                                                                                                                                                                                               |
| portalContainer      | Element to render the clock in using portal.                                                                                                                                                                 | n/a                     | `document.getElementById('my-div')`                                                                                                                                                                                                   |
| rangeDivider         | Divider between time inputs.                                                                                                                                                                                 | `"–"`                   | `" to "`                                                                                                                                                                                                                              |
| required             | Whether time input should be required.                                                                                                                                                                       | `false`                 | `true`                                                                                                                                                                                                                                |
| secondAriaLabel      | `aria-label` for the second input.                                                                                                                                                                           | n/a                     | `"Second"`                                                                                                                                                                                                                            |
| secondPlaceholder    | `placeholder` for the second input.                                                                                                                                                                          | `"--"`                  | `"ss"`                                                                                                                                                                                                                                |
| value                | Input value.                                                                                                                                                                                                 | n/a                     | <ul><li>Date: `new Date(2017, 0, 1, 22, 15)`</li><li>String: `"22:15:00"`</li><li>An array of dates: `[new Date(2017, 0, 1, 22, 15), new Date(2017, 0, 1, 23, 45)]`</li><li>An array of strings: `["22:15:00", "23:45:00"]`</li></ul> |

### Clock

TimeRangePicker component passes all props to React-Clock, with the exception of `className` (you can use `clockClassName` for that instead). There are tons of customizations you can do! For more information, see [Clock component props](https://github.com/wojtekmaj/react-clock#props).

## License

The MIT License.

## Author

<table>
  <tr>
    <td>
      <img src="https://github.com/wojtekmaj.png?s=100" width="100">
    </td>
    <td>
      Wojciech Maj<br />
      <a href="mailto:kontakt@wojtekmaj.pl">kontakt@wojtekmaj.pl</a><br />
      <a href="https://wojtekmaj.pl">https://wojtekmaj.pl</a>
    </td>
  </tr>
</table>
