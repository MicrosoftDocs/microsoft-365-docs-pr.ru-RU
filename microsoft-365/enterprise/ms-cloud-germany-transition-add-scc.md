---
title: Сведения об опыте работы с электронными данными во время миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: Сводка. Этапы миграции электронных данных для миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592143"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Сведения о том, как получить сведения об обнаружении электронных данных во время миграции из Microsoft Cloud Deutschland
В следующих разделах приводится дополнительная информация об опыте получения сведений об обнаружении электронных данных при переходе из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в службы Office 365 в новом немецком регионе центра обработки данных.

## <a name="ediscovery-administration-until-phase-4"></a>администрирование электронных открытий до 4-го этапа
До 4-го этапа Центр безопасности и соответствия требованиям будет полностью доступен. Все содержимое по-прежнему остается в Microsoft Cloud Germany и управляется Центром безопасности и соответствия требованиям Microsoft Cloud Germany https://protection.office.de/) (.

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>опыт по обнаружению электронных обнаружений между этапом 4 и до конца 9-й фазы
С начала 4-го этапа и до завершения 9-го этапа поиски электронных обнаружений сбой или возвращение 0 результатов для sharePoint Online, OneDrive для бизнеса и Exchange Online, которые были перенесены.

> [!NOTE]
> Во время миграции клиенты могут продолжать создавать случаи, удерживания, поиски и экспорты в Центре & [безопасности,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)включая [поиск контента.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Однако поиски в местах SharePoint Online, OneDrive для бизнеса и Exchange Online, которые были перенесены, возвращают результаты 0 или создают ошибку.

В случае, если поиск возвращает нулевые результаты или ошибку во время миграции, примите следующие действия для SharePoint Online: 
- Скачайте сайты непосредственно с сайта SharePoint Online или OneDrive для бизнеса, следуя инструкциям по загрузке файлов и папок [из OneDrive или SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Для этого метода потребуются разрешения администратора SharePoint Online или разрешения только для чтения на сайте.
- Если ограничения превышены, как поясняется в файле загрузки и папках из OneDrive или [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)клиенты могут использовать клиент синхронизации OneDrive для бизнеса, следуя указаниям в файлах [Sync SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)и Teams с компьютером.

- Дополнительные сведения см. [в Exchange Server.](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery)


## <a name="ediscovery-administration-after-phase-9"></a>администрирование электронных разыскных открытий после 9-го этапа

**Применяется к:** Все клиенты, использующие eDiscovery

На 9-м этапе будут завершены заключительные шаги по переходу в новый немецкий центр обработки данных. На этом этапе все оставшиеся компоненты службы будут перенесены. После 9-го этапа использование Центра безопасности и соответствия требованиям в Microsoft Cloud Germany (protection.office.de) больше не поддерживается. Вместо этого используйте новый [Центр безопасности](https://security.microsoft.com/) или [Центр соответствия](https://compliance.microsoft.com/) требованиям. Все данные были перенесены на новые порталы администрирования. 

| Step(s) | Описание | Влияние |
|:-------|:-------|:-------|
|  Все расположения SharePoint Online, OneDrive для бизнеса и Exchange Online были перенесены вместе с Центром безопасности и соответствия требованиям (SCC). | Все действия по обнаружению электронных обнаружений должны запускаться от клиента по всему миру. Поиск теперь будет на 100% успешным. Любые сбои или ошибки должны следовать обычным каналам поддержки. | Нет |
||||

### <a name="ediscovery-retention-policy"></a>Политика хранения электронных данных
**Применяется к:**  Все клиенты, применявшие политику хранения в рамках этапов предварительной миграции

| Step(s) | Описание | Влияние |
|:-------|:-------|:-------|
| Удаление политик хранения по всей организации, созданных во время этапов предварительной миграции | Клиенты могут удалить политики хранения на всей организации, созданные во время работы перед миграцией клиентов. | Нет |
||||
