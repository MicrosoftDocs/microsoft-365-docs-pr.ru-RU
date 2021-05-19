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
description: В этой статье вы узнаете о средствах и методах, которые можно использовать для мониторинга и Microsoft 365 подключения.
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538811"
---
# <a name="monitor-microsoft-365-connectivity"></a>Проверка подключения Microsoft 365

После развертывания Microsoft 365 вы можете Microsoft 365 подключение с помощью некоторых средств и методов ниже. Вы хотите понять официальные [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) рекомендации по охране и непрерывности служб, а также рекомендации по использованию Microsoft 365 в [медленной сети.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) Вы также хотите захватить приложение [администрирования Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) и закладки нашего Microsoft 365 для [бизнеса - Справка администратора](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).
  
## <a name="monitoring-microsoft-365-connectivity"></a>Мониторинг Microsoft 365 подключения

|||
|:-----|:-----|
|**Получение уведомления о новых Microsoft 365 конечных точках** <br/> |Если вы управляете конечными точками [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)вы хотите получать уведомления при публикации новых конечных точек, вы можете подписаться на наш RSS-канал с помощью вашего любимого читателя RSS. Вот как [подписаться через Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) или вы можете [иметь RSS-обновления каналов по электронной почте.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Используйте System Center для мониторинга Microsoft 365** <br/> |Если вы используете Microsoft System Center, вы можете [](https://www.microsoft.com/download/details.aspx?id=43708) скачать пакет System Center управления для Office 365, чтобы начать мониторинг Microsoft 365 сегодня. Дополнительные сведения см. в руководстве по операциям пакетов управления. <br/> |
|**Наблюдение за работоспособностью Azure ExpressRoute** <br/> |Если вы подключаете Microsoft 365 Azure ExpressRoute для Microsoft 365, необходимо убедиться, что вы используете панель мониторинга состояния службы Microsoft 365, а также время устранения неполадок Azure с помощью [службы Azure Resource.](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**Использование Azure AD Connect Health с AD FS** <br/> |Если вы используете службу AD FS для единой Sign-On с Microsoft 365, необходимо приступить к использованию Azure AD Подключение Health для мониторинга инфраструктуры [AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**Программный мониторинг Microsoft 365** <br/> |Обратитесь к нашим рекомендациям по [API Microsoft 365 управления.](/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Связанные статьи

[Настройка Microsoft 365 корпоративный служб и приложений](configure-services-and-applications.md)
  
[Подготовь организацию к Microsoft 365 корпоративный](get-your-organization-ready-for-office-365.md)
  
[Планирование сети и настройка производительности для Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365 интеграции с локальной средой](microsoft-365-integration.md)
  
[Управление Microsoft 365 конечными точками](managing-office-365-endpoints.md)
