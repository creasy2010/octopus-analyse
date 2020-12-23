### zi-CN.json:

{
SIMPLE": "简单的句子",
"HELLO": "你好, {name}。欢迎来到{where}!",
"TIP": "这是<span style='color:red'>HTML</span>",
"TIP_VAR": "这是<span style='color:red'>{message}</span>",
"SALE_START": "拍卖将在{start, date}开始",
"SALE_END": "拍卖将在{end, date, full}结束",
"COUPON": "优惠卷将在{expires, time, medium}过期",
"TIME": "时间是{theTime, time}",
"SALE_PRICE": "售价{price, number, CNY}",
"PHOTO": "你有{photoNum, number}张照片",
"MESSAGE_NOT_IN_COMPONENT": "react-intl-universal 可以在非 React.Component 的 js 文件进行国际化"
}

### use:

## Step 1

import intl from 'react-intl-universal';

// For Node.js, common locales should be added in the application
global.Intl = IntlPolyfill;
require('intl/locale-data/jsonp/en.js');
require('intl/locale-data/jsonp/zh.js');
require('intl/locale-data/jsonp/fr.js');
require('intl/locale-data/jsonp/ja.js');

## Step 2

const currentLocale = "zh-CN"; // Determine user's locale here
intl.init({
currentLocale,
locales: {
[currentLocale]: require(`./locales/${currentLocale}`)
}
});

## Step 3

import intl from 'react-intl-universal';

 <div>{intl.getHTML('TIP_VAR', {message: 'HTML with variables'})}</div>

        <div className="title">Date Examples:</div>
        <div>{intl.get('SALE_START', {start})}</div>
        <div>{intl.get('SALE_END', {end})}</div>
        <div>{intl.get('COUPON', {expires})}</div>


        <div>{intl.get('SALE_PRICE', {price})}</div>

        <div>{intl.get('SIMPLE')}</div>
        <div>{intl.get('HELLO', {name:'Tony', where:'Alibaba'})}</div>

        <div>{intl.get("PHOTO", { photoNum: 0 })}</div>
        <div>{intl.get("PHOTO", { photoNum: 1 })}</div>
        <div>{intl.get("PHOTO", { photoNum: 1000000 })}</div>
