## 使用 assembly 打包成 jar

為了方便很常將 Maven 中的套件直接使用 assembly 一起包在 jar

最近發現 A 專案加到 B 專案中，在 IDEA 執行都行正常，打包成 jar 檔就會找不到 class

後來終於在網上找到解法了，回到 A 專案 Maven -> install ，再重新打包 B 專案 jar 就可以了！

![Alt text](img/idea-1.jpg)