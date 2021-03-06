---
title: Дополнительные требования к сетевой безопасности для Office 365 GCC High и DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Сводка: Office 365 GCC High и DoD имеют дополнительные требования к сетевой безопасности'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926563"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Дополнительные требования сетевой безопасности для Office 365 GCC High и DoD

*Эта статья применяется к Office 365 GCC, Office 365, Microsoft 365 GCC и Microsoft 365 DoD.*

Office 365 GCC high и DOD — это безопасные облачные среды, которые отвечают потребностям правительства Соединенных Штатов и его поставщиков и подрядчиков.  Эти облачные среды имеют дополнительные сетевые ограничения, к которым разрешен доступ к внешним конечным точкам.

GCC Для клиентов с высоким уровнем и doD, планируя использовать федерационные удостоверения или гибридное сосуществование, может потребоваться, чтобы Корпорация Майкрософт разрешила входящие и/или исходящие доступы к существующим локальному развертыванию.  Примеры таких действий:

* Использование федераированных удостоверений (с службами Федерации Active Directory или аналогичной поддержкой STS)
* Гибридное сосуществование с локальной Exchange Server или Skype для бизнеса развертывания
* Перенос существующего пользовательского контента из локальной системы

Чтобы разрешить службе общаться с конечными точками  на месте, необходимо отправить электронное письмо в Office 365 для изменения сети.

> [!WARNING]
> Все запросы имеют трехнедельный SLA и не могут быть ускоряться **из-за** необходимых элементов управления безопасностью и соответствия требованиям и конвейеров развертывания.  Это включает начальные сетевые запросы, а также любые изменения после перехода в службу.  Убедитесь, что сетевые группы знают об этой временной шкале и включают ее в циклы планирования.

Отправьте сообщение электронной [почты Office 365 для государственных организаций Allow-List запросы](mailto:o365gwlt@microsoft.com) со следующими сведениями:

* **Чтобы**: [Office 365 для государственных организаций Allow-List запросы](mailto:o365gwlt@microsoft.com)
* **От**: Администратор клиента — отправка электронной почты **должна соответствовать** контакту глобального администратора в клиенте
* **Тема электронной** почты: Office 365 GCC запрос высокой сети — contoso.onmicrosoft.us (замените имя клиента)

В текст сообщения должны быть включены следующие данные:

* Имя Microsoft Online Services клиента (например, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Список рассылки электронной почты, с помощью который Корпорация Майкрософт будет взаимодействовать для связи, связанной с изменением сети и/или последующими решениями для недействительных подсетей.
* Указать, планируете ли вы использовать Microsoft Teams совместное сосуществование с локальной развертыванием
* Федерационная система удостоверений, внешне доступные URL-адрес (например, sts.contoso.com) и диапазон IP-адресов в области нотации CIDR (например,. 10.1.1.0/28)
* Url-адрес и диапазон IP-адресов локального списка сертификатов PKI в нотации CIDR
* Внешне доступный URL-адрес и диапазон IP Exchange Server локального развертывания в ciDR нотации
* Внешне доступный URL-адрес и диапазон IP Skype для бизнеса локального развертывания в ciDR нотации

В целях безопасности и соответствия требованиям помните о следующих ограничениях на запрос:

* Существует четыре ограничения подсети для каждого клиента
* Подсети должны быть в нотации CIDR (например, 10.1.1.0/28)
* Диапазоны подсетей не могут быть больше /24
* Мы **не можем** разместить запросы на доступ к коммерческим облачным службам (коммерческим Office 365, Google G-Suite, Amazon Web Services и т.д.)

После того, как ваш запрос был получен и утвержден Корпорацией Майкрософт, для реализации будет установлен трехнедельный SLA, который не может быть ускоряться.  Вы получите начальное подтверждение, когда мы получим ваш запрос и окончательное подтверждение после его завершения.
