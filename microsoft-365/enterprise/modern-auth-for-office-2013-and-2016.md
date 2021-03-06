---
title: Современная проверка подлинности в клиентских приложениях Office 2013 и Office 2016
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Узнайте, Microsoft 365 современные функции проверки подлинности работают по-разному для Office 2013 и 2016 г.
ms.openlocfilehash: 60b1729d9830fd12141d162c4fe721267e52d437
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229843"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Как работает современная проверка подлинности Office 2013, Office 2016 и Office 2019 г.

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Ознакомьтесь с этой статьей, чтобы узнать, как клиентские приложения Office 2013, Office 2016 и Office 2019 годов используют современные функции проверки подлинности на основе конфигурации проверки подлинности в клиенте Microsoft 365 для Exchange Online, SharePoint Online и Skype для бизнеса Online.

> [!NOTE]
> Устаревшие клиентские приложения, например Office 2010 и Office для Mac 2011 г., не поддерживают современную проверку подлинности и могут использоваться только при базовой проверке подлинности.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Доступность современной проверки подлинности для Microsoft 365 служб

Для служб Microsoft 365 состояние современной проверки подлинности по умолчанию:

- Включено **для** Exchange Online по умолчанию. См. в Exchange Online включить или отключить [современную проверку](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) подлинности.

- Включено **для** SharePoint Online по умолчанию.

- Включено **для** Skype для бизнеса Online по умолчанию. См. [в Skype для бизнеса Online для современной](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)проверки подлинности, чтобы отключить ее или включить.

> [!NOTE]
> Для клиентов, созданных **до** 1 августа 2017 г., современная проверка подлинности по умолчанию **отключена** в Exchange Online и Skype для бизнеса Online.

## <a name="sign-in-behavior-of-office-client-apps"></a>Вход в клиентские Office приложений

Office 2013 г. клиентские приложения по умолчанию поддерживают устаревшую проверку подлинности. Legacy означает, что они поддерживают либо помощника по входу в Microsoft Online, либо базовую проверку подлинности. Чтобы эти клиенты использовали современные функции проверки подлинности, Windows клиент должен иметь набор ключей реестра. Инструкции см. в [инструкции Enable Modern Authentication for Office 2013 на Windows устройствах.](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)

Чтобы включить современную проверку подлинности для устройства с Windows (например, ноутбука или планшета), на котором установлен Microsoft Office 2013, необходимо настроить указанные ниже разделы реестра. Это нужно сделать для каждого устройства, на котором вы хотите включить современную проверку подлинности.

|**Раздел реестра**|**Тип**|**Значение** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |

Узнайте, как использовать современную проверку подлинности [(ADAL)](./hybrid-modern-auth-overview.md) с помощью Skype для бизнеса, чтобы узнать, как она работает с Skype для бизнеса.

Office 2016 и Office 2019 года клиенты поддерживают современную проверку подлинности по умолчанию, и для использования этих новых потоков клиенту не требуется никаких действий. Однако для использования устаревшей проверки подлинности необходимы явные действия.

