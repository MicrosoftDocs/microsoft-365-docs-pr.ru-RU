---
title: Этапы миграции AD FS для миграции с Microsoft Cloud записей
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
description: 'Сводка: этапы миграции служб федерации Active Directory (AD FS) для миграции с Microsoft Cloud записей.'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554814"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Этапы миграции AD FS для миграции с Microsoft Cloud записей

Чтобы перенести ферму служб федерации Active Directory (AD FS) из Microsoft Cloud записей, выполните указанные ниже действия.

1. Выполните резервное копирование параметров AD FS, в том числе FF Trust со сведениями об [этих действиях](#backup). Назовите резервную копию **Microsoft cloud Deutschland_Only** , чтобы указать, что у нее есть только сведения о клиенте Microsoft Cloud записей.
2. Протестируйте восстановление с помощью Microsoft Cloud Deutschland_Only резервную копию, ферма AD FS должна продолжать работать как записей в Microsoft Cloud.
3. Создайте новое отношение доверия с проверяющей стороной из **AD FS > служб Office 365**.
4. В разделе **отношения доверия с проверяющей стороной** в консоли управления AD FS выберите **Добавить отношение доверия с проверяющей** стороной.
5. Нажмите кнопку **Далее** на странице **приветствия** мастера добавления отношения доверия с проверяющей стороной.
6. На странице **Выбор источника данных** выберите **Импорт данных о проверяющей стороне, опубликованных в Интернете или в локальной сети**. Для параметра **адрес метаданных федерации (имя узла или URL-адрес)** задано значение `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Нажмите кнопку **Далее**.
7. На странице **Выбор источника данных** введите отображаемое имя. Корпорация Майкрософт рекомендует использовать **платформу идентификации Microsoft Office 365 по всему миру**. Нажмите кнопку **Далее**.
8. Нажмите кнопку **Далее** в **разделе Настройка многофакторной проверки подлинности сейчас?**, **Выберите правила авторизации выдачи** и **все готово к добавлению страниц доверия** .
9. Нажмите кнопку **Закрыть** на странице **Готово** .

После закрытия мастера устанавливается отношение доверия с проверяющей стороной Естс служб Office 365. Однако правила преобразования выдачи не устанавливаются.

Вы можете использовать [справку по AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) для создания правильных правил преобразования выдачи. Созданные правила утверждений, созданные с помощью справки AD FS, можно либо добавить вручную через консоль управления AD FS, либо с помощью PowerShell. Справка по AD FS создаст необходимые сценарии PowerShell, которые необходимо запустить.  

1. Запустите **Создание утверждений** в СПРАВКЕ AD FS и скопируйте сценарий преобразования утверждений PowerShell с помощью параметра **Copy** в правом верхнем углу скрипта.
2. Вставьте созданную оболочку PowerShell в следующее:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Выполнение завершенного скрипта.
4.  Убедитесь, что имеются два отношения доверия проверяющей стороны; один для всего мира и один для БФ.
5.  Выполните резервное копирование отношений доверия, выполнив [указанные ниже действия](#backup). Сохраните файл с именем **ффандворлдвиде**.
6.  Выполните внутреннюю миграцию и убедитесь, что служба AD FS все еще работает во время процесса миграции.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Аварийное восстановление AD FS (база данных WID)

Чтобы восстановить ферму AD FS в [средстве аварийного восстановления служб федерации Active Directory](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) , необходимо использовать его. Таким образом, перед началом миграции необходимо скачать и сохранить средство резервного копирования. В этом примере (средах ТАТ) для резервного копирования фермы были выполнены следующие команды:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Резервное копирование фермы AD FS

1. Установите средство быстрого восстановления служб федерации Active Directory на основном сервере AD FS.
2. Импортируйте модуль в сеансе PowerShell с помощью этой команды.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Выполните команду резервного копирования.

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Безопасно храните резервную копию в нужном месте. 

### <a name="restore-an-ad-fs-farm"></a>Восстановление фермы AD FS

Если ферма закончилась неудачно и нет способа вернуться на старую ферму, выполните следующие действия. 

1. Переместите ранее созданный и сохраненный архив на новый основной сервер AD FS.
2. Выполните следующую `Restore-ADFS` команду PowerShell. При необходимости импортируйте SSL-сертификат AD FS заранее.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Укажите новые записи DNS или подсистему балансировки нагрузки для новых серверов AD FS.

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Миграция из Microsoft Cloud записей в службы Office 365 в новых регионах центра обработки данных на немецком языке](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Взаимодействие с пользователем во время миграции](ms-cloud-germany-transition-experience.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительные предварительные действия](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения о [службах](ms-cloud-germany-transition-add-general.md), [устройствах](ms-cloud-germany-transition-add-devices.md), [опыте](ms-cloud-germany-transition-add-experience.md)и службах [федерации Active Directory](ms-cloud-germany-transition-add-adfs.md).

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
