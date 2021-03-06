---
title: Общие политики доступа к удостоверениям и устройствам — Microsoft 365 для корпоративных | Документы Майкрософт
description: Описывает рекомендуемые общие политики и конфигурации доступа к удостоверениям и устройствам.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: e7148e666b7d96d6de328089fccc4bb444b9f502
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594009"
---
# <a name="common-identity-and-device-access-policies"></a>Основные политики доступа для удостоверений и устройств

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- Azure

В этой статье описываются распространенные рекомендуемые политики для обеспечения доступа к облачным службам Microsoft 365, включая локальное приложение, опубликованное с помощью прокси-сервера Azure Active Directory (Azure AD).

В этом руководстве обсуждается, как развертывать рекомендуемые политики в новой среде. Настройка этих политик в отдельной лабораторной среде позволяет понять и оценить рекомендуемые политики перед установкой выкатки в предварительной и производственной средах. Новая среда может быть облачной или гибридной, чтобы отражать ваши потребности в оценке.

## <a name="policy-set"></a>Набор политик

На следующей схеме иллюстрирует рекомендуемый набор политик. В нем показано, какой уровень защиты применяется к каждой политике и применяются ли политики к ПК, телефонам и планшетам или к обеим категориям устройств. Также указывается, где настраиваются эти политики.

[![Общие политики для настройки удостоверений и доступа к устройствам](../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

Вот одно страницу сводки PDF со ссылками на отдельные политики:

[![Изображение большого пальца для удостоверения и защиты устройств для Microsoft 365 раздатки](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Просмотр в формате PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Скачивание в формате PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

В остальной части этой статьи описано, как настроить эти политики.

> [!NOTE]
> Перед регистрацией устройств в Intune рекомендуется использовать многофакторную проверку подлинности (MFA), чтобы убедиться, что устройство находится в распоряжении намечаемого пользователя. Необходимо зарегистрировать устройства в Intune, прежде чем применять политики соответствия требованиям.

Чтобы у вас было время для выполнения этих задач, рекомендуем реализовать базовые политики в порядке, заданной в этой таблице. Однако политики MFA для чувствительных и строго регулируемых уровней защиты могут быть реализованы в любое время.

|Уровень защиты|Политики|Дополнительные сведения|Лицензирование|
|---|---|---|---|
|**Базовый уровень**|[Требовать MFA, когда риск входов средний *или* *высокий*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 или Microsoft 365 E3 с надстройки безопасности E5|
||[Блокирование клиентов, не поддерживающих современную проверку подлинности](#block-clients-that-dont-support-multi-factor)|Клиенты, которые не используют современную проверку подлинности, могут обойти политики условного доступа, поэтому важно их заблокировать.|Microsoft 365 E3 или E5|
||[Необходимость смены пароля для пользователей с высоким риском](#high-risk-users-must-change-password)|Заставляет пользователей изменять пароль при входе в учетную запись, если для их учетной записи обнаружена высокая активность.|Microsoft 365 E5 или Microsoft 365 E3 с надстройки безопасности E5|
||[Применение политики защиты данных приложения (APP)](#apply-app-data-protection-policies)|Одна политика защиты приложений intune на платформе (Windows, iOS/iPadOS, Android).|Microsoft 365 E3 или E5|
||[Требуются утвержденные приложения и защита приложений](#require-approved-apps-and-app-protection)|Обеспечивает защиту мобильных приложений для телефонов и планшетов с помощью iOS, iPadOS или Android.|Microsoft 365 E3 или E5|
||[Определение политик соответствия требованиям устройств](#define-device-compliance-policies)|Одна политика для каждой платформы.|Microsoft 365 E3 или E5|
||[Требовать использования соответствующих политике компьютеров](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Обеспечивает управление компьютерами Intune с помощью Windows macOS.|Microsoft 365 E3 или E5|
|**Конфиденциально**|[Требовать MFA при низком, среднем или высоком риске *входов*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 или Microsoft 365 E3 с надстройки безопасности E5|
||[Требуются совместимые компьютеры *и мобильные* устройства](#require-compliant-pcs-and-mobile-devices)|Обеспечивает управление intune как для компьютеров (Windows или macOS), так и для телефонов или планшетов (iOS, iPadOS или Android).|Microsoft 365 E3 или E5|
|**Строго контролируемый**|[*Всегда* требуется MFA](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 или E5|
|

## <a name="assigning-policies-to-groups-and-users"></a>Назначение политик группам и пользователям

Перед настройкой политик определите группы Azure AD, которые вы используете для каждого уровня защиты. Обычно базовая защита применяется ко всем в организации. Пользователь, включенный как для базовой, так и для конфиденциальной защиты, будет иметь все применяемые базовые политики, а также конфиденциальные политики. Защита является накопительной и применяются самые ограничительные политики.

Рекомендуется создать группу Azure AD для исключения условного доступа. Добавьте эту группу ко всем политикам  условного доступа в исключении значения параметра **Пользователи** и группы в разделе **Назначения.** Это позволяет обеспечить доступ к пользователю при устранении неполадок. Это рекомендуется только в качестве временного решения. Отслеживайте изменения в этой группе и убедитесь, что группа исключений используется только по назначению.

Ниже приводится пример группового назначения и исключений, требующих MFA.

![Пример группового назначения и исключений для политик MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Вот результаты:

- Все пользователи должны использовать MFA, если риск входного знака средний или высокий.

- Члены группы executive staff должны использовать MFA, если риск входного входного знака низкий, средний или высокий.

  В этом случае члены группы executive staff соответствуют базовым и конфиденциальным политикам условного доступа. Элементы управления доступом для обеих политик объединены, что в данном случае эквивалентно конфиденциальной политике условного доступа.

- Члены группы Top Secret Project X всегда должны использовать MFA

  В этом случае члены группы Top Secret Project X соответствуют базовым и строго регулируемым политикам условного доступа. Элементы управления доступом для обеих политик объединены. Поскольку управление доступом для строго регулируемой политики условного доступа является более строгим, оно используется.

Будьте осторожны при применении более высоких уровней защиты к группам и пользователям. Например, члены группы Project X должны будут использовать MFA при каждом входе, даже если они не работают над высокорегулируемым контентом для Project X.

Все группы Azure AD, созданные в рамках этих рекомендаций, должны создаваться Microsoft 365 группами. Это важно для развертывания меток конфиденциальности при обеспечении безопасности документов в Microsoft Teams и SharePoint.

![Пример создания группы Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Требовать MFA на основе риска входных данных

Прежде чем требовать его использования, необходимо, чтобы пользователи зарегистрировались в MFA. Если у вас Microsoft 365 E5, Microsoft 365 E3 надстройка безопасности E5, Office 365 с EMS E5 или отдельные лицензии Azure AD Premium P2, вы можете использовать политику регистрации MFA в Azure AD Identity Protection, чтобы потребовать, чтобы пользователи зарегистрировались для MFA. Необходимой [работой](identity-access-prerequisites.md) является регистрация всех пользователей в MFA.

После регистрации пользователей вы можете потребовать регистрацию в MFA с помощью новой политики условного доступа.

1. Войдите на [портал Azure](https://portal.azure.com) со своими учетными данными.
2. В списке служб Azure выберите **Azure Active Directory.**
3. В **списке Управление** выберите **безопасность,** а затем выберите **условный доступ.**
4. Выберите **новую политику** и введите имя новой политики.

В следующих таблицах описываются параметры политики условного доступа, которые требуют MFA на основе риска входных данных.

В разделе **Назначения:**

|Параметр|Элемент Property|Значения|"Заметки"|
|---|---|---|---|
|Пользователи или группы|Включить|**Выберите пользователей и группы > пользователей и групп.** Выберите конкретные группы, содержащие целевые учетные записи пользователей.|Начните с группы, которая включает пилотные учетные записи пользователей.|
||Исключить|**Пользователи и группы.** Выберите группу исключений условного доступа; учетные записи служб (идентификаторы приложений).|Членство должно быть изменено на временной основе по мере необходимости.|
|Облачные приложения или действия|**Облачные приложения > включить**|**Выберите приложения.** Выберите приложения, к которые необходимо применить эту политику. Например, выберите Exchange Online.||
|Условия|||Настройка условий, специфических для среды и потребностей.|
||Риск при входе||Руководство см. в следующей таблице.|
|

### <a name="sign-in-risk-condition-settings"></a>Параметры условий риска при входе

Применение параметров уровня риска в зависимости от уровня защиты, на который вы нацелены.

|Уровень защиты|Необходимые значения уровня риска|Action|
|---|---|---|
|Базовый уровень|Высокий, средний|Проверьте оба.|
|Конфиденциальный|Высокая, средняя, низкая|Проверьте все три.|
|Строго контролируемый||Оставьте все параметры неконтранными, чтобы всегда применять MFA.|
|

В разделе **Элементы управления доступом:**

|Параметр|Элемент Property|Значения|Action|
|---|---|---|---|
|Предоставить|**Предоставление доступа**||Выбор|
|||**Требуется многофакторная проверка подлинности**|Чек|
||**Требовать все выбранные средства управления**||Выбор|
|

Выберите **Выберите Параметры** **Для сохранения параметров гранта.**

Наконец, выберите **политику "Включить",** а затем выберите **Создать**. 

Кроме того, рассмотрите возможность использования [средства What if](/azure/active-directory/active-directory-conditional-access-whatif) для тестирования политики.

## <a name="block-clients-that-dont-support-multi-factor"></a>Блокировка клиентов, не поддерживаюющих многофакторную поддержку

Используйте параметры в этих таблицах для политики условного доступа, чтобы заблокировать клиентов, которые не поддерживают многофакторную проверку подлинности.

В [этой статье](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) см. список клиентов в Microsoft 365, которые поддерживают многофакторную проверку подлинности.

В разделе **Назначения:**

|Параметр|Элемент Property|Значения|"Заметки"|
|---|---|---|---|
|Пользователи или группы|Включить|**Выберите пользователей и группы > пользователей и групп.** Выберите конкретные группы, содержащие целевые учетные записи пользователей.|Начните с группы, которая включает пилотные учетные записи пользователей.|
||Исключить|**Пользователи и группы.** Выберите группу исключений условного доступа; учетные записи служб (идентификаторы приложений).|Членство должно быть изменено на временной основе по мере необходимости.|
|Облачные приложения или действия|**Облачные приложения > включить**|**Выбор приложений.** Выберите приложения, соответствующие клиентам, которые не поддерживают современную проверку подлинности.||
|Условия|**Клиентские приложения**|Выберите **да** для **настройки** <p> Очистка контрольных знаков **для браузерных** и **мобильных приложений и клиентов настольных компьютеров**||
|

В разделе **Элементы управления доступом:**

|Параметр|Элемент Property|Значения|Action|
|---|---|---|---|
|Предоставить|**Заблокировать доступ**||Выбор|
||**Требовать все выбранные средства управления**||Выбор|
|

Выберите **Выберите Параметры** **Для сохранения параметров гранта.**

Наконец, выберите **политику "Включить",** а затем выберите **Создать**. 

Рассмотрите возможность использования [средства What if](/azure/active-directory/active-directory-conditional-access-whatif) для тестирования политики.

Для Exchange Online можно использовать политики проверки подлинности для отключения базовой проверки [подлинности,](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)что заставляет все запросы на доступ клиентов использовать современную проверку подлинности.

## <a name="high-risk-users-must-change-password"></a>Необходимость смены пароля для пользователей с высоким риском

Для обеспечения того, чтобы скомпрометированная учетная запись всех пользователей с высоким уровнем риска была вынуждена выполнить изменение пароля при входе, необходимо применить следующую политику.

Войдите на [портал Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) с помощью учетных данных администратора и последовательно выберите **Защита идентификации Azure AD > Политика риска пользователя**.

В разделе **Назначения:**

|Type|Элемент Property|Значения|Action|
|---|---|---|---|
|Users|Включить|**Все пользователи**.|Выбор|
|Риск пользователя|**Высокий**||Выбор|
|

Во втором разделе **Назначения:**

|Type|Элемент Property|Значения|Action|
|---|---|---|---|
|Доступ|**Разрешить доступ**||Выбор|
|||**Требовать смену пароля**|Чек|
|

Выберите **Сделано,** чтобы сохранить **параметры Access.**

Наконец, выберите **политику "Для** **обеспечения выполнения",** а затем выберите **Сохранить**.

Рассмотрите возможность использования [средства What if](/azure/active-directory/active-directory-conditional-access-whatif) для тестирования политики.

Используйте эту политику в сочетании с настройками защиты паролей [Azure AD,](/azure/active-directory/authentication/concept-password-ban-bad)которая обнаруживает и блокирует известные слабые пароли, их варианты и дополнительные слабые термины, которые специфичен для вашей организации. Защита паролей Azure AD гарантирует, что измененные пароли являются прочными.

## <a name="apply-app-data-protection-policies"></a>Применение политик защиты данных APP

ApPs определяют, какие приложения разрешены и какие действия они могут принимать с данными организации. Выбор, доступный в APP, позволяет организациям адаптировать защиту к конкретным потребностям. Для некоторых может быть не очевидно, какие параметры политики необходимы для реализации полного сценария. Чтобы помочь организациям узаконить конечную точку мобильных клиентов, Корпорация Майкрософт ввела таксономию для своей платформы защиты данных APP для управления мобильными приложениями для iOS и Android.

Структура защиты данных APP организована на три различных уровня конфигурации, каждый уровень строится на уровне предыдущего:

- **Enterprise базовой** защиты данных (уровень 1) обеспечивает защиту приложений пин-кодом и шифрованием и выполняет селективные операции по уничтожению. Для устройств с Android этот уровень проверяет проверку android-устройств. Это конфигурация начального уровня, которая обеспечивает аналогичное управление защитой данных в Exchange Online почтовых ящиков и знакомит ИТ и пользователей с APP.
- **Enterprise расширенной защиты** данных (уровень 2) вводит механизмы предотвращения утечки данных APP и минимальные требования к ОС. Это конфигурация, которая применима к большинству мобильных пользователей, которые имеют доступ к работе или школьным данным.
- Enterprise высокой защиты данных (уровень 3) внедряет расширенные механизмы защиты данных, улучшенную конфигурацию **ПИН-кода** и app Mobile Threat Defense. Эта конфигурация является желательной для пользователей, которые имеют доступ к данным с высоким уровнем риска.

Чтобы просмотреть конкретные рекомендации для каждого уровня конфигурации и минимальные приложения, которые необходимо защитить, просмотрите рамки защиты данных с помощью [политик защиты приложений.](/mem/intune/apps/app-protection-framework)

Используя принципы, описанные в конфигурациях доступа к удостоверениям и [устройствам,](microsoft-365-policies-configurations.md)уровни базовой и конфиденциальной защиты тесно соотнося с корпоративными настройками защиты данных уровня 2. Уровень высокорегулируемой защиты тесно совмещится с корпоративными высокими настройками защиты данных уровня 3.

|Уровень защиты|Политика защиты приложений|Дополнительные сведения|
|---|---|---|
|Базовый уровень|[Улучшенная защита данных уровня 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Параметры политики, примененные на уровне 2, включают все параметры политики, рекомендуемые для уровня 1, и только добавляют или обновляют ниже параметры политики, чтобы реализовать больше элементов управления и более сложную конфигурацию, чем уровень 1.|
|Конфиденциальный|[Улучшенная защита данных уровня 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Параметры политики, примененные на уровне 2, включают все параметры политики, рекомендуемые для уровня 1, и только добавляют или обновляют ниже параметры политики, чтобы реализовать больше элементов управления и более сложную конфигурацию, чем уровень 1.|
|Строго регламентированная|[Защита высоких данных предприятия уровня 3](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Параметры политики, примененные на уровне 3, включают все параметры политики, рекомендуемые для уровней 1 и 2, и только добавляют или обновляют параметры политики ниже, чтобы реализовать больше элементов управления и более сложную конфигурацию, чем уровень 2.|
|

Чтобы создать новую политику защиты приложений для каждой платформы (iOS и Android) в Microsoft Endpoint Manager с помощью параметров среды защиты данных, вы можете:

1. Создайте политики вручную, следуя шагам в Области создания и развертывания политик защиты приложений с [помощью Microsoft Intune](/mem/intune/apps/app-protection-policies).
2. Импорт образцов шаблонов конфигурации политики защиты [приложений Intune с](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) помощью сценариев [PowerShell Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Требуются утвержденные приложения и защита ПРИЛОЖЕНИЯ

Чтобы обеспечить соблюдение политик защиты ПРИЛОЖЕНИЙ, примененных в Intune, необходимо создать политику условного доступа, чтобы требовать утвержденных клиентских приложений и условий, задаваемых политиками защиты ПРИЛОЖЕНИЙ.

Для обеспечения соблюдения политик защиты ПРИЛОЖЕНИЙ требуется набор политик, описанных в политике защиты приложений Require для доступа к облачным приложениям [с условным доступом.](/azure/active-directory/conditional-access/app-protection-based-conditional-access) Эти политики включены в этот рекомендуемый набор политик настройки удостоверений и доступа.

Чтобы создать политику условного доступа, которая требует утвержденных приложений и защиты приложений, выполните статью "Шаг 1: Настройка политики условного доступа Azure AD для Microsoft 365" в сценарии [1: Microsoft 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)приложения требуют утвержденных приложений с политиками защиты приложений, что позволяет Outlook для iOS и Android, но блокирует OAuth, Exchange ActiveSync клиентов от подключения к Exchange Online.

   > [!NOTE]
   > Эта политика гарантирует, что мобильные пользователи могут Office конечные точки с помощью применимых приложений.

Если вы позволяете мобильному доступу к Exchange Online, реализуем клиенты [Block ActiveSync,](secure-email-recommended-policies.md#block-activesync-clients)что не позволяет Exchange ActiveSync клиентам, используя базовую проверку подлинности, подключиться к Exchange Online. Эта политика не изображена на рисунке в верхней части этой статьи. Она описана и изображена в [рекомендациях политики по обеспечению безопасности электронной почты.](secure-email-recommended-policies.md)

Чтобы создать политику условного доступа, требуемую Edge для iOS и Android, выполните статью "Шаг 2. Настройка политики условного доступа Azure AD для Microsoft 365" в сценарии [2.](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)Для браузерных приложений требуются утвержденные приложения с политиками защиты приложений, что позволяет Edge для iOS и Android, но блокирует подключение других веб-браузеров мобильных устройств к конечным точкам Microsoft 365.

 Эти политики используют средства управления грантами [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) и Require app protection [policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Наконец, блокировка устаревшей проверки подлинности для других клиентских приложений на устройствах с iOS и Android гарантирует, что эти клиенты не смогут обойти политики условного доступа. Если вы следуете указаниям в этой статье, вы уже настроили клиенты Block, которые не поддерживают [современную проверку подлинности.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Определение политик соответствия требованиям к устройствам

Политики соответствия требованиям, предъявляемым к устройствам, определяют требования, которые должны соответствовать требованиям, которые должны быть определены как совместимые. Вы создаете политики соответствия требованиям устройств Intune из центра Microsoft Endpoint Manager администрирования.

Необходимо создать политику для каждого компьютера, телефона или планшетной платформы:

- Администратор android-устройств
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 и более поздней
- Windows 10 и более поздней

Чтобы создать политики соответствия требованиям устройств, войдите в [центр администрирования Microsoft Endpoint Manager с](https://endpoint.microsoft.com) учетными данными администратора и перейдите к политикам соответствия требованиям  \>  \> **устройств.** Выберите **создать политику**.

Для развертывания политик соответствия требованиям к устройствам они должны быть назначены группам пользователей. После создания и сохранения политики назначается политика. В центре администрирования выберите политику и выберите **назначения.** После выбора групп, которые вы хотите получить политику, выберите **Сохранить,** чтобы сохранить назначение группы и развернуть политику.

Пошаговая инструкция по созданию политик соответствия требованиям [](/mem/intune/protect/create-compliance-policy) в Intune см. в Microsoft Intune в документации Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Рекомендуемые параметры для Windows 10 и более поздней

Следующие параметры рекомендуется использовать для компьютеров, работающих Windows 10, а затем, как это было настроено в шаге **2:** Параметры соответствия требованиям процесса создания политики.

Правила **оценки > Windows службы аттестации** для устройств см. в этой таблице.

|Свойства|Значение|Action|
|---|---|---|
|Требуется BitLocker|Обязательность|Выбор|
|Требуется включить безопасную загрузку на устройстве|Обязательность|Выбор|
|Требуют целостности кода|Обязательность|Выбор|
|

Для **свойств устройства укажите** соответствующие значения для версий операционной системы на основе ИТ-политик и политик безопасности.

Для **соответствия требованиям диспетчера конфигурации** выберите **Require**.

Для **системной безопасности** см. эту таблицу.

|Type|Элемент Property|Значение|Action|
|---|---|---|---|
|Password|Требуется пароль для разблокировки мобильных устройств|Обязательность|Выбор|
||Простые пароли|Блокировка|Выбор|
||Тип пароля|По умолчанию устройства|Выбор|
||Минимальная длина пароля|6 |Тип|
||Максимальное время бездействия до необходимости пароля|15|Тип <p> Этот параметр поддерживается для версий Android 4.0 и выше или KNOX 4.0 и выше. Для устройств с iOS он поддерживается для iOS 8.0 и выше.|
||Срок действия пароля (дней)|41|Тип|
||Количество предыдущих паролей для предотвращения повторного использования|5 |Тип|
||Требуется пароль при возвращении устройства из состояния ожидания (Mobile и Holographic)|Обязательность|Доступно для Windows 10 и более поздней|
|Шифрование|Шифрование хранения данных на устройстве|Обязательность|Выбор|
|Безопасность устройств|Брандмауэр|Обязательность|Выбор|
||Защита от вирусов|Обязательность|Выбор|
||Antispyware|Обязательность|Выбор <p> Этот параметр требует решения anti-Spyware, зарегистрированного в центре Безопасность Windows.|
|Defender|Microsoft Defender Antimalware|Обязательность|Выбор|
||Минимальная версия антивируса Microsoft Defender||Тип <p> Поддерживается только для Windows 10 рабочего стола. Корпорация Майкрософт рекомендует отставать от последней версии не более чем на пять версий.|
||Подпись microsoft Defender antimalware до настоящего времени|Обязательность|Выбор|
||Защита в режиме реального времени|Обязательность|Выбор <p> Поддерживается только для Windows 10 рабочего стола|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender для конечной точки

|Type|Элемент Property|Значение|Action|
|---|---|---|---|
|Правила Microsoft Defender для конечных точек в центре Microsoft Endpoint Manager администрирования|[Требовать, чтобы устройство было на уровне или под машинным показателем риска](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|Средний|Выбор|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Требуют совместимые компьютеры (но не совместимые телефоны и планшеты)

Перед добавлением политики, требующей совместимых компьютеров, обязательно зарегистрировать устройства для управления в Intune. Перед регистрацией устройств в Intune рекомендуется использовать многофакторную проверку подлинности для обеспечения того, что устройство находится в распоряжении намечаемого пользователя.

Чтобы требовать совместимые компьютеры:

1. Войдите на [портал Azure](https://portal.azure.com) со своими учетными данными.
2. В списке служб Azure выберите **Azure Active Directory.**
3. В **списке Управление** выберите **безопасность,** а затем выберите **условный доступ.**
4. Выберите **новую политику** и введите имя новой политики.

5. В **статье Назначение выберите** Пользователей и **группы** и включай в нее, к кому необходимо применить политику. Кроме того, исключите группу исключения условного доступа.

6. В **статье Назначения выберите** **облачные приложения или действия.**

7. Для **Включить** выберите выберите приложения **> Выберите,** а затем выберите нужные приложения из списка **облачных** приложений. Например, выберите Exchange Online. Выберите **Выберите,** когда это будет сделано.

8. Чтобы требовать совместимые компьютеры (но не совместимые телефоны и планшеты), в соответствии с заданиями **выберите** платформы **> устройств.** Выберите **Да** для **Настройки**. Выберите **выберите платформы устройств,** выберите **Windows** **и macOS,** а затем выберите **Готово**.

9. Под **управлением Access** выберите **Grant** .

10. Выберите **доступ к гранту,** а **затем проверьте, что устройство Require должно быть помечено как совместимый.** Для нескольких элементов управления **выберите Требуются все выбранные элементы управления.** По завершению выберите **Выберите**.

11. Выберите **для** **политики Включить,** а затем выберите **Создать**.

> [!NOTE]
> Перед включением этой политики убедитесь, что устройство соответствует требованиям. В противном случае вы можете быть заблокированы и не сможете изменить эту политику до тех пор, пока учетная запись пользователя не будет добавлена в группу исключений условного доступа.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Требуются совместимые компьютеры *и мобильные* устройства

Чтобы требовать соответствия требованиям для всех устройств:

1. Войдите на [портал Azure](https://portal.azure.com) со своими учетными данными.
2. В списке служб Azure выберите **Azure Active Directory.**
3. В **списке Управление** выберите **безопасность,** а затем выберите **условный доступ.**
4. Выберите **новую политику** и введите имя новой политики.

5. В **статье Назначение выберите** Пользователей и **группы** и включай в нее, к кому необходимо применить политику. Кроме того, исключите группу исключения условного доступа.

6. В **статье Назначения выберите** **облачные приложения или действия.**

7. Для **Включить** выберите выберите приложения **> Выберите,** а затем выберите нужные приложения из списка **облачных** приложений. Например, выберите Exchange Online. Выберите **Выберите,** когда это будет сделано.

8. Под **управлением Access** выберите **Grant** .

9. Выберите **доступ к гранту,** а **затем проверьте, что устройство Require должно быть помечено как совместимый.** Для нескольких элементов управления **выберите Требуются все выбранные элементы управления.** По завершению выберите **Выберите**.

10. Выберите **для** **политики Включить,** а затем выберите **Создать**.

> [!NOTE]
> Перед включением этой политики убедитесь, что устройство соответствует требованиям. В противном случае вы можете быть заблокированы и не сможете изменить эту политику до тех пор, пока учетная запись пользователя не будет добавлена в группу исключений условного доступа.

## <a name="next-step"></a>Следующий этап

[![Шаг 3. Политики для гостевых и внешних пользователей](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Узнайте о рекомендациях политики для гостевых и внешних пользователей](identity-access-policies-guest-access.md)