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
description: В этой статье вы узнаете о средствах и методах, которые можно использовать для отслеживания и поддержки подключения к Microsoft 365.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692974"
---
# <a name="monitor-microsoft-365-connectivity"></a>Проверка подключения Microsoft 365

После развертывания Microsoft 365 вы можете поддерживать подключение к Microsoft 365 с помощью некоторых средств и методов, которые приведены ниже. Вам необходимо понять официальные [](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) рекомендации по обеспечению безопасности и непрерывности обслуживания, а также нашим рекомендациям по использованию [Microsoft 365 в медленных сетях.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) Вы также захотите захватить приложение для администрирования [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) и закладки microsoft 365 для бизнеса [справку для администраторов.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Мониторинг подключения Microsoft 365

|||
|:-----|:-----|
|**Получение уведомлений о новых конечных точках Microsoft 365** <br/> |Если вы управляете конечными точками [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)вы хотите получать уведомления при публикации новых конечных точек, вы можете подписаться на наш RSS-канал с помощью вашего любимого RSS-читателя. Вот как [подписаться через Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) или вы можете отправить вам по электронной почте обновления [RSS-канала.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Использование System Center для мониторинга Microsoft 365** <br/> |Если вы используете Microsoft System Center, вы можете скачать [пакет управления System Center для Office 365,](https://www.microsoft.com/download/details.aspx?id=43708) чтобы начать мониторинг Microsoft 365 уже сегодня. Дополнительные сведения см. в руководстве по работе с пакетом управления или в записи блога "Мониторинг [Office 365 с помощью System Centre Operations Manager"](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Наблюдение за работоспособностью Azure ExpressRoute** <br/> |При подключении к Microsoft 365 с помощью Azure ExpressRoute для Microsoft 365 необходимо убедиться, что вы используете панель мониторинга состояния службы Microsoft 365, а также Azure, сокращая время устранения неполадок с состоянием [ресурсов Azure](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**Использование Azure AD Connect Health с AD FS** <br/> |Если вы используете AD FS для единого Sign-On с Microsoft 365, вам необходимо начать использовать Azure AD Connect Health для отслеживания инфраструктуры [AD FS.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/)  <br/> |
|**Программный мониторинг Microsoft 365** <br/> |Обратитесь к нашим рекомендациям по API управления [Microsoft 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)
  
## <a name="related-topics"></a>Связанные статьи

[Настройка служб и приложений Microsoft 365 корпоративный](configure-services-and-applications.md)
  
[Подготовьтесь к microsoft 365 корпоративный для своей организации](get-your-organization-ready-for-office-365.md)
  
[Планирование сети и настройка производительности для Microsoft 365](network-planning-and-performance.md)
  
[Интеграция Microsoft 365 с локальной средой](microsoft-365-integration.md)
  
[Управление конечными точками Microsoft 365](managing-office-365-endpoints.md)
