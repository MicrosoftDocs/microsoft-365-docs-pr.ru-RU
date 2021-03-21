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
ms.openlocfilehash: 146f476a43e46925d87763a800467bf52adc73e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918910"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland

Это изменение конфигурации необходимо применять в любое время до начала этапа 2.
После завершения второго этапа изменение конфигурации будет работать, и вы сможете войти в систему с помощью глобальных конечных точек Office 365, таких как `https://portal.office.com` . Если вы реализуете изменение конфигурации до этапа 2, глобальные конечные  точки Office 365 еще не работают, но новое доверяющий доверие сторон по-прежнему является частью конфигурации служб Федерации Active Directory (AD FS).

Клиенты, которые используют федерационную проверку подлинности с помощью служб Федерации Active Directory (AD FS), не должны вносить изменения в URL-адреса эмитента, используемые для всех проверки подлинности с локальной службой доменных служб Active Directory (AD DS) во время миграции. Изменение URL-адресов эмитента приведет к сбоям проверки подлинности для пользователей домена. URL-адреса эмитента можно изменить непосредственно в AD FS  или при преобразовании домена из управляемого в _федераторский_ и наоборот. Рекомендуется не добавлять, удалять и не конвертировать федераированный домен в перенесенном клиенте Azure AD. URL-адреса эмитента могут быть изменены после полного завершения миграции.

Чтобы подготовить ферму AD FS к миграции из Microsoft Cloud Deutschland, выполните следующие действия:

1. С помощью этих действий необходимо создать параметров AD FS, в том числе существующего доверия сторон microsoft Cloud Deutschland Relying [Party.](#backup) Назови **резервную копию MicrosoftCloudDeutschlandOnly,** чтобы указать, что у нее есть только сведения о клиенте Microsoft Cloud Deutschland.

   > [!NOTE]
   > Резервное копирование будет содержать не только существующий доверчивый партийный траст Office 365 для Microsoft Cloud Deutschland, но и все другие доверчивые партийные траста, присутствующие в соответствующей ферме AD FS.

2. Проверьте восстановление с помощью резервного копирования MicrosoftCloudDeutschlandOnly, ферма AD FS должна продолжать работать только в Microsoft Cloud Deutschland.

После завершения и тестирования резервного копирования AD FS выполните следующие действия, чтобы добавить новое доверение сторон в конфигурацию ADFS:

1. Откройте консоль управления AD FS.

2. В левой области консоли управления ADFS перейдите в меню **Доверчивые** стороны.

3. В правой области выберите **Add Relying Party Trust...**

4. Выберите **Начало** на странице **Добро** пожаловать мастера доверия для доверяющих сторон с добавлением.

5. На странице **Выбор источника данных** выберите импорт данных о стороне, которая полагается, опубликованной в Интернете или в **локальной сети.** Значение **адреса метаданных Федерации (имя хозяина или URL-адрес)** должно быть задано `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Нажмите кнопку **Далее**.

6. На странице **Укажите имя отображения** введите имя отображения, например **Microsoft Office 365 Identity Platform WorldWide.** Нажмите кнопку **Далее**.

7. Если вы используете ADFS в Windows Server 2012, на странице мастер настройте многофакторную проверку подлинности **сейчас?** Выберите подходящий выбор в соответствии с требованиями проверки подлинности. Если вы придерживались по умолчанию, выберите, что в данный момент не нужно настраивать параметры многофакторной проверки подлинности для этого доверяемого **участника.** Вы можете изменить этот параметр позже, если хотите.

8. Для AD FS 2012: В правилах разрешения  на выдачу выберите разрешить всем пользователям доступ к выбранной стороне и нажмите **кнопку Далее**. 

8. Для AD FS 2016 и AD FS 2019: на странице **Выбор** политики управления доступом выберите соответствующую политику управления доступом и нажмите **кнопку Далее**. Если ни один из них не выбран, доверение доверяющих сторон **не будет** работать.

9. Нажмите **кнопку Далее** на **странице Готово добавить доверие,** чтобы завершить мастер.

10. Нажмите **Кнопку Закрыть** на **финишной** странице.

Закрыв мастера, устанавливается доверяющий участник с глобальной службой Office 365. Однако правила преобразования выдачи пока не настроены.

Вы можете использовать [AD FS Help для](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) создания правильных правил преобразования выдачи. Созданные правила утверждения, созданные с помощью AD FS Help, можно добавлять вручную через консоль управления AD FS или с Помощью PowerShell. AD FS Help будет создавать необходимые скрипты PowerShell, которые необходимо выполнять.  

> [!NOTE]
> [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) будет создавать стандартные правила преобразования выдачи, которые отгружаются вместе с продуктом. Однако, если правила преобразования настраиваемой выдачи в Microsoft Cloud Deutschland Relying Party Trust (например, пользовательские URL-адреса эмитента, нестандартные неизменяемые ID или любые другие настройки), правила, созданные службой AD FS, должны быть изменены таким образом, чтобы они вписывались в настраиваемую логику, созданную в настоящее время для доверения сторон Microsoft Cloud Deutschland. Если эти настройки не интегрированы в правила, созданные с помощью [AD FS Help,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)проверка подлинности  в Microsoft Office **365 Identity Platform WorldWide,** скорее всего, не будет работать для федеративной идентичности.

1. Запустите **создание утверждений** в [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) и скопируйте скрипт PowerShell с помощью параметра **Copy** в правом верхнем углу скрипта.

2. Следуйте шагам, описанным в справке [AD FS о](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) том, как запустить сценарий PowerShell в ферме AD FS для создания глобального доверяемой группы доверия.

3. Убедитесь, что присутствуют два полагаться partyTtrusts; один для Microsoft Cloud Deutschland и один для глобальной службы Office 365. Для проверки можно использовать следующую команду. Он должен возвращать две строки и соответствующие имена и идентификаторы.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Резервное копирование полной конфигурации миграции, включая оба доверчивых участника, с помощью [этих действий.](#backup) Сохраните его с именем **MicrosoftCloudDeutschlandAndWorldwide.**

5. В то время как клиент находится в миграции, регулярно убедитесь, что проверка подлинности AD FS работает с облаком Microsoft Cloud Deutschland и Microsoft Global в различных поддерживаемых шагах миграции.


## <a name="ad-fs-disaster-recovery-wid-database"></a>Аварийное восстановление AD FS (база данных WID)


Чтобы восстановить ферму AD FS в аварийной ситуации, необходимо использовать средство быстрого восстановления [AD FS.](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) Поэтому необходимо скачать средство и перед началом миграции создать и безопасно хранить резервное копирование. В этом примере были запущены следующие команды для обратного запуска фермы в базе данных WID:

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


## <a name="more-information"></a>Дополнительная информация

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

- [Сведения о программе миграции Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Сведения о программе миграции Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here)