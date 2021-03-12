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
description: Сводка. Этапы миграции служб Федерации active Directory (AD FS) для миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727471"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland

Это изменение конфигурации может применяться в любое время до начала этапа 4.
После завершения второго этапа изменение конфигурации будет работать, и вы сможете войти в Глобальные конечные точки Office 365, такие как `https://portal.office.com` . Если вы реализуете изменение конфигурации до этапа 2, глобальные конечные  точки Office 365 еще не работают, но новое доверяющий доверие сторон по-прежнему является частью конфигурации служб Федерации Active Directory (AD FS).

Чтобы перенести ферму AD FS из Microsoft Cloud Deutschland:

1. Сохраняйте параметры AD FS, включая сведения о доверии FF с [помощью этих действий.](#backup) Назови **резервную Deutschland_Only** Microsoft Cloud, чтобы указать, что у нее есть только сведения о клиенте Microsoft Cloud Deutschland.
2. Проверьте восстановление с помощью резервного Deutschland_Only Microsoft Cloud, ферма AD FS должна продолжать работать только в Microsoft Cloud Deutschland.

После завершения и тестирования резервного копирования AD FS выполните следующие действия, чтобы добавить новое доверение сторон в конфигурацию ADFS:

1. Откройте консоль управления AD FS
2. В левом окантовке консоли управления ADFS раздвяйте **ADFS,** затем доверяйте **отношениям,** а затем доверяйте **доверием сторон.**
3. В правой области выберите **Add Relying Party Trust...**
4. Выберите **Далее** на странице **Приветствие** мастера доверяющих сторон добавить.
5. На странице **Выбор источника данных** выберите импорт данных о стороне, которая полагается, опубликованной в Интернете или в **локальной сети.** Значение **адреса метаданных Федерации (имя хозяина или URL-адрес)** должно быть задано `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Затем нажмите кнопку **Далее**.
6. На странице **Выбор источника данных** введите имя отображения, например Microsoft Office **365 Identity Platform WorldWide.** Затем нажмите кнопку **Далее**.
7. На странице Мастер **Настройка многофакторной** проверки подлинности сейчас? Выберите подходящий выбор в соответствии с требованиями проверки подлинности. Если вы придерживались по умолчанию, выберите, что в данный момент не нужно настраивать параметры многофакторной проверки подлинности для этого доверяемого **участника.** Вы можете изменить этот параметр позже, если хотите.
8. В **правилах разрешения** на выдачу выберите разрешить всем пользователям доступ к выбранной стороне, которая полагается, нажмите  **кнопку Далее**
9. Нажмите **кнопку Далее** на **странице Готово добавить доверие,** чтобы завершить мастер.
10. Нажмите **Кнопку Закрыть** на **финишной** странице.

Закрыв мастера, устанавливается доверяющий участник с глобальными службами Office 365. Однако правила преобразования выдачи пока не настроены.

Вы можете использовать [AD FS Help для](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) создания правильных правил преобразования выдачи. Созданные правила утверждения, созданные с помощью AD FS Help, можно добавлять вручную через консоль управления AD FS или с Помощью PowerShell. AD FS Help будет создавать необходимые скрипты PowerShell, которые необходимо выполнять.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Запустите **создание утверждений** в справке AD FS и скопируйте сценарий преобразования утверждений PowerShell с помощью параметра **Copy** в правом верхнем углу скрипта.
2. Откройте предпочтительный текстовый редактор и вклейте скрипт PowerShell в новое текстовое окно.
3. Добавьте следующие строки PowerShell в конец вклеит скрипт из шага 2
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. Безопасность и выполнение сценария PowerShell.
5. Убедитесь, что присутствуют два доверчивых участника; один для Microsoft Cloud Deutschland и один для глобальной службы Office 365.
6. Резервное копирование доверия с помощью [этих действий.](#backup) Сохраните его с именем **FFAndWorldwide.**
7. Выполните миграцию backend и убедитесь, что AD FS по-прежнему работает во время процесса миграции.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Аварийное восстановление AD FS (база данных WID)

Чтобы восстановить ферму AD FS в аварийной ситуации, необходимо использовать средство быстрого восстановления [AD FS.](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) Поэтому необходимо скачать средство и перед началом миграции создать и безопасно хранить резервное копирование. В этом примере (средах TAT) для обратного запуска фермы запускаются следующие команды:

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
4. Безопасно храните резервную копию в нужном месте.

### <a name="restore-an-ad-fs-farm"></a>Восстановление фермы AD FS

Если ферма полностью сбой и нет способа вернуться к старой ферме, делайте следующее. 

1. Перемещение ранее сгенерированной и хранимой резервной копии на новый основной сервер AD FS.
2. Запустите следующую `Restore-ADFS` команду PowerShell. При необходимости импортировать сертификат SSL AD FS заранее.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Указать новые записи DNS или балансировку нагрузки на новые серверы AD FS.

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
