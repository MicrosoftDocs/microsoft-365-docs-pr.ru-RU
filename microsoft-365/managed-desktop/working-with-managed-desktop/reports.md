---
title: Работа с отчетами
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917686"
---
# <a name="work-with-reports"></a>Работа с отчетами

Microsoft Managed Desktop предоставляет несколько отчетов и панелей мониторинга, которые ИТ-администраторы в организации могут использовать для понимания различных аспектов популяции устройств.Отчеты можно найти в двух местах: [в Microsoft Endpoint Manager](https://endpoint.microsoft.com) и в Центре администрирования Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Отчеты в Microsoft Endpoint Manager

Консоль Microsoft Endpoint Manager объединяет отчеты из нескольких продуктов в одном расположении, чтобы помочь вам отслеживать и исследовать проблемы с конфигурацией и устройствами организации Azure AD ("клиент"). Рабочий стол Microsoft Managed имеет раздел **"Отчеты"** в основном меню, в котором можно найти отчеты, специфические для управления устройствами, зарегистрированными в Microsoft Managed Desktop.

Эти отчеты включают:
- **Управляемые устройства**  >  **Обновления функций.** В этом представлении показан общий статус обновлений функций на управляемых настольных устройствах Майкрософт.
- **Управляемые устройства**  >  **Обновления Office.** В этом представлении показан общий статус обновлений Office на управляемых настольных устройствах Майкрософт.

Кроме того, в нескольких местах в Microsoft Endpoint Manager можно фильтровать отчеты из других групп продуктов, чтобы конкретно включать или исключать устройства, управляемые Microsoft Managed Desktop. Эти отчеты интегрировали эту возможность фильтрации:

- [Все устройства](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Соответствие устройства требованиям](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Некомплиентные устройства](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Настраиваемые роли управляемых настольных компьютеров Майкрософт гарантируют доступ только к отчетам Microsoft Managed Desktop. Чтобы получить доступ к другим частям Microsoft Endpoint Manager, таким как **Все** устройства, см. в этой ссылке управление доступом на основе ролей [с помощью Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Отчеты в Центре администрирования Microsoft 365

Вы можете найти отчеты о microsoft Managed Desktop, открыв Центр администрирования Microsoft  [365,](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)а затем перейдите к отчетам и выбрав microsoft **Managed Desktop.** Вы также можете следовать прямой ссылке на эти отчеты из **вкладки Microsoft Managed Desktop** на домашней странице [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Эти отчеты включают: 

- [Сведения об использовании](usage-insights.md) . В этом представлении метрики использования для устройств Microsoft Managed Desktop.
- [Сведения о надежности](reliability-insights.md) . В этом представлении содержится сводка о состоянии здоровья управляемых устройств.
- [Сведения о батарее](battery-insights.md) . В этом представлении показано, как расход энергии приложений и прогнозируемый срок службы батареи для устройств в вашей среде.
- [Сведения об обновлении безопасности](security-update-insights.md) Windows . В этом представлении показаны сведения о состоянии обновлений безопасности для устройств Microsoft Managed Desktop.

 ## <a name="inventory-data"></a>Данные инвентаризации

Помимо других отчетов, можно экспортировать сведения о устройствах, управляемых Microsoft Managed Desktop. В **представлении Устройств** области **Устройств** в Microsoft Endpoint Manager используйте вкладку Экспорт все, чтобы  [скачать подробный отчет о запасах.](device-inventory-report.md)