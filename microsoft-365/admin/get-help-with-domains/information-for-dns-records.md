---
title: Сбор сведений, необходимых для создания записей DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Соберите значения и сведения, необходимые для создания записей DNS для подключения домена к Microsoft 365 подписке.
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393887"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Сбор сведений, необходимых для создания записей DNS

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Шаг 1. Поиск значения записи TXT и проверка

::: moniker range="o365-worldwide"

1. В Центр администрирования Microsoft 365 перейдите на **страницу Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены.</a>

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).

::: moniker-end
    
2. На странице **Домены** выберите домен, а затем выберите **настройку Начните.** Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.
    
3. На странице **Проверка домена** выберите Добавить запись **TXT в DNS-записи** домена, а затем выберите **Продолжить**.
    
4. Скопируйте **показанные значения TXT.** Выглядит так: **MS=msXXXXXXXXXXX.** 
    
5. Перейдите [к добавлению записей DNS](create-dns-records-at-any-dns-hosting-provider.md)для подключения домена и выполните действия по добавлению записей на веб-сайте хоста DNS.
    
6. Выполните действия по созданию записи TXT (или записи MX) в вашем DNS-хозяйте, а затем проверьте домен в Microsoft 365.

7. Удалите запись TXT (или запись MX) с вашего DNS-хоста после проверки домена в Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Шаг 2. Поиск значения записи MX для электронной почты и других

::: moniker range="o365-worldwide"

1. В Центр администрирования Microsoft 365 перейдите на **страницу Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).

::: moniker-end
    
2. На странице **Домены** щелкните свой домен.
    
3. Выберите **Управление DNS,** выберите **дополнительные параметры** Добавить свой собственный DNS и выберите Продолжить просмотр  >   записей DNS, чтобы добавить. 
    
    Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.
    
    То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.
    
4. Перейдите [к добавлению записей DNS](create-dns-records-at-any-dns-hosting-provider.md)для подключения домена и выполните действия по добавлению записей на веб-сайте хоста DNS.

5. Следуйте указаниям, чтобы создать записи в своем узле DNS.

## <a name="related-content"></a>См. также:

[Вопросы и ответы о доменах](../setup/domains-faq.yml) (статья)\
[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)\
[Управление доменами](index.yml) (страница ссылки)