Щелкните ссылки ниже, чтобы узнать, как Office 2013, Office 2016 и Office 2019 г. проверка подлинности клиентов работает с Microsoft 365 службами в зависимости от того, включена или не включена современная проверка подлинности.

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [Skype для бизнеса Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

В следующей таблице описывается поведение проверки подлинности для Office 2013, Office 2016 и Office 2019 г. при подключении к Exchange Online с современной проверкой подлинности или без нее.

|Office клиентской версии приложения****|Ключ реестра присутствует?****|Современная проверка подлинности на?****|Поведение проверки подлинности с включенной современной проверкой подлинности для клиента (по умолчанию)****|Поведение проверки подлинности с современной проверкой подлинности отключено для клиента****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Нет <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Да  <br/> |Проверка подлинности в Outlook 2013, 2016 или 2019 годах. <br/> [Дополнительные сведения](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Заставляет современную проверку подлинности в Outlook клиенте.<br/> |
|Office 2019  <br/> |Нет или EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |
|Office 2019  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |
|Office 2019  <br/> |Да, EnableADAL=0  <br/> |Нет  <br/> |Обычная проверка подлинности  <br/> |Обычная проверка подлинности  <br/> |
|Office 2016  <br/> |Нет <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Да  <br/> |В 2013, 2016 или 2019 годах будет происходить современная проверка подлинности. <br/> [Дополнительные сведения](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Заставляет современную проверку подлинности в Outlook клиенте.<br/> |
|Office 2016  <br/> |Нет или EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |
|Office 2016  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |
|Office 2016  <br/> |Да, EnableADAL=0  <br/> |Нет  <br/> |Обычная проверка подлинности  <br/> |Обычная проверка подлинности  <br/> |
|Office 2013  <br/> |Нет  <br/> |Нет  <br/> |Обычная проверка подлинности  <br/> |Обычная проверка подлинности  <br/> |
|Office 2013  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется базовая проверка подлинности. Сервер отказывается от современной проверки подлинности, если клиент не включен.  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

В следующей таблице описывается поведение проверки подлинности для Office 2013, Office 2016 и Office 2019 г. при подключении к SharePoint Online с современной проверкой подлинности или без нее.

|Office клиентской версии приложения****|Ключ реестра присутствует?****|Современная проверка подлинности на?****|Поведение проверки подлинности с включенной современной проверкой подлинности для клиента (по умолчанию)****|Поведение проверки подлинности с современной проверкой подлинности отключено для клиента****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Нет или EnableADAL = 1  <br/> |Да  <br/> |Только современная проверка подлинности.  <br/> |Невыполнение подключения.  <br/> |
|Office 2019  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Только современная проверка подлинности.  <br/> |Невыполнение подключения.  <br/> |
|Office 2019  <br/> |Да, EnableADAL = 0  <br/> |Нет  <br/> |Только помощник по входу в Microsoft Online.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |
|Office 2016  <br/> |Нет или EnableADAL = 1  <br/> |Да  <br/> |Только современная проверка подлинности.  <br/> |Невыполнение подключения.  <br/> |
|Office 2016  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Только современная проверка подлинности.  <br/> |Невыполнение подключения.  <br/> |
|Office 2016  <br/> |Да, EnableADAL = 0  <br/> |Нет  <br/> |Только помощник по входу в Microsoft Online.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |
|Office 2013  <br/> |Нет  <br/> |Нет  <br/> |Только помощник по входу в Microsoft Online.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |
|Office 2013  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Только современная проверка подлинности.  <br/> |Невыполнение подключения.  <br/> |

### <a name="skype-for-business-online"></a>Skype для бизнеса Online
<a name="BK_SFBO"> </a>

В следующей таблице описывается поведение проверки подлинности для Office 2013, Office 2016 и Office 2019 г. при подключении к Skype для бизнеса Online с современной проверкой подлинности или без нее.

|Office клиентской версии приложения****|Ключ реестра присутствует?****|Современная проверка подлинности на?****|Поведение проверки подлинности с помощью современной проверки подлинности включено для клиента****|Поведение проверки подлинности с современной проверкой подлинности отключено для клиента (по умолчанию)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Нет или EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |
|Office 2019  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |
|Office 2019  <br/> |Да, EnableADAL = 0  <br/> |Нет  <br/> |Только помощник по входу в Microsoft Online.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |
|Office 2016  <br/> |Нет или EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |
|Office 2016  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |
|Office 2016  <br/> |Да, EnableADAL = 0  <br/> |Нет  <br/> |Только помощник по входу в Microsoft Online.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |
|Office 2013  <br/> |Нет  <br/> |Нет  <br/> |Только помощник по входу в Microsoft Online.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |
|Office 2013  <br/> |Да, EnableADAL = 1  <br/> |Да  <br/> |Сначала предпринята попытка современной проверки подлинности. Если сервер отказывается от современного подключения к проверке подлинности, используется помощник по входу в Microsoft Online. Сервер отказывается от современной проверки подлинности, Skype для бизнеса клиенты Online не включены.  <br/> |Только помощник по входу в Microsoft Online.  <br/> |

## <a name="see-also"></a>См. также

[Включение современной проверки подлинности для Office 2013 на устройствах с Windows](../admin/security-and-compliance/enable-modern-authentication.md)

[Многофакторная проверка подлинности для Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Во входе Microsoft 365 с многофакторной проверкой подлинности](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)