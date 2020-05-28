---
title: Сбор сведений, необходимых для создания записей DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Сведения о том, как найти значения и сведения, необходимые для создания записей DNS для Microsoft 365. '
ms.openlocfilehash: fddd1180f2dd80ffeec2aeec49ed821055dd5f15
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399912"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Сбор сведений, необходимых для создания записей DNS

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Шаг 1: Найдите значение записи TXT и проверьте

::: moniker range="o365-worldwide"

1. В центре администрирования Microsoft 365 перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> установки".

::: moniker-end

::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу " **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> установки".

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу " **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> установки".

::: moniker-end
    
2. На странице **домены** выберите свой домен, а затем нажмите кнопку **запустить программу установки**. Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.
    
3. На странице **Проверка домена** выберите **Добавить запись типа TXT**, а затем нажмите кнопку **Далее**.
    
4. Скопируйте отображаемое **значение txt** . Он выглядит следующим образом: **MS = мскскскскскскскскс**. 
    
5. Перейдите к разделу [Создание записей DNS для любого поставщика услуг размещения DNS](create-dns-records-at-any-dns-hosting-provider.md)и выберите узел DNS из списка регистраторов, чтобы просмотреть пошаговые инструкции.
    
6. Выполните действия, необходимые для создания записи TXT (или записи MX) на узле DNS, а затем убедитесь, что домен возвращен в Microsoft 365.

7. Удалите запись TXT (или запись MX) с узла DNS после проверки домена в Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Шаг 2: поиск значения записи MX для электронной почты и т. д.

::: moniker range="o365-worldwide"

1. В центре администрирования Microsoft 365 перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> установки".

::: moniker-end
    
::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу " **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> установки".

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу " **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> установки".

::: moniker-end
    
2. На странице **Домены** щелкните свой домен. 
    
3. В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.
    
    Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.
    
    То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.
    
4. Перейдите к разделу [Создание DNS-записей на любом поставщике услуг размещения DNS](create-dns-records-at-any-dns-hosting-provider.md), а затем выберите узел DNS из списка регистраторов, чтобы просмотреть пошаговые инструкции по добавлению записей на веб-сайте узла DNS.
    
5. Следуйте указаниям, чтобы создать записи в своем узле DNS.
