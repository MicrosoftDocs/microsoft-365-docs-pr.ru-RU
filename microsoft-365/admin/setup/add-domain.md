---
title: Добавление домена в Microsoft 365
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
description: Добавьте домен в Microsoft 365 в Центре администрирования Microsoft 365, добавив запись DNS на своем DNS-сайте. Мастер установки поумека процесса.
ms.openlocfilehash: 3e7463bd4cf6b7836a9770421e0b8ce597524a67
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658055"
---
# <a name="add-a-domain-to-microsoft-365"></a>Добавление домена в Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.yml)**. 
  
 *Для добавления, изменения или удаления доменов **необходимо быть** глобальным администратором плана предприятия или [предприятия.](https://products.office.com/business/office)  Эти изменения влияют на весь *клиент,* настроенные администраторы или обычные пользователи не смогут вносить эти изменения.*  

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
    
2. Перейдите на **страницу "Параметры**  >  **доменов".** 

3. Выберите **"Добавить домен".**
    
4. Введите имя домена, который нужно добавить, а затем выберите **"Далее".**
    
5. Выберите, как вы хотите подтвердить владение доменом.
    
    1. Если ваш регистратор доменных [](../get-help-with-domains/domain-connect.md) имен использует [Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365)Корпорация Майкрософт автоматически настроит ваши записи, построив вход в регистратор и подтвердив подключение к Microsoft 365. Вы будете возвращены в Центр администрирования, и корпорация Майкрософт автоматически проверит ваш домен.
    2. Вы можете подтвердить владение доменом с помощью записи типа TXT. Выберите этот  список и выберите "Далее", чтобы увидеть инструкции по добавлению этой записи DNS на веб-сайт регистратора. Проверка записи может занять до 30 минут. 
    3. Вы можете добавить текстовый файл на веб-сайт домена. Выберите и скачайте TXT-файл из мастера установки, а затем загрузите файл в папку верхнего уровня вашего веб-сайта. Путь к файлу должен выглядеть примерно так: `http://mydomain.com/ms39978200.txt` . Мы подтвердим, что вы владеете доменом, найдя файл на вашем веб-сайте.
    
6. Выберите, как вы хотите внести изменения в DNS, необходимые для использования домена корпорацией Майкрософт.
    
    1. Choose **Add the DNS records for me** if your registrar supports Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft will set up [your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.
    2. Выберите **я сам добавлю записи DNS,** если вы хотите присоединить только определенные службы Microsoft 365 к вашему домену или пропустить это сейчас и сделать это позже. **Этот пункт предназначен для опытных пользователей.**

7. Если вы решили самостоятельно добавить записи  *DNS,* выберите "Далее", и вы увидите страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов для регистрации домена. 

    Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи. 
    
    Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    
    
    Если вы хотите подождать позже, либо отойдите от всех служб и нажмите  кнопку **"Продолжить",** либо на предыдущем шаге подключения к домену выберите "Дополнительные параметры" и выберите "Пропустить **сейчас".**
    
8. Select **Finish** — you're done!

## <a name="add-or-edit-custom-dns-records"></a>Добавление и изменение настраиваемых записей DNS

Выполните следующие действия, чтобы добавить пользовательскую запись для веб-сайта или стороной службы.

1. Во sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Перейдите на **страницу "Параметры**   >  **доменов".**

3. На странице **Домены** выберите домен. 
    
4. В **параметрах DNS выберите** **настраиваемые записи;** затем выберите **"Новая настраиваемая запись".**

5. Выберите тип записи DNS, которую необходимо добавить, и введите сведения для новой записи.
    
6. Нажмите **Сохранить**.

## <a name="registrars-with-domain-connect"></a>Регистраторы с подключением к домену

[Регистраторы](https://www.domainconnect.org/) с включенным подключением к домену позволяют добавлять домен в Microsoft 365 в течение трех этапов, который занимает несколько минут. 
  
В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, например Teams, работают с вашим доменом.
  
> [!NOTE]
> Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Интеграция регистраторов Domain Connect с Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer или WildWestDomains (resellers GoDaddy using SecureServer DNS hosting)
    - Примеры:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Что происходит с электронной почтой и веб-сайтом?

После завершения настройки запись MX для вашего домена будет обновлена так, чтобы она указыировала на Microsoft 365, и вся электронная почта для вашего домена начнет отправляться в Microsoft 365. Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене!
  
Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде. Действия по настройке Domain Connect не влияют на ваш веб-сайт.

## <a name="related-articles"></a>Статьи по теме

[Вопросы и ответы о доменах](domains-faq.yml)

[Что такое домен?](../get-help-with-domains/what-is-a-domain.md)

[Приобретение доменного имени в Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Настройка домена (инструкции для конкретных узлов)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
