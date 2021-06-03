---
title: Работа с отчетами
description: Различные отчеты, доступные в компьютеры, управляемые Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729972"
---
# <a name="work-with-reports"></a>Работа с отчетами

компьютеры, управляемые Майкрософт предоставляет несколько отчетов и панелей мониторинга, которые ИТ-администраторы в организации могут использовать для понимания различных аспектов популяции устройств.Отчеты можно найти в двух местах: в [Microsoft Endpoint Manager](https://endpoint.microsoft.com) и в [центре администрирования Microsoft 365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Отчеты в Microsoft Endpoint Manager

Консоль Microsoft Endpoint Manager объединяет отчеты из нескольких продуктов в одном расположении, чтобы помочь вам отслеживать и исследовать проблемы с конфигурацией и устройствами организации Azure AD ("клиент"). Рабочий стол Microsoft Managed имеет раздел **"Отчеты"** в основном меню, в котором можно найти отчеты, компьютеры, управляемые Майкрософт управления зарегистрированными устройствами.

Эти отчеты включают:
- **Управляемые устройства**  >  **Обновления функций.** В этом представлении показан общий статус обновлений функций на компьютеры, управляемые Майкрософт устройствах.
- **Управляемые устройства**  >  **Office** обновления. В этом представлении показан общий Office обновлений на компьютеры, управляемые Майкрософт устройствах.

Кроме того, в нескольких местах Microsoft Endpoint Manager можно фильтровать отчеты из других групп продуктов, чтобы конкретно включать или исключать устройства, управляемые компьютеры, управляемые Майкрософт. Эти отчеты интегрировали эту возможность фильтрации:

- [Все устройства](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Соответствие устройства требованиям](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Некомплиентные устройства](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Настраиваемые компьютеры, управляемые Майкрософт ролей гарантируют доступ только к отчетам компьютеры, управляемые Майкрософт отчетов. Чтобы получить доступ к другим частям Microsoft Endpoint Manager, таким как все **устройства,** см. управление доступом на основе ролей с [Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) 


 ## <a name="inventory-data"></a>Данные инвентаризации

В дополнение к другим отчетам можно экспортировать сведения о устройствах, управляемых компьютеры, управляемые Майкрософт. В **представлении Устройств** области **устройств** Microsoft Endpoint Manager используйте вкладку **Экспорт** все, чтобы скачать [подробный отчет о запасах.](device-inventory-report.md)