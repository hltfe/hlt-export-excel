# hlt-export-excel

> 纯 js 导出 excel

## 下载

```
npm install hlt-export-excel

or

yarn add hlt-export-excel

```

## 文档

### 用法

```
    const ExportJsonExcel = require('js-export-excel')

    var option={};

    option.fileName = 'excel'
    option.datas=[
      {
        sheetData:[{one:'一行一列',two:'一行二列'},{one:'二行一列',two:'二行二列'}],
        sheetName:'sheet',
        sheetFilter:['two','one'],
        sheetHeader:['第一列','第二列'],
        columnWidths: [20, 20]
      },
      {
        sheetData:[{one:'一行一列',two:'一行二列'},{one:'二行一列',two:'二行二列'}]
      }
    ];

    var toExcel = new ExportJsonExcel(option); //new
    toExcel.saveExcel(); //保存
```

### option

    1.datas 数据
    ```
       /*多个sheet*/
       /*每个sheet为一个object */
       [{
       sheetData:[], // 数据
       sheetName:'', // sheet名字
       sheetFilter:[], //列过滤
       sheetHeader:[] // 第一行
       columnWidths: [] //列宽 需与列顺序对应
       }]

    ```
    2.fileName 下载文件名(默认：download)

#### sheet option
    1.sheetName sheet 名字(可有可无)(默认 sheet1)
    2.sheetHeader 标题（excel 第一行数据）
    ```
        sheetHeader: ["第一列", "第二列"];

    ```
    3.columnWidths 列宽 非必须
    ```
        columnWidths = [20, ""];

    ```
    4.sheetData 数据源(必须)
    ```
        <!--两种形式-->
        <!--第一种 object-->
        [{one:'一行一列',two:'一行二列'},{one:'二行一列',two:'二行二列'}]
        <!--第二种 arrary-->
        [['一行一列','一行二列'],['二行一列','二行二列']]

    ```
    5.sheetFilter 列过滤(只有在 data 为 object 下起作用)(可有可无)
    ```
        sheetFilter = ["two", "one"];

    ```
