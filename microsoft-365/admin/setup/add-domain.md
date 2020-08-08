---
title: Добавление домена в Microsoft 365
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Добавьте свой домен в Microsoft 365 в центре администрирования Microsoft 365, добавив запись DNS на узел DNS. Мастер установки проводит вас через процесс.
ms.openlocfilehash: 8b70466e5cf82d9cf5be67162263f28ab5bd0d5d
ms.sourcegitcommit: 20c219332270f1013d48b39773dd0e48dabad9e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "46592302"
---
# <a name="add-a-domain-to-microsoft-365"></a>Добавление домена в Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.md)**. 
  
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
    
2. Перейдите на страницу **Settings**"  >  **домены** параметров". 

3. Выберите **Добавить домен**.
    
4. Введите имя домена, который вы хотите добавить, и нажмите кнопку **Далее**.
    
5. Выберите способ проверки того, что вы владеете доменом.
    
    1. Если ваш домен зарегистрирован на GoDaddy или 1 &amp; 1, нажмите кнопку **войти**  >  **Далее** , чтобы Майкрософт [настроила свои записи автоматически](../get-help-with-domains/domain-connect.md).
    
    2. Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки. Если вы не узнаете или не можете получить доступ к записи электронной почты, вы можете использовать третий вариант.
    
    3. Вы можете подтвердить владение доменом с помощью записи типа TXT. Установите этот флажок и нажмите кнопку **Далее** , чтобы просмотреть инструкции по добавлению этой записи DNS на веб-сайт регистратора. Проверка после добавления записи может занять до 30 минут. 
    
6. Выберите способ внесения изменений DNS, необходимых для использования домена в Office.
    
    1. Выберите **добавить записи DNS для меня,** если вы хотите, чтобы Office автоматически настроил DNS. 
    
  
    2. Нажмите **я буду добавлять записи DNS самостоятельно** , если вы хотите присоединить к домену только определенные службы Microsoft 365, или если вы хотите пропустить эту операцию, и сделать это позже. **Этот пункт предназначен для опытных пользователей.**
    
7. Если вы решили *добавить записи DNS самостоятельно* , нажмите кнопку **Далее** , чтобы увидеть страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов, чтобы настроить свой домен. 
    
  
  
    Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи. 
    
    Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    
    
    Если вы хотите подождать позже, прокрутите страницу вниз и выберите **пропустить этот шаг**.
    
8. Нажмите кнопку Готово, чтобы **завершить работу** . 

## <a name="add-or-edit-custom-dns-records"></a>Добавление и изменение настраиваемых записей DNS

Выполните указанные ниже действия, чтобы добавить настраиваемую запись для веб-сайта или сторонней службы.

1. Войдите в центр администрирования Майкрософт по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Перейдите на страницу **Settings**"   >  **домены** параметров".

3. На странице **Домены** выберите домен. 
    
4. В разделе **параметры DNS**выберите **Настраиваемые записи**; затем выберите **создать настраиваемую запись**.

5. Выберите тип записи DNS, которую вы хотите добавить, и введите сведения для новой записи.
    
6. Нажмите **Сохранить**.

## <a name="registrars-with-domain-connect"></a>Регистраторы с подключением к домену

Регистраторы с поддержкой [подключения к домену](https://www.domainconnect.org/) позволяют добавить свой домен в Microsoft 365 в процессе, сокоторый в течение трех этапов. 
  
В мастере мы просто подтверждаю, что вы владеете доменом и автоматически настроили записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Майкрософт 365, например команды, работающие с доменом.
  
> [!NOTE]
> Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Служба регистраторов подключений к доменам интеграция с Microsoft 365

- [1 &amp; 1 ионос](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [CloudFlare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [плеск](https://www.plesk.com/)
- [медиатемпле](https://mediatemple.net/)
- Секуресервер или Вилдвестдомаинс (GoDaddy торговые посредники, использующие службу хостинга на Секуресервер DNS)
    - [Домены Маддог](https://www.maddogdomains.com/)
    - [чеапнамес](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>Что происходит с электронной почтой и веб-сайтом?

После завершения установки запись MX для вашего домена будет обновлена, чтобы она ссылалась на Microsoft 365, а вся электронная почта для вашего домена будет начинаться с Microsoft 365. Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене.
  
Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде. Действия по настройке подключения к домену не повлияют на ваш веб-сайт.

## <a name="related-articles"></a>Статьи по теме

[Вопросы и ответы о доменах](domains-faq.md)

[Что такое домен?](../get-help-with-domains/what-is-a-domain.md)

[Приобретение доменного имени в Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Настройка домена (инструкции для конкретных узлов)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Получение справки о доменах](../get-help-with-domains/get-help-with-domains.md)
