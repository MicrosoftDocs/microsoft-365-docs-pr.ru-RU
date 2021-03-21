---
title: Проверка подключения Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: В этой статье вы узнаете о средствах и методах, которые можно использовать для мониторинга и поддержания подключения Microsoft 365.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920780"
---
# <a name="monitor-microsoft-365-connectivity"></a>Проверка подключения Microsoft 365

После развертывания Microsoft 365 вы можете поддерживать подключение Microsoft 365 с помощью некоторых средств и методов ниже. Вы хотите понять официальные [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) рекомендации по охране и непрерывности служб, а также рекомендации по использованию [Microsoft 365 в медленной сети.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) Вы также хотите захватить приложение [администрирования Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) и закладки нашего [Microsoft 365 для бизнеса - Справка администратора](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).
  
## <a name="monitoring-microsoft-365-connectivity"></a>Мониторинг подключения Microsoft 365

|||
|:-----|:-----|
|**Получение уведомления о новых конечных точках Microsoft 365** <br/> |Если вы управляете конечными точками [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)вы хотите получать уведомления при публикации новых конечных точек, вы можете подписаться на наш RSS-канал с помощью вашего любимого читателя RSS. Вот как [подписаться через Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) или вы можете [иметь RSS-обновления каналов по электронной почте.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Использование Центра систем для мониторинга Microsoft 365** <br/> |Если вы используете Центр систем Microsoft, вы можете скачать пакет управления системным центром для [Office 365,](https://www.microsoft.com/download/details.aspx?id=43708) чтобы начать мониторинг Microsoft 365 уже сегодня. Дополнительные сведения см. в руководстве по операциям пакетов управления или в этом блоге post [Office365 Monitoring с помощью System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Наблюдение за работоспособностью Azure ExpressRoute** <br/> |При подключении к Microsoft 365 с помощью Azure ExpressRoute для Microsoft 365 необходимо убедиться, что вы используете панель мониторинга здоровья служб Майкрософт 365, а также время устранения неполадок Azure с помощью [службы Azure Resource.](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**Использование Azure AD Connect Health с AD FS** <br/> |Если вы используете AD FS для единой системы Sign-On Microsoft 365, необходимо приступить к использованию Службы подключения Azure AD для мониторинга инфраструктуры [AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**Программный мониторинг Microsoft 365** <br/> |Обратитесь к нашим рекомендациям по API управления [Microsoft 365](/office/office-365-management-api/office-365-management-apis-overview).  <br/> |

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Родственные темы

[Настройка корпоративных служб и приложений Microsoft 365](configure-services-and-applications.md)
  
[Готовьтесь к microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Планирование сети и настройка производительности для Microsoft 365](network-planning-and-performance.md)
  
[Интеграция Microsoft 365 с локальной средой](microsoft-365-integration.md)
  
[Управление конечными точками Microsoft 365](managing-office-365-endpoints.md)