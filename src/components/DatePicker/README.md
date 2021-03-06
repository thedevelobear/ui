The Datepicker allows the user to select a date or date range from a calendar.

We recommend [React Dates](https://github.com/airbnb/react-dates) for DatePickers and DateRangePickers.

### Usage

Initialize with loading classes to load the styling from WFP UI

```js
import 'react-dates/initialize';
import { SingleDatePicker, DateRangePicker } from 'react-dates';
import ReduxFormWrapper from '../ReduxFormWrapper';

<SingleDatePickerInput
  datePicker={SingleDatePicker}
/>

<DateRangePickerInput
  datePicker={DateRangePicker}
/>
```

### Usage with redux-form or final-forms

```js
<Field
  component={ReduxFormWrapper}
  inputComponent={SingleDatePickerInput}
  datePicker={SingleDatePicker}
  format={value => (value ? moment(value) : undefined)}
  normalize={data => data && data.value && data.value.format()}
/>
```

```js
<Field
  component={ReduxFormWrapper}
  inputComponent={DateRangePickerInput}
  datePicker={DateRangePicker}
  format={value => (value ? { startDate: moment(value.startDate), endDate: moment(value.endDate) } : undefined)}
/>
```