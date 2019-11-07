---
title: Hexo 的使用筆記
date: 2019-11-07 22:50:03
tags: [notes]
---

太久沒有使用，把指令都給忘光了，還得回去看英文的文件才能重新開始寫文章。不如花點時間記一下會用到的指令，下次就不用看原文了

## npm 相關

### 更新所有套件

```bash
$ npm update -g
```
`-g`應該是更新電腦裡所有npm安裝的套件，否則就只會更新目前專案指定的套件（的樣子）

## 主題相關

### 更新Next的主題

```bash
$ cd themes/next
$ git pull
```
如果有git的話就pull一下，沒有的話要手動來了

### 匯出個人改過的東西

```bash
$ git diff _config.yml > ../_config.yml.patch
```
不想commit或是stash這個內層的專案，不然就很難pull了。  
匯出改過的東西之後，下次要更新前就可以放心把_config.yml恢復預設了

### 匯入個人改過的設定

```bash
$ git apply --reject ../_config.yml.patch
```
若有失敗，就會停止，接著就得手動自己更新了


## Hexo 相關

### 新增一篇新文章

```bash
$ hexo new "標題"
```
預設將會新建一個post，在專案中

### 跑本地端的Server起來預覽

```bash
$ hexo server
```
執行後會跳出連結讓你點選，就能看到自己的網頁

### 產生網頁

```bash
$ hexo generate
```
會產生網頁放在`Public`的資料夾中

### 發佈網頁

```bash
$ hexo deploy
```
把產生的網頁發布到git上

### 清掉本地端生成的快取

```bash
$ hexo clean
```
會清掉全部自動生成的檔案，包括網頁之類的。


