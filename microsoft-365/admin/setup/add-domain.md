---
title: Добавление домена в Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Добавьте свой домен в Office 365 в центре администрирования Microsoft 365, добавив запись DNS на узел DNS. Мастер установки проводит вас через процесс.
ms.openlocfilehash: 746163b83190a73326ad589b8e3bc9377ddaa9b4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209644"
---
# <a name="add-a-domain-to-office-365"></a>Добавление домена в Office 365

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](domains-faq.md)**. 
  
 *Чтобы добавить, изменить или удалить домены, **необходимо** быть **глобальным администратором** [плана бизнеса или предприятия](https://products.office.com/business/office). Эти изменения затрагивают весь клиент, *Администраторы* или *обычные пользователи* не смогут вносить эти изменения.*  

 Выполните указанные ниже действия, чтобы добавить, настроить или продолжить настройку домена. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Перейдите на страницу "**домены** **установки** > ". 

3. Выберите **Добавить домен**.
    
4. Введите имя домена, который вы хотите добавить, и нажмите кнопку **Далее**.
    
5. Выберите способ проверки того, что вы владеете доменом.
    
    1. Если ваш домен зарегистрирован на GoDaddy или 1&amp;1, установите флажок **войти** > **Далее, после** чего Office 365 настроит [свои записи автоматически](../get-help-with-domains/domain-connect.md).
    
    2. Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки. Если вы не узнаете или не можете получить доступ к записи электронной почты, вы можете использовать третий вариант.
    
    3. Вы можете подтвердить владение доменом с помощью записи типа TXT. Установите этот флажок и нажмите кнопку **Далее** , чтобы просмотреть инструкции по добавлению этой записи DNS на веб-сайт регистратора. Проверка после добавления записи может занять до 30 минут. 
    
6. Выберите способ внесения изменений DNS, необходимых для использования домена в Office.
    
    1. Выберите **добавить записи DNS для меня,** если вы хотите, чтобы Office автоматически настроил DNS. 
    
  
    2. Нажмите **я буду добавлять записи DNS самостоятельно** , если вы хотите присоединить к вашему домену только определенные службы Office 365, или если вы хотите пропустить это действие и сделать это позже. **Этот пункт предназначен для опытных пользователей.**
    
7. Если вы решили *добавить записи DNS самостоятельно* , нажмите кнопку **Далее** , чтобы увидеть страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов, чтобы настроить свой домен. 
    
  
  
    Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Просмотрите наш список [инструкций для конкретных хостов](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи. 
    
    Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    
    
    Если вы хотите подождать позже, прокрутите страницу вниз и выберите **пропустить этот шаг**.
    
8. Нажмите кнопку Готово, чтобы **завершить работу** . 

## <a name="related-articles"></a>Статьи по теме

[Вопросы и ответы о доменах](domains-faq.md)

[Что такое домен?](../get-help-with-domains/what-is-a-domain.md)

[Приобретение доменного имени в Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Настройка домена (инструкции для конкретных узлов)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Получение справки по доменам Office 365](../get-help-with-domains/get-help-with-domains.md)
