---
title: File.getAsText
slug: Web/API/File/getAsText
---
{{APIRef("File API")}}

### 概述

按照指定的编码类型将文件内容解析成字符串并返回。

### 示例

```plain
// fileInput 是一个 HTMLInputElement 元素：<input type="file" id="myfileinput" multiple>
var fileInput = document.getElementById("myfileinput");

// files 是一个 FileList 对象 (类似 NodeList)
var files = fileInput.files;

// 一个对象，包含了允许的 MIME 类型
var accept = {
    binary : ["image/png", "image/jpeg"],
    text :   ["text/plain", "text/css", "application/xml", "text/html"]
};

var file;

for (var i = 0; i < files.length; i++) {

    file = files[i];

    // 如果文件的类型能够被检测到
   if (file !== null) {

        if (accept.text.indexOf(file.mediaType) > -1) {

            // file 是个可接受的文本文件，使用 utf-8 编码读取
            var data = file.getAsText("utf-8");
            // 使用字符串方法处理 data

        } else if (accept.binary.indexOf(file.mediaType) > -1) {
            // file 是个可接受的二进制文件
        }
    }
}
```