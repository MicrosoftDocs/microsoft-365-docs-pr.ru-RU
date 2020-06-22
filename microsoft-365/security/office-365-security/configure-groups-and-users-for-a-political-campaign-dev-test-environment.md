---
title: Настройка групп и пользователей в среде разработки и тестирования для политической кампании
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: Сводка. Сведения о создании пробных подписок на Office 365 и Enterprise Mobility + Security (EMS) с пользователями и группами в случае среды разработки и тестирования для политической кампании.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d8c315364e9a00a49ad825ef2652ff4e8a7476b
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755276"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании

 **Сводка.** Сведения о создании пробных подписок на Office 365 и Enterprise Mobility + Security (EMS) с пользователями и группами в случае среды разработки и тестирования для политической кампании.

Инструкции из этой статьи помогут создать среду разработки и тестирования, которая включает упрощенные учетные записи пользователей и группы. Она необходима для решения, упомянутого в статье [Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Этап 1. Создание среды разработки и тестирования Office 365

На этом этапе вы получите пробные подписки на Office 365 E5 и Enterprise Mobility + Security (EMS) E5 для вымышленной организации, которая проводит политическую кампанию.

Сначала выполните инструкции для **этапа 2** из статьи [Простая базовая конфигурация](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Затем оформите пробную подписку EMS E5 и добавьте ее для той же организации, что и пробную подписку.

1. При необходимости войдите в Центр администрирования, используя учетные данные глобального администратора пробной подписки. Дополнительные сведения см. в статье [Вход](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Выберите плитку **Администрирование**.

3. На вкладке **Центр администрирования Microsoft 365** в браузере, в области навигации слева, щелкните **Выставление счетов > Приобретение служб**.

4. On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.

5. На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.

6. На странице **Получение заказа** нажмите кнопку **Продолжить**.

Затем включите лицензию на EMS E5 для своей учетной записи глобального администратора.

1. Открыв вкладку браузера **Центр администрирования Microsoft 365**, на панели навигации слева выберите **Пользователи > Активные пользователи**.

2. Выберите свою учетную запись глобального администратора и щелкните ссылку **Изменить** для параметра **Лицензии на продукты**.

3. На панели **Лицензии на продукты** переведите переключатель **Enterprise Mobility + Security E5** в положение **Вкл.**, нажмите **Сохранить**, а затем дважды **Закрыть**.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Этап 2. Создание и настройка групп Azure Active Directory (AD)

На этом этапе создаются и настраиваются группы Azure AD для кампании.

Сначала создайте набор групп для обычной политической кампании на портале Azure.

1. On a separate tab in your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.

2. На портале Azure последовательно выберите **Azure Active Directory > Пользователи и группы > Все группы**.

3. Выполните приведенные ниже шаги для каждой группы из этого списка:

   - "Старший и стратегический персонал";

   - "ИТ-персонал";

   - "Специалисты по аналитике";

   - "Основной штат сотрудников";

   - "Операционный персонал";

   - "Выездной персонал".

1. В колонке **Все группы** выберите пункт **+ Новая группа**.

2. Введите имя группы из списка в поле **Имя**.

3. Выберите **Динамический пользователь** для параметра **Членство**.

4. Выберите вариант **Да** для параметра **Включить функции Office**.

5. Выберите **Добавить динамический запрос**.

6. В поле **Место добавления пользователей** выберите **Отдел**.

7. В следующем поле выберите **Равно**.

8. В следующем поле введите имя группы из списка.

9. Выберите **Добавить запрос** > **Создать**.

10. Выберите **Пользователи и группы — Все группы**.

Затем настройте группы так, чтобы их членам автоматически назначались лицензии на Office 365 E5 и EMS E5.

1. На портале Azure последовательно выберите **Azure Active Directory > Лицензии > Все продукты**.

2. В списке выберите **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5**, затем нажмите **+ Назначить**.

3. В колонке **Назначение лицензии** щелкните **Пользователи и группы**.

4. В списке выберите следующие группы:

   - Специалисты по аналитике

   - Выездной персонал

   - ИТ-персонал

   - Операционный персонал

   - Основной штат сотрудников

   - Старший и стратегический персонал

5. Выберите **Выбрать** > **Назначить**.

6. Закройте вкладку портала Azure в браузере.

## <a name="phase-3-add-your-user-accounts"></a>Этап 3. Добавление учетных записей пользователей

На этом этапе добавляются демонстрационные учетные записи пользователей для политической кампании.

Прежде всего [подключитесь к модулю PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Затем введите название организации, адрес и общий пароль и выполните эти команды в командной строке PowerShell или интегрированной среде сценариев (ISE):

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.

Чтобы проверить динамическое членство в группах и групповое лицензирование:

1. На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Администрирование**.

2. На новой вкладке браузера**Центр администрирования Microsoft 365** щелкните **Пользователи**.

3. В списке пользователей выберите **Кандидат**.

4. В области свойств учетной записи **Кандидат** убедитесь, что:

   - она входит в состав группы **Старший и стратегический персонал** (в разделе **Членство в группах**);

   - ей назначены лицензии на **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5** (в разделе **Лицензии на продукты**).

5. Закройте область учетной записи пользователя **Кандидат**.

## <a name="record-values-for-future-reference"></a>Запишите значения для дальнейшего использования

Запишите эти значения для работы с пробными подписками Office 365 и EMS для этой среды разработки и тестирования:

- Название вашей организации: ![Подчеркнутый](../../media/Common-Images/TableLine.png)

  Например, для доменного имени contoso.onmicrosoft.com название организации — "contoso".

- Имя глобального администратора: ![Подчеркнутый](../../media/Common-Images/TableLine.png).onmicrosoft.com

  Запишите пароль для этой учетной записи и общий первоначальный пароль для других учетных записей пользователей в надежном месте.

## <a name="next-step"></a>Следующий этап

Создайте четыре типа для сайтов группы SharePoint Online в этой среде разработки и тестирования, следуя инструкциям из статьи [Создание сайтов группы в среде разработки и тестирования для политической кампании](create-team-sites-in-a-political-campaign-dev-test-environment.md).

## <a name="see-also"></a>См. также

[Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Создание сайтов группы в среде разработки и тестирования для политической кампании](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[Руководства по лаборатории тестирования для облачных решений](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Освоение облака и гибридные решения](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
