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
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921354"
---
# <a name="work-with-reports"></a>Работа с отчетами

Компьютеры, управляемые Майкрософт, предоставляют несколько отчетов и панелей мониторинга, которые ИТ-администраторы организации могут использовать для понимания различных аспектов работы устройств.Отчеты можно найти в двух расположениях: [в Microsoft Endpoint Manager](https://endpoint.microsoft.com) и в Центре администрирования Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Отчеты в Microsoft Endpoint Manager

Консоль Microsoft Endpoint Manager объединяет отчеты из нескольких продуктов в единое расположение, помогая отслеживать и исследовать проблемы с конфигурацией и устройствами вашей организации Azure AD ("клиент"). Рабочий стол, управляемый  Майкрософт, имеет раздел "Отчеты" в главном меню, где можно найти отчеты, относякие к управлению компьютерами, управляемыми Майкрософт, на зарегистрированных устройствах.

К этим отчетам относятся:
- **Управляемые устройства**  >  **Обновления функций:** в этом представлении показано общее состояние обновлений функций на устройствах, управляемых Майкрософт.
- **Управляемые устройства**  >  **Обновления Office:** в этом представлении показано общее состояние обновлений Office на устройствах, управляемых Майкрософт.

Кроме того, в нескольких расположениях в Microsoft Endpoint Manager можно фильтровать отчеты от других групп продуктов, в частности включать или исключать устройства, управляемые компьютерами, управляемыми Майкрософт. Эти отчеты интегрировали эту возможность фильтрации:

- [Все устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Соответствие устройства требованиям](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Несовершенные устройства](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Настраиваемые роли компьютеров, управляемых Майкрософт, гарантируют доступ только к отчетам microsoft Managed Desktop. Чтобы получить доступ к другим частям Microsoft Endpoint Manager, таким как "Все устройства", см. функцию управления доступом на основе [ролей с помощью Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Отчеты в Центре администрирования Microsoft 365

Вы можете найти отчеты microsoft Managed Desktop Insights, открыв Центр администрирования  [Microsoft 365,](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)а затем выбрав "Отчеты" и выбрав "Компьютеры, управляемые **Майкрософт".** Вы также можете перенаправить эти отчеты по прямой ссылке на вкладку **"Управляемые** компьютеры Майкрософт" на домашней странице [Microsoft Endpoint Manager.](https://endpoint.microsoft.com) 

К этим отчетам относятся: 

- [Анализ использования —](usage-insights.md) это представление предоставляет метрики использования для ваших настольных компьютеров, управляемых Майкрософт.
- [Анализ надежности](reliability-insights.md) — это представление содержит сводку по состоянию здоровья управляемых устройств.
- [Анализ заряда батареи.](battery-insights.md) В этом представлении показаны сведения о потреблении энергии приложений и прогнозируемых время работы батареи для устройств в вашей среде.
- [Анализ обновлений для системы безопасности Windows.](security-update-insights.md) В этом представлении показаны сведения о состоянии обновлений для системы безопасности для настольных устройств, управляемых Майкрософт.

 ## <a name="inventory-data"></a>Данные инвентаризации

В дополнение к другим отчетам можно экспортировать сведения об устройствах, управляемых компьютерами, управляемыми Майкрософт. В **представлении "Устройства"** области "Устройства" Microsoft  Endpoint Manager используйте вкладку "Экспортировать все", чтобы скачать подробный отчет [об инвентаризации.](device-inventory-report.md) 
