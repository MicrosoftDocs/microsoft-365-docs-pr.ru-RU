---
title: Среда разработки и тестирования изолированного сайта группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: Сводка. Настройка сайта группы SharePoint Online, изолированного от остальной части Организации в среде разработки и тестирования Microsoft 365.
ms.openlocfilehash: e21dccb9ef535bb997d6e62b70e5576bf531041c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199665"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Среда разработки и тестирования изолированного сайта группы SharePoint Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Сводка:** Настройка сайта группы SharePoint Online, изолированного от остальной части Организации в среде разработки и тестирования Microsoft 365.

Сайты групп SharePoint Online в Microsoft 365 — это расположения для совместной работы с помощью общей библиотеки документов, записной книжки OneNote и других служб. Во многих случаях требуется широкий доступ и совместная работа отделов или организаций. Однако в некоторых случаях необходимо управлять доступом и разрешениями для совместной работы небольшой группы пользователей.

Доступ к сайтам группы SharePoint Online и к каким пользователям можно управлять с помощью групп SharePoint и уровней разрешений. По умолчанию на сайтах SharePoint Online предусмотрено три уровня доступа:

- **Участники** могут просматривать, создавать и изменять ресурсы на сайте.

- **Владельцы** могут полностью контролировать сайт, в том числе изменять разрешения.

- **Посетители** могут просматривать ресурсы на сайте.

В этой статье приведены инструкции по настройке изолированного сайта группы SharePoint Online для секретного исследовательского проекта ProjectX. Требования доступа:

- Только участники проекта могут получить доступ к сайту и его содержимому (документам, записной книжке OneNote, страницам), уровни разрешений SharePoint на просмотр и редактирование определяются членством в группе.

- Только создатель сайта и члены группы администраторов сайта могут выполнять администрирование сайта, в том числе изменять разрешения на уровне сайта.

Настройка изолированного сайта группы SharePoint Online в среде разработки и тестирования Microsoft 365 состоит из трех этапов:

1. Создайте среду разработки и тестирования Microsoft 365.

2. Создание пользователей и групп для ProjectX.

3. Создание сайта группы SharePoint Online для ProjectX и его изоляция.

