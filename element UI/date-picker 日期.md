## date-picker

```
type决定日期类型
date 
day
week
month
year
daterange 日期范围方便查询
monthrange
```

````html
      单文档标签
<el-date-picker
                  v-model="searchForm.dates"
                  type="daterange"
                  range-separator="——"
                  start-placeholder="开始日期"
                  end-placeholder="结束日期"
                  value-format="yyyy-MM-dd"
                />
````



