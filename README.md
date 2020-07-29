# lwc-css-overrides
LWC uses shadow DOM which prevents modifying CSS of standard lightning components. This repository contains instruction how to override standard LWC CSS and offers useful, often needed overrides.

## How to use
1. Deploy Static Resource 'LWC_CSS_Overrides'.
2. In LWC import 'loadStyle' method:
```
import { loadStyle } from 'lightning/platformResourceLoader';
```

3. Also import 'LWC_CSS_Overrides': 
```
import LWC_CSS_Overrides from '@salesforce/resourceUrl/LWC_CSS_Overrides';
```

4. Load styles in 'connectedCallback':
```
connectedCallback() {
  loadStyle(this, LWC_CSS_Overrides)
}
```

5. Add required classes to elements in template:
```
<lightning-datatable
  class="datatable_hide-row-number"
  style="font-size: 0.6875rem;"
  columns={columns}
  data={items}
  key-field="Id"></lightning-datatable>
```

## Usefull classes
| Class         | Description   |
| ------------- | ------------- |
| datatable_th-center       | Align header to center  |
| datatable_hide-row-number | Hide Row Number Column  |
