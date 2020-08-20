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
description: Добавьте домен в Microsoft 365 в Центре администрирования Microsoft 365, добавив запись DNS на узел DNS. Мастер установки поможет вам выполнить все действия.
ms.openlocfilehash: 0adf8b4dcd5d7bd31038b74a574f449f32bfb037
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814436"
---
# <a name="add-a-domain-to-microsoft-365"></a>Добавление домена в Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.md)**. 
  
 *Чтобы добавить, измените или удалите домены, **необходимо быть** **глобальным** администратором [корпоративного или корпоративного плана.](https://products.office.com/business/office) Эти изменения затрагивают весь клиент, *настроенные администраторы* и *обычные* пользователи не смогут внести такие изменения.*  

 Выполните следующие действия, чтобы добавить, настроить или продолжить настройку домена. 

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
    
2. Перейдите на страницу **"Параметры**  >  **домена".** 

3. Выберите **пункт "Добавить домен".**
    
4. Введите имя домена, который нужно добавить, и нажмите кнопку **"Далее".**
    
5. Выберите способ проверки принадлежности домена.
    
    1. Если ваш домен зарегистрирован на сайте GoDaddy или 1 &amp; 1, нажмите кнопку **"Вход в**  >  **систему Next",** и Корпорация Майкрософт [автоматически настроит ваши ваши записи.](../get-help-with-domains/domain-connect.md)
    
    2. Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки. Если вам не знаком вашадрес адрес или у вас нет доступа к нему, вы можете использовать третий вариант.
    
    3. Вы можете подтвердить владение доменом с помощью записи типа TXT. Установите этот флажок **и** нажмите кнопку "Далее", чтобы просмотреть инструкции о добавлении записи DNS на веб-сайт регистратора. Проверка добавленной записи может занять до 30 минут. 
    
6. Выберите, как вы хотите внести изменения в DNS, необходимые для использования домена системой Office.
    
    1. Choose **Add the DNS records for me** if you want Office to configure your DNS automatically. 
    
  
    2. Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **Этот пункт предназначен для опытных пользователей.**
    
7. Если вы решили  *добавить записи DNS*  самостоятельно, нажмите кнопку **"Далее",** и откроется страница со всеми записями, которые нужно добавить на веб-сайт регистратора для настройки домена. 
    
  
  
    Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи. 
    
    Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    
    
    Если вы хотите подождать, прокрутите экран вниз и выберите этот **шаг пропустить.**
    
8. Нажмите **кнопку** "Готово" — все готово! 

## <a name="add-or-edit-custom-dns-records"></a>Добавление и изменение настраиваемых записей DNS

Выполните указанные ниже действия, чтобы добавить пользовательскую запись для веб-сайта или сторонней службы.

1. Войдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Майкрософт.

2. Перейдите на страницу **"Параметры**   >  **домена".**

3. На странице **Домены** выберите домен. 
    
4. В разделе **"Параметры DNS"** выберите **"Настраиваемые записи";** затем выберите **"Создать настраиваемую запись".**

5. Выберите тип записи DNS, которую необходимо добавить, и введите необходимые данные.
    
6. Нажмите кнопку **Сохранить**.

## <a name="registrars-with-domain-connect"></a>Регистраторы с подключением к домену

[С помощью](https://www.domainconnect.org/) подключаемого домена регистраторы позволяют добавить ваш домен в Microsoft 365 в три этапа, занимаемых минутами. 
  
В мастере мы просто подтвердим, что вы являетесь владельцем домена, а затем настроим записи вашего домена, чтобы электронная почта поступала в Microsoft 365 и другие службы Microsoft 365 (например, Teams) с вами.
  
> [!NOTE]
> Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Регистраторы доменных имен, интегрированные с Microsoft 365

- [1 &amp; 1. ОБЪЕКТЫ СОСТОЯЩИХ ИЗ](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer или WildWestDomains (торговые посредники GoDaddy с использованием размещения DNS SecureServer)
    - [Домены MadDog](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>Что происходит с моей электронной почтой и веб-сайтом?

По окончании настройки выполняется обновление записи MX для вашего домена, в результате чего запись будет указана на Microsoft 365, и все почтовые сообщения для вашего домена будут поступать в Microsoft 365. Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене!
  
Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде. Действия по настройке подключения к домену не влияют на работу вашего веб-сайта.

## <a name="related-articles"></a>Статьи по теме

[Вопросы и ответы о доменах](domains-faq.md)

[Что такое домен?](../get-help-with-domains/what-is-a-domain.md)

[Приобретение доменного имени в Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Настройка домена (инструкции для конкретных узлов)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
