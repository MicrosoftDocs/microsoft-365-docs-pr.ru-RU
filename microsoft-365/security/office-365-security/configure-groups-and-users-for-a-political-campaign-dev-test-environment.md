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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: Сводка. Сведения о создании пробных подписок на Office 365 и Enterprise Mobility + Security (EMS) с пользователями и группами в случае среды разработки и тестирования для политической кампании.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e21cdfb0aabbdb10397d6d16c879756449a498e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204968"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](defender-for-office-365.md)

 **Сводка.** Сведения о создании пробных подписок на Office 365 и Enterprise Mobility + Security (EMS) с пользователями и группами в случае среды разработки и тестирования для политической кампании.

Инструкции из этой статьи помогут создать среду разработки и тестирования, которая включает упрощенные учетные записи пользователей и группы. Она необходима для решения, упомянутого в статье [Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Этап 1. Создание среды разработки и тестирования Office 365

На этом этапе вы получите пробные подписки на Office 365 E5 и Enterprise Mobility + Security (EMS) E5 для вымышленной организации, которая проводит политическую кампанию.

Сначала выполните инструкции для **этапа 2** из статьи [Простая базовая конфигурация](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).

Затем оформите пробную подписку EMS E5 и добавьте ее для той же организации, что и пробную подписку.

1. При необходимости войдите в Центр администрирования, используя учетные данные глобального администратора пробной подписки. Дополнительные сведения см. в статье [Вход](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Выберите плитку **Администрирование**.

3. На вкладке **Центр администрирования Microsoft 365** в браузере, в области навигации слева, щелкните **Выставление счетов > Приобретение служб**.

4. На странице **Приобретение служб** найдите элемент **Enterprise Mobility + Security E5**. Наведите на него указатель мыши и выберите **Начать бесплатный пробный период**.

5. На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.

6. На странице **Получение заказа** нажмите кнопку **Продолжить**.

Затем включите лицензию на EMS E5 для своей учетной записи глобального администратора.

1. Открыв вкладку браузера **Центр администрирования Microsoft 365**, на панели навигации слева выберите **Пользователи > Активные пользователи**.

2. Выберите свою учетную запись глобального администратора и щелкните ссылку **Изменить** для параметра **Лицензии на продукты**.

3. На панели **Лицензии на продукты** переведите переключатель **Enterprise Mobility + Security E5** в положение **Вкл.**, нажмите **Сохранить**, а затем дважды **Закрыть**.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Этап 2. Создание и настройка групп Azure Active Directory (AD)

На этом этапе создаются и настраиваются группы Azure AD для кампании.

Сначала создайте набор групп для обычной политической кампании на портале Azure.

1. Откройте отдельную вкладку в браузере, а затем перейдите на портал Azure по адресу <https://portal.azure.com>. Если необходимо, выполните вход с использованием учетных данных учетной записи глобального администратора пробной подписки Office 365 E5.

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

Прежде всего [подключитесь к модулю PowerShell Azure Active Directory для Graph](../../enterprise/connect-to-microsoft-365-powershell.md).

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
> Общий пароль используется для автоматизации и упрощения настройки среды разработки и тестирования. Не рекомендуется для рабочих подписок. При входе в каждую из этих новых учетных записей пользователя вам будут показаны запросы на изменение пароля.

Чтобы проверить динамическое членство в группах и групповое лицензирование:

1. На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Администрирование**.

2. На новой вкладке браузера **Центр администрирования Microsoft 365** щелкните **Пользователи**.

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

[Руководства по лаборатории тестирования для облачных решений](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Освоение облака и гибридные решения](/office365/enterprise/cloud-adoption-and-hybrid-solutions)