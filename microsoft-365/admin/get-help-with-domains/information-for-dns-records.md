---
title: Сбор необходимых сведений для создания DNS-записей Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Сведения о том, как найти значения и сведения, необходимые для создания записей DNS для Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: d6093dd8a7e8d901be7b172a31dcd0e56c549ab3
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "43188997"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>Сбор необходимых сведений для создания DNS-записей Office 365

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Шаг 1: Найдите значение записи TXT и проверьте

1. В центре администрирования Microsoft 365 перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **установки** \> ".

::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> .

::: moniker-end
    
2. На странице **домены** выберите свой домен, а затем нажмите кнопку **запустить программу установки**. Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.
    
3. На странице **Проверка домена** выберите **Добавить запись типа TXT**, а затем нажмите кнопку **Далее**.
    
4. Скопируйте отображаемое **значение txt** . Он выглядит следующим образом: **MS = мскскскскскскскскс**. 
    
5. Перейдите к разделу [Создание записей DNS для любого поставщика услуг размещения DNS](create-dns-records-at-any-dns-hosting-provider.md)и выберите узел DNS из списка регистраторов, чтобы просмотреть пошаговые инструкции.
    
6. Выполните действия, чтобы создать запись TXT (или MX) на своем узле DNS, а затем проверьте домен в Office 365.

7. Удалите запись TXT (или запись MX) с узла DNS, когда домен будет проверен в Office 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Шаг 2: поиск значения записи MX для электронной почты и т. д.

1. В центре администрирования Microsoft 365 перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **установки** \> ".
    
::: moniker range="o365-germany"

1. В центре администрирования перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. В центре администрирования перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> .

::: moniker-end
    
2. На странице **Домены** щелкните свой домен. 
    
3. В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.
    
    Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.
    
    То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.
    
4. Перейдите к разделу [Создание DNS-записей на любом поставщике услуг размещения DNS](create-dns-records-at-any-dns-hosting-provider.md), а затем выберите узел DNS из списка регистраторов, чтобы просмотреть пошаговые инструкции по добавлению записей на веб-сайте узла DNS.
    
5. Следуйте указаниям, чтобы создать записи в своем узле DNS.
