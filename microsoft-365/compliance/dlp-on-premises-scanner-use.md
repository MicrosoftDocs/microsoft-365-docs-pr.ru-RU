---
title: Использование локального сканера для защиты от потери данных Microsoft 365 (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Узнайте, как использовать локальный сканер для защиты от потери данных Microsoft 365 для сканирования неактивных данных и реализации защитных мер на локальных файловых ресурсах и в локальных папках и библиотеках документов SharePoint.
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289179"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Использование локального сканера для защиты от потери данных Microsoft 365 (предварительная версия)

Чтобы помочь вам ознакомиться с локальными возможностями защиты от потери данных, а также с использованием этих возможностей в политиках защиты от потери данных, мы составили для вас несколько сценариев.

> [!IMPORTANT]
> Эти сценарии локальной защиты от потери данных — не официальные процедуры для создания и настройки политик защиты от потери данных. Если вам нужно использовать политики защиты от потери данных в общих ситуациях, прочитайте эти статьи:
>
> - [Сведения о защите от потери данных](dlp-learn-about-dlp.md)
> - [Начало работы со стандартной политикой защиты от потери данных](get-started-with-the-default-dlp-policy.md)
> - [Создание политики защиты от потери данных на основе шаблона](create-a-dlp-policy-from-a-template.md)
> - [Создание, тестирование и настройка политики защиты от потери данных](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Сценарий: обнаружение файлов, соответствующих правилам защиты от потери данных

Данные с локального сканера защиты от потери данных используются в нескольких областях

#### <a name="activity-explorer"></a>Обозреватель действий

 Локальная защита от потери данных (Майкрософт) обнаруживает соответствия правил защиты от потери данных и сообщает о них в [Обозреватель действий](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).

#### <a name="microsoft-365-audit-log"></a>Журнал аудита Microsoft 365

В общедоступной предварительной версии соответствия правил защиты от потери данных доступны в пользовательском интерфейсе журнала аудита, см. [Поиск журнала аудита в Центре соответствия требованиям](search-the-audit-log-in-security-and-compliance.md) или с помощью командлета [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) в PowerShell.

#### <a name="aip"></a>AIP

Данные обнаружения доступны в локальном отчете в формате csv, который хранится по адресу:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Выполните поиск следующих столбцов:

- Режим DLP
- Статус DLP
- Комментарий DLP
- Имя правила DLP
- Действия DLP
- Владелец
- Текущие разрешения NTFS (SDDL)
- Примененные разрешения NTFS (SDDL)
- Тип разрешений NTFS

### <a name="scenario-enforce-dlp-rule"></a>Сценарий: принудительное применение правила защиты от потери данных

Если вы хотите принудительно применить правила защиты от потери данных к отсканированным файлам, то такое принудительное применение должно быть включено как для задания сканирования содержимого в AIP, так и на уровне политики в защите от потери данных.

#### <a name="configure-dlp-to-enforce-policy-actions"></a>Настройка защиты от потери данных для принудительного применения действий политики

1. Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies) и выберите политику защиты от потери данных, направленную на репозитории локального расположения, которые вы настроили в AIP.
2. Изменение политики
3. На странице **Проверка или включение политики** выберите пункт **Да, включить сейчас**.

## <a name="see-also"></a>См. также

- [Сведения о локальном сканере защиты от потери данных (предварительная версия)](dlp-on-premises-scanner-learn.md)
- [Начало работы с локальным сканером для защиты от потери данных (предварительная версия)](dlp-on-premises-scanner-get-started.md)
- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)
- [Создание, тестирование и настройка политики защиты от потери данных](create-test-tune-dlp-policy.md)
- [Начало работы с обозревателем действий](data-classification-activity-explorer.md)
