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
description: 'Узнайте, как найти значения и сведения, необходимые для создания записей DNS для Microsoft 365. '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126375"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Сбор сведений, необходимых для создания записей DNS

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Шаг 1. Поиск значения записи TXT и проверка

::: moniker range="o365-worldwide"

1. В Центре администрирования Microsoft 365 перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">установки".</a>

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **"Домены** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">установки".</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **"Домены** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">установки".</a>

::: moniker-end
    
2. На странице **"Домены"** выберите свой домен, а затем выберите **"Начать установку".** Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.
    
3. На странице **"Проверка домена"** выберите **"Добавить запись TXT",** а затем выберите **"Далее".**
    
4. Скопируйте **показанные значения TXT.** Он выглядит так: **MS=msXXXXXXXXX.** 
    
5. Перейдите к созданию [записей DNS](create-dns-records-at-any-dns-hosting-provider.md)у любого поставщика услуг размещения DNS и выберите свой хост DNS в списке регистраторов, чтобы увидеть пошаговых инструкций.
    
6. Выполните действия по созданию TXT-записи (или записи MX) на своем DNS-сайте, а затем проверьте домен обратно в Microsoft 365.

7. Удалите запись TXT (или запись MX) с хоста DNS после проверки домена в Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Шаг 2. Поиск значения записи MX для электронной почты и других

::: moniker range="o365-worldwide"

1. В Центре администрирования Microsoft 365 перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">установки".</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **"Настройка** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">доменов".</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **"Домены** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">установки".</a>

::: moniker-end
    
2. На странице **Домены** щелкните свой домен. 
    
3. В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.
    
    Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.
    
    То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.
    
4. Перейдите к созданию записей DNS у любого поставщика услуг размещения [DNS,](create-dns-records-at-any-dns-hosting-provider.md)а затем выберите свой DNS-сайт в списке регистраторов, чтобы увидеть пошаговых инструкций по добавлению записей на веб-сайте этого DNS-сайта.
    
5. Следуйте указаниям, чтобы создать записи в своем узле DNS.
