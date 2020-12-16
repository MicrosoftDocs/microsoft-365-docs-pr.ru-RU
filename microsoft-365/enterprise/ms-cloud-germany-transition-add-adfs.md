---
title: Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland
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
description: Сводка. Этапы миграции служб федерации Active Directory (AD FS) для миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688669"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland

Чтобы перенести ферму служб федерации Active Directory (AD FS) из Microsoft Cloud Deutschland:

1. С помощью этих действий можно создать параметров [](#backup)AD FS, включая сведения о доверии FF. Назовем резервную **копию microsoft Cloud Deutschland_Only** указать, что у нее есть только сведения о клиенте Microsoft Cloud Deutschland.
2. Проверьте восстановление с помощью резервной копии Microsoft Cloud Deutschland_Only, ферма AD FS должна продолжать работать только как Microsoft Cloud Deutschland.
3. Создайте новое отношения доверия с отношениями доверия с > Службы **AD FS в Office 365.**
4. В **окнах доверия с отношениями** доверия с этой стороной в консоли управления AD FS выберите "Добавить отношения доверия с этой **стороной".**
5. Выберите **"Далее"** на странице приветствия мастера добавления отношения доверия с подстройки. 
6. На странице **"Выбор источника данных"** выберите "Импорт данных о стороне, опубликованной в Интернете или **в локальной сети".** Для **адреса метаданных федерации (имя или URL-адрес)** федерации установлено значение `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Нажмите кнопку **Далее**.
7. На странице **"Выбор источника данных"** введите отображаемого имени. Корпорация Майкрософт рекомендует **Microsoft Office 365 Identity Platform WorldWide.** Нажмите кнопку **Далее**.
8. Нажмите **кнопку** "Далее" в области "Настройка многофакторной проверки подлинности"? **Выберите**"Правила авторизации выдачи" и "Готово **к добавлению** страниц доверия". 
9. Нажмите **кнопку "Закрыть"** на **странице "Готово".**

Закрыв мастер, устанавливается отношения доверия с отношениями доверия с службами Office 365 eSTS. Однако правила преобразования выдачи не устанавливаются.

Справку [AD FS можно использовать](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) для создания правильных правил преобразования выдачи. Созданные правила утверждений, созданные с помощью справки AD FS, можно добавить вручную с помощью консоли управления AD FS или с помощью PowerShell. Справка AD FS создает необходимые сценарии PowerShell, которые необходимо запустить.  

1. Запустите **справку "Создание** утверждений" в AD FS и скопируйте сценарий преобразования утверждений PowerShell с помощью параметра **"Копировать"** в правом верхнем углу сценария.
2. В paste the generated PowerShell into the following:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Выполните завершенный сценарий.
4.  Убедитесь, что имеются два отношения доверия с проверяемой стороной; один для всемирного и второй для BF.
5.  Резервное копирование доверия с помощью [этих действий.](#backup) Сохраните его с именем **FFAndWorldwide.**
6.  Завершите миграцию на тыл и убедитесь, что службы AD FS по-прежнему работают в процессе миграции.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Аварийное восстановление AD FS (база данных WID)

Для восстановления фермы AD FS в аварийном средстве быстрого восстановления [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) необходимо использовать средство быстрого восстановления. Поэтому необходимо скачать средство и перед началом миграции создать резервную копию и безопасно сохранить ее. В этом примере (средах СДВИБ) для работы с фермой были выполнить следующие команды:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Back up an AD FS Farm

1. Установите средство быстрого восстановления AD FS на основном сервере AD FS.
2. Импортировать модуль в сеансе PowerShell с помощью этой команды.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Запустите команду резервного копирования:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Безопасно храните резервную копию в нужном месте назначения. 

### <a name="restore-an-ad-fs-farm"></a>Восстановление фермы AD FS

Если в ферме полностью сбой и возврат к старой ферме не удастся, сделайте следующее. 

1. Переместим ранее созданную и сохраненную резервную копию на новый основной сервер AD FS.
2. Запустите следующую `Restore-ADFS` команду PowerShell. При необходимости импортировать SSL-сертификат AD FS заранее.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Указать новые записи DNS или балансировку нагрузки на новые серверы AD FS.

## <a name="more-information"></a>Дополнительная информация

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
