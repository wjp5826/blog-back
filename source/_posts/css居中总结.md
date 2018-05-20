---
title: css居中总结
date: 2018-05-20 00:36:53
tags: css
---

### 一、水平居中系列

1. inline或者inline-*元素
    ```css
    .center-children {
        text-align: center;
    }
    ```
    inline、inline-block、inline-table、inline-flex等有效
2. 一个块级元素
      ```css
    .center{
       margin:0 auto;   
     }
     ```
3. 多个块级元素

    使用inline-block和text-align配合或者使用flex

### 二、垂直居中系列

1. inline或者inline-*元素
 1、单行：上下添加相等的内边距
      ```css
      .link {
          padding-top: 30px;
          padding-bottom: 30px;
        }
      ```
  2、多行：
       
    ```css
    // 可以模拟表格
    .center-table{
      display:table;
    }
    .center-table children{
      display:table-cell;
      vertical-align:center;
    }
    ```  
    ```css
    // 可以使用flexbox
    .flex-center-vertically {
      display: flex;
      justify-content: center;
      flex-direction: column;
      height: 400px;
     }
    ```
    
2. 块级元素
 1). 知道块级元素的高度
   ```css
   .parent {
     position: relative;
    }
    .child {
      position: absolute;
      top: 50%;
      height: 100px;
      margin-top: -50px;                                
      box-sizing: border-box; */
    }
  ```
 2). 不知道块级元素的高度
     ```css
     .parent {
          position: relative;
        }
        .child {
          position: absolute;
          top: 50%;
          transform: translateY(-50%);
        }
        ```
 3). 使用flexbox
     ```css
       .parent {
          display: flex;
          flex-direction: column;
          justify-content: center;
        }
     ```
### 三、居中（垂直和水平）

1. 固定宽度和高度
    
      ```css
        .parent {
          position: relative;
        }

        .child {
          width: 300px;
          height: 100px;
          padding: 20px;
        
          position: absolute;
          top: 50%;
          left: 50%;
        
          margin: -70px 0 0 -170px;
        }
      ```
        
2. 不知道宽度和高度
    
      ```css
        .parent {
          position: relative;
        }
        .child {
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);
        }
      ```
        
3. 使用flexbox
    
      ```css
        .parent {
          display: flex;
          justify-content: center;
          align-items: center;
        }
      ```