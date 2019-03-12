# demo
## new Date()相关获取当月天数和当月第一天
var  myDate = new Date();

### 获取本月第一天周几
var monthFirst = new Date(myDate.getFullYear(), parseInt(myDate.getMonth()), 1).getDay(); </br>
### 获取本月天数(获取后一个月的0日即前一月的最后一日)
var totalDay=(new Date(myDate.getFullYear(), parseInt(myDate.getMonth() + 1), 0)).getDate();</br>
