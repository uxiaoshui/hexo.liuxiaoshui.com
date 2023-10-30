---
title: 第二篇用typora编写
date: 2023-10-30 03:31:43
tags: 测试测试
---

#  测试typora编写


![图片啊这是](/img/OIG (3).jpg)

```java
package com.alau.cat.common.i18n;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.MessageSource;
import org.springframework.context.i18n.LocaleContextHolder;
import org.springframework.stereotype.Service;

import java.util.Locale;

@Service
public class UnifiedMessageSource {
    @Autowired
    private MessageSource messageSource;

    /**
     * 获取国际化消息
     * @param code 消息code
     * @return
     */
    public String getMessage(String code) {

        return getMessage(code, null);
    }

    /**
     * 获取国际化消息
     * @param code 消息code
     * @param args 参数
     * @return
     */
    public String getMessage(String code, Object[] args) {

        return getMessage(code, args, "");
    }

    /**
     * 获取国际化消息
     * @param code 消息code
     * @param args 参数
     * @param defaultMessage 默认消息
     * @return
     */
    public String getMessage(String code, Object[] args, String defaultMessage) {
        Locale locale = LocaleContextHolder.getLocale();
        return messageSource.getMessage(code, args, defaultMessage, locale);
    }
}

```

