# highcharts-export-example

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev
```

## How to reproduce export bug in highcharts
* After running the command `npm run dev` go to `http://localhost:3000` in Firefox
* Export the chart as image
* Nothing should happen
* Check console to verify the error

### Workaround 1
* Open `public/main.css`
* Remove the css custom properties (variables)
* Export the chart as image
* The chart should be exported, but styling of axis labels and legend labels is incorrect

### Workaround 2
* Open `pages/index.vue`
* Change `import Highcharts from "highcharts/highcharts.src"` to `import Highcharts from "highcharts/highcharts"`;
* Export the chart as image
* The chart should be exported, but styling of axis labels and legend labels is incorrect