> [!TIP]
> Щелкните [здесь](https://aka.ms/catlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования в One Microsoft Cloud.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Этап 1: создание простой или имитируемой среды для разработки и тестирования Microsoft 365 для предприятий

Если вы хотите просто создать изолированный сайт группы SharePoint Online с минимальными требованиями, выполните инструкции, приведенные в разделе этапы 2 и 3 [упрощенной базовой конфигурации](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Если вы хотите создать изолированный сайт группы SharePoint Online в смоделированной конфигурации предприятия, следуйте инструкциям в статье [Синхронизация хэша паролей для тестовой среды Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

> [!NOTE]
> Для создания изолированного сайта SharePoint Online не требуется имитация среды Enterprise dev/test, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS). Она указана здесь, чтобы вы могли протестировать изолированный сайт SharePoint Online и поэкспериментировать с ним в среде, которая представляет типичную среду для организаций.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Этап 2: создание учетных записей пользователей и групп доступа

Воспользуйтесь инструкциями из статьи [Подключение к Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) , чтобы подключиться к пробной подписке с помощью учетной записи глобального администратора:

- Компьютер (для упрощенной среды разработки и тестирования Microsoft 365).

- Виртуальная машина CLIENT1 (для среды разработки и тестирования Microsoft 365 для предприятий).

Чтобы создать новые группы доступа для сайта группы SharePoint Online ProjectX, выполните следующие команды в командной консоли Windows Azure Active Directory для Windows PowerShell:

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

Введите название организации (например, contosotoycompany) и двузначный код страны, а затем выполните следующие команды в командной строке модуля Windows Azure Active Directory для Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Запишите в надежном месте пароль, созданный командой **New-MsolUser** для учетной записи ведущего дизайнера.

Выполните следующие команды в командной строке модуля Windows Azure Active Directory для Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Запишите в надежном месте пароль, созданный командой **New-MsolUser** для учетной записи ведущего научного сотрудника.

Выполните следующие команды в командной строке модуля Windows Azure Active Directory для Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Запишите в надежном месте пароль, созданный командой **New-MsolUser** для учетной записи вице-президента по развитию.

Затем, чтобы добавить новые учетные записи в новые группы доступа, выполните следующие команды PowerShell в командной строке модуля Windows Azure Active Directory для Windows PowerShell:

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Результатом

- Группа доступа ProjectX – Members содержит сведения об дизайнере и учетных записях ведущего сотрудника.

- Группа доступа ProjectX — администраторы содержит учетную запись глобального администратора для пробной подписки.

- Группа доступа ProjectX – просматривающий содержит учетную запись пользователя ВИЦЕs Development

На рисунке 1 показаны группы доступа и их членство.

**Рисунок 1**

![Группы Microsoft 365 и их членство для изолированного сайта группы SharePoint Online](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Этап 3. Создание сайта группы SharePoint Online для ProjectX и его изоляция

Чтобы создать сайт группы SharePoint Online для ProjectX, выполните перечисленные ниже действия.

1. С помощью браузера на локальном компьютере (облегченная настройка) или на компьютере CLIENT1 (смоделированная конфигурация предприятия) Войдите в центр администрирования Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ), используя свою учетную запись глобального администратора.

2. В списке плиток выберите **SharePoint**.

3. На новой вкладке SharePoint в браузере нажмите **+ Создать сайт**.

4. В поле **Имя сайта группы** введите **ProjectX**. В окне **Параметры конфиденциальности**выберите пункт **частные пользователи могут получать доступ к этому сайту**.

5. В поле **Описание сайта группы** введите **Сайт SharePoint для ProjectX** и нажмите кнопку **Далее**.

6. На панели **Кого вы хотите добавить**? нажмите **Завершить**.

7. В новой вкладке **Главная, ProjectX** в браузере, на панели инструментов, щелкните значок параметров и выберите **Разрешения для сайта**.

8. В области **Разрешения для сайта** нажмите **Параметры дополнительных разрешений**.

9. В новой вкладке **Разрешения: Project X** в браузере нажмите **Параметры запросов на доступ**.

10. В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить запросы на доступ** (все три флажка должны быть сняты) и нажмите кнопку **ОК**.

11. Выберите **ProjectX — участники** в списке.

12. На странице **Пользователи и группы** нажмите кнопку **Создание**.

13. В диалоговом окне **Общий доступ** введите **ProjectX-Members**, выберите группу и нажмите **Поделиться**.

14. Нажмите кнопку "Назад" в браузере.

15. Выберите **ProjectX — владельцы** в списке.

16. На странице **Пользователи и группы** нажмите кнопку **Создание**.

17. В диалоговом окне **Общий доступ** введите **ProjectX-Admins**, выберите группу и нажмите **Поделиться**.

18. Нажмите кнопку "Назад" в браузере.

19. Выберите **ProjectX — посетители** в списке.

20. На странице **Пользователи и группы** нажмите кнопку **Создание**.

21. В диалоговом окне **Общий доступ** введите **ProjectX-Viewers**, выберите группу и нажмите **Поделиться**.

22. Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Главная, ProjectX** в браузере и закройте область **Разрешения для сайта**.

Ниже приведены результаты настройки разрешений.

- Группа ProjectX Members содержит только группу доступа ProjectX-Members (которая содержит только учетные записи ведущего дизайнера и ведущего пользователя) и группу ProjectX (которая содержит только учетную запись глобального администратора).

- Группа SharePoint Owners ProjectX содержит только группу доступа ProjectX-Admins (которая содержит только учетную запись глобального администратора).

- Группа SharePoint "Посетители ProjectX" содержит только группу доступа ProjectX-просматривающих (которая содержит только учетную запись "вице-президент разработки").

- Участники не могут изменять разрешения на уровне сайта (это могут делать только члены группы ProjectX-Admins).

- Другие учетные записи пользователей не могут получить доступ к сайту и его ресурсам и запросить доступ к нему.

На рисунке 2 показаны группы SharePoint и их участники.

**Рис. 2**

![Группы SharePoint Online и их членство для изолированного сайта группы SharePoint Online](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Теперь рассмотрим доступ, используя учетную запись пользователя конструктора ведущего:

1. Закройте вкладку **Главная, ProjectX** в браузере и перейдите на вкладку **Домашняя страница Microsoft Office**.

2. Щелкните имя глобального администратора и нажмите **Выйти**.

3. Войдите в центр администрирования Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ), используя имя и пароль учетной записи ведущего дизайнера.

4. В списке плиток выберите **SharePoint**.

5. На новой вкладке **SharePoint** введите **ProjectX** в поле поиска, активируйте поиск и выберите сайт группы **ProjectX**. Сайт группы ProjectX откроется на новой вкладке в браузере.

6. Щелкните значок параметров. Обратите внимание, что параметр **Разрешения для сайта** отсутствует, так как только члены группы ProjectX-Admins могут изменять разрешения для сайта.

7. Откройте приложение "Блокнот" или другой текстовый редактор.

8. Скопируйте URL-адрес сайта группы ProjectX и вставьте его в новой строке в приложении "Блокнот" или другом текстовом редакторе.

9. На новой вкладке **Главная, ProjectX** в браузере нажмите **Документы**.

10. Скопируйте URL-адрес папки документов ProjectX и вставьте его в новой строке в Блокноте или другом текстовом редакторе.

11. В новой вкладке **ProjectX — Документы** в браузере нажмите **Создать > Документ Word**.

12. Введите какой-либо текст на странице, дождитесь, пока состояние будет **сохранено**, нажмите кнопку "назад" в браузере, а затем обновите страницу. В папке **Документы** появится новый файл **Документ.docx**.

13. Нажмите кнопку с многоточием для **Document.docx** документа, а затем щелкните **получить ссылку**.

14. Скопируйте URL-адрес в диалоговом окне **общий доступ к Document.docxу** и вставьте его в новую строку в блокноте или в текстовом редакторе, а затем закройте диалоговое окно **общий доступ к Document.docx** .

15. Закройте вкладки **ProjectX — Документы** и **SharePoint** в браузере и перейдите на вкладку **Домашняя страница Microsoft Office**.

16. Щелкните имя **ведущего дизайнера** и нажмите **Выйти**.

Теперь рассмотрим доступ, используя учетную запись "вице — президент по разработке":

1. Войдите в центр администрирования Microsoft 365 (), [https://admin.microsoft.com](https://admin.microsoft.com) используя имя и пароль учетной записи вице-президента по разработке.

2. В списке плиток выберите **SharePoint**.

3. На новой вкладке **SharePoint** введите **ProjectX** в поле поиска, активируйте поиск и выберите сайт группы **ProjectX**. Сайт группы ProjectX откроется на новой вкладке в браузере.

4. Нажмите **Документы** и выберите файл **Документ.docx**.

5. Во вкладке **Документ.docx** в браузере попробуйте изменить текст. Вы увидите сообщение о том, что **этот документ доступен только для чтения**, так как у учетной записи вице-президента по развитию есть только разрешения на просмотр сайта.

6. Закройте вкладки **Документ.docx**, **ProjectX — Документы** и **SharePoint** в браузере.

7. Перейдите на вкладку **Домашняя страница Microsoft Office**, щелкните имя **вице-президента по развитию** и нажмите **Выйти**.

Теперь рассмотрим доступ с учетной записью пользователя, не имеющей разрешений.

1. Войдите в центр администрирования Microsoft 365 (), [https://admin.microsoft.com](https://admin.microsoft.com) используя имя учетной записи пользователя 3 и пароль.

2. В списке плиток выберите **SharePoint**.

3. 	В новой вкладке **SharePoint** введите **ProjectX** в поле поиска и активируйте поиск. Вы увидите сообщение **Нет результатов, соответствующих вашим условиям поиска**.

4. Скопируйте URL-адрес сайта ProjectX из открытого Блокнота или другого текстового редактора в адресную строку браузера и нажмите клавишу **Ввод**. Вы увидите страницу **Доступ запрещен**.

5. Скопируйте URL-адрес папки документов ProjectX из Блокнота или другого текстового редактора в адресную строку браузера и нажмите клавишу **Ввод**. Вы увидите страницу **Доступ запрещен**.

6. Скопируйте URL-адрес файла Документ.docx из Блокнота или другого текстового редактора в адресную строку браузера и нажмите клавишу **Ввод**. Вы увидите страницу **Доступ запрещен**.

7. Закройте вкладку **SharePoint** в браузере, перейдите на вкладку **Домашняя страница Microsoft Office**, щелкните имя **пользователя 3** и нажмите **Выйти**.

Теперь изолированный сайт SharePoint Online готов к выполнению дополнительного эксперимента.

## <a name="next-step"></a>Следующий шаг

Когда вы будете готовы выполнить развертывание изолированного сайта группы SharePoint Online в рабочей среде, просмотрите подробные инструкции из статьи [Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>См. также

[Изолированные сайты групп SharePoint Online](isolated-sharepoint-online-team-sites.md)

[Руководства по лабораториям тестирования (TLG) для принятия облачных решений](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Базовая конфигурация "имитация предприятия"](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[Простая базовая конфигурация](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[Освоение облака и гибридные решения](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
