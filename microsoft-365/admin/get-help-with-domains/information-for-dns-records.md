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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Соберите значения и сведения, необходимые для создания записей DNS для подключения домена к Microsoft 365 подписке.
ms.openlocfilehash: e65d53269f5fb8625b12c4eb22f78516818045be
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635730"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Сбор сведений, необходимых для создания записей DNS

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Шаг 1. Поиск значения записи TXT и проверка

::: moniker range="o365-worldwide"

1. В центре Microsoft 365 администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a>

::: moniker-end

::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a>

::: moniker-end
    
2. На странице **Домены** выберите домен, а затем выберите **настройку Начните.** Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.
    
3. На странице **Проверка домена** выберите **Добавить запись TXT** вместо этого, а затем выберите **Далее**.
    
4. Скопируйте **показанные значения TXT.** Выглядит так: **MS=msXXXXXXXXXXX.** 
    
5. Перейдите [к созданию записей DNS](create-dns-records-at-any-dns-hosting-provider.md)в любом поставщике DNS-хостинга и выберите свой DNS-хост из списка регистраторов, чтобы пошаговых инструкций.
    
6. Выполните действия по созданию записи TXT (или записи MX) в вашем DNS-хозяйте, а затем проверьте домен в Microsoft 365.

7. Удалите запись TXT (или запись MX) с вашего DNS-хоста после проверки домена в Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Шаг 2. Поиск значения записи MX для электронной почты и других

::: moniker range="o365-worldwide"

1. В центре Microsoft 365 администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a>

::: moniker-end
    
2. На странице **Домены** щелкните свой домен. 
    
3. В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.
    
    Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.
    
    То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.
    
4. Перейдите к созданию записей [DNS](create-dns-records-at-any-dns-hosting-provider.md)в любом поставщике DNS-хостинга, а затем выберите свой DNS-хост из списка регистраторов, чтобы пошаговых инструкций по добавлению записей на веб-сайте этого ведущего DNS.
    
5. Следуйте указаниям, чтобы создать записи в своем узле DNS.

## <a name="related-content"></a>См. также:

[Вопросы и ответы о доменах](../setup/domains-faq.yml) (статья)\
[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)\
[Управление доменами](index.yml) (страница ссылки)