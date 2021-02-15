---
title: Дополнительные сведения Azure Active Directory для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Дополнительные сведения об Azure Active Directory при переходе с Microsoft Cloud в Германии (Microsoft Cloud Deutschland) на службы Office 365 в новом регионе центра обработки данных в Германии.
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688836"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Дополнительные сведения Azure Active Directory для миграции из Microsoft Cloud Deutschland

Чтобы завершить переход с облачной службы Azure на общеизвестное облако Azure, мы рекомендуем обновить конечную точку проверки подлинности, конечную точку Azure Active Directory (Azure AD) Graph и MS Graph для ваших приложений до конечных точек коммерческого облака, когда конечная точка OpenID Connect (OIDC) будет сообщать о конечных точках коммерческого `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` облака. 
 
**Когда следует внести это изменение?**

Вы получите уведомление на портале Azure или Office, когда клиент завершит миграцию из немецкого облака в коммерческое облако. У вас есть 30 дней после получения этого уведомления для завершения этих обновлений, чтобы ваше приложение продолжает работать для клиентов, которые переносят из облака Azure Germany в общеобъемное облако Azure.
 
Существует три предварительных условия для обновления вашего органа по входу:

 - Конечная точка обнаружения OIDC для клиента возвращает общедоступные конечные точки облака `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` Azure AD.

 - Если ваш клиент настроен для федерации, службы федерации Active Directory (AD FS) обновляются для синхронизации с Azure AD Public. Вы можете следовать инструкциям по обновлению параметров Azure AD Connect для внося это изменение.

 - Приложения ресурсов, при их применении, меняются для потребления маркеров, подписанных Azure AD Germany и Azure AD Public.
 
**Какие приложения?**

Приложение может быть любым из следующих:

- [Одно page app (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Веб-приложение, которое подписывает пользователей](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Веб-приложение, которое вызывает веб-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Защищенный веб-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Веб-API, который вызывает веб-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Классическое приложение](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Приложение "Daemon"](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Мобильное приложение](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Когда приложение переходит к использованию в качестве своего полномочия, маркеры будут `login.microsoftonline.com` подписаны этим новым органом. Если у вас есть какие-либо приложения ресурсов, в которые звонят другие приложения, необходимо разрешить проверку токенов на лях. Это означает, что приложению необходимо разрешить маркеры, подписанные общедоступными облаками Azure AD Germany и Azure AD. Эта проверка токенов необходимо, пока все клиентские приложения, которые звонят в вашу службу, не будут полностью перенесены в общечное облако Azure AD. После миграции приложению ресурсов необходимо принимать только маркеры, подписанные общедоступным облаком Azure AD.

**Что нужно обновить?**

1. Если в Azure в Германии размещено приложение, используемное для проверки подлинности пользователей Azure в Германии или Office 365 Germany, убедитесь, что это приложение используется в качестве органа в контексте проверки `https://login.microsoftonline.com` подлинности.

    - См. контексты проверки подлинности Azure AD.
    - Это относится как к проверке подлинности приложения, так и к любым API, которые могут вызываться вашим приложением (например, Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Обновив конечную точку Azure AD Graph, чтобы она была `https://graph.windows.net` обновлена.

3. Обновим конечную точку MS Graph, чтобы она была `https://graph.microsoft.com` .

4. Обновите все немецкие облачные конечные точки (например, для Exchange Online и SharePoint Online), которые используются вашими приложениями в качестве конечных точек для общедоступных облаков.

5. Обновим параметры среды так, чтобы `AzurePublic` они были (а не) в `AzureGermany` средствах администрирования и сценариях для:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**Как насчет приложений, которые я публикую?**

Если вы публикуете приложение, доступное пользователям за пределами клиента, может потребоваться изменить регистрацию приложения, чтобы обеспечить непрерывность. Другие клиенты, которые используют ваше приложение, могут быть перемещены в другое время, чем ваш клиент. Чтобы гарантировать, что они никогда не потеряют доступ к вашему приложению, необходимо согласиться на синхронизацию вашего приложения из Azure в Германии с azure общедоступным.

## <a name="additional-considerations"></a>Дополнительные рекомендации

Ниже учесть некоторые дополнительные аспекты azure AD.

- Для федераированной проверки подлинности:

  - Не следует создавать, продвигать или понизить уровня федеративного домена во время перехода клиента. После завершения миграции в службу Azure AD (клиент полностью завершен) можно возобновить управление федератными доменами.

  - При использовании федерационной проверки подлинности со службами федерации Active Directory (AD FS) во время миграции не следует вносить изменения в IS-адреса issuer, используемые для всей проверки подлинности с помощью ваших доменных служб Active Directory (AD DS). Изменение URIS-адресов пользователей в домене приведет к сбоям проверки подлинности. ЮРИСовщика можно изменить непосредственно в AD FS или при преобразовании домена из управляемого в федераированный и наоборот. Корпорация Майкрософт рекомендует клиентам не добавлять, удалять и не преобразовывать федераированный домен в переносимом клиенте Azure AD. URIS-адреса выдавлицы можно изменить после завершения миграции.

- Для сетей:

  - Создание сетей с именем IPv6 не работает на портале `http://portal.microsoftazure.de/` Azure. Используйте портал Azure для создания сетей с именем `https://portal.azure.com` IPv6.
 
   - На портале Microsoft Cloud Deutschland нельзя создать надежные диапазоны IP-адресов для параметров службы многофакторной идентификации Azure (MFA). Используйте портал Azure AD для служб Office 365, чтобы создать надежные диапазоны IP-адресов Azure MFA.


- Для условного доступа: 

  - Политики условного доступа со следующими средствами управления предоставлением не поддерживаются до завершения миграции в службы Office 365 (после этапа завершения миграции [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Требовать совместимые устройства
    - Требовать утвержденное приложение
    - Требовать политику защиты приложений
    
  - Интерфейс политики условного доступа выдает ложное предупреждение о том, что для клиента включены значения по умолчанию безопасности, даже если он отключен, а политики условного доступа уже существуют для клиента. Для управления политиками условного доступа следует игнорировать предупреждение или использовать портал служб Office 365. 

- Сценарии Intune поддерживаются только для конечных точек по всему миру после завершения миграции клиента, включая все миграции рабочих нагрузок Office.

- Пользователи Microsoft Cloud Deutschland, которые используют метод уведомления мобильных приложений для запросов MFA, видят в приложении Microsoft Authenticator ObjectId (GUID) пользователя вместо имени основного пользователя (UPN). После завершения миграции клиента Azure AD и его работы в службах Office 365 новые активации Microsoft Authenticator будут отображать upNs пользователей. Существующие учетные записи Microsoft Authenticator продолжат отображать objectId пользователя, но они продолжат работать для уведомлений мобильных приложений. 

- Для клиентов, созданных после 22 октября 2019 г., при миграции клиента в службу Office 365 могут быть автоматически включены значения по умолчанию для системы безопасности. Администраторы клиента могут оставить включенными значения по умолчанию для системы безопасности и зарегистрироваться для MFA или отключить эту функцию. Дополнительные сведения см. в [подзагонии "Отключение стандартных стандартов безопасности".](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > Организации, которые не включены автоматически во время миграции, могут быть автоматически зарегистрированы в будущем, так как в службе Office 365 будет включена функция включения по умолчанию для обеспечения безопасности. Администраторы, явно отключившие или включившие значения по умолчанию для системы безопасности, могут сделать это, обновив функцию в **azure Active Directory > Properties.** После явного включения функции администратором она не будет включена автоматически.

- После миграции клиента на портале Office 365 Germany, а также на портале Office 365 будет предупреждаться о версии Azure AD Connect. Это может быть проигнорировано, если предупреждение о версии больше не отображается после завершения миграции. Если на любом портале есть предупреждение (до или после миграции), необходимо обновить Azure AD Connect. В предупреждении говорится: "Мы обнаружили, что вы используете устаревшее средство синхронизации каталогов. Мы рекомендуем перейти в Центр загрузки Майкрософт, чтобы получить последнюю версию Azure AD Connect".

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Переход:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [функций](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
