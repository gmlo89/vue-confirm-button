# VueConfirmButton

# Introduction

Button to request confirm before execute an action using [SweetAlert2](https://sweetalert2.github.io/ "SweetAlert2")
[DEMO](https://codesandbox.io/s/sad-visvesvaraya-2qy5n?file=/src/App.vue)

# Installation 
```JavaScript
npm i --save vue-confirm-button-gmlo
```

# Usage 
```JavaScript
import VueConfirmButton from "vue-confirm-button-gmlo";

Vue.component('VueConfirmButton', VueConfirmButton);
```

```HTML
<vue-confirm-button dialog-title="Do you confirm delete this item?">Delete</vue-confirm-button>
```



# Props

| Props                       | Type              | Required | Default                     |
| --------------------------- | ----------------- | -------- | --------------------------- |
| dialog-title                | String            | yes      | -                           |
| dialog-text                 | String            | no       | -                           |
| confirm-button-text         | String            | no       | "Yes"                       |
| cancel-button-text          | String            | no       | "Cancel"                    |

You can inherit attributes directly to the button, example:


```HTML
<!-- Use bootstrap classes on button and disabled-->
<vue-confirm-button class="btn btn-danger" disabled dialog-title="Do you confirm delete this item?">Delete</vue-confirm-button>
```

# Events
| Event | Description |
| -------- | ---------------- |
| confirmed | When the user to click on confirm button |
| canceled | When the user to click on cancel button or exit from the dialog |


# License
[MIT](https://github.com/sagalbot/vue-select/blob/master/LICENSE.md)