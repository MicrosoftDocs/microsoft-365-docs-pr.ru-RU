---
title: Политики доступа к удостоверениям и устройствам для обеспечения гостевого и внешнего доступа B2B — Microsoft 365 для предприятий | Документы Майкрософт
description: Описывает рекомендуемый условный доступ и связанные политики защиты доступа гостевых и внешних пользователей.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c2c01278831433c02e5c869dba83f223eea57d27
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683239"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Политики, разрешающие гостевой и внешний доступ к B2B

В этой статье описывается, как настроить рекомендуемые общие политики доступа к удостоверениям и устройствам, чтобы разрешить доступ гостевых и внешних пользователей с учетной записью Azure Active Directory (Azure AD) business-to-Business (B2B). Это руководство построено на [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)

Эти рекомендации предназначены для применения к **базовому уровню** защиты. Однако вы также можете скорректировать рекомендации в зависимости от  степени детализации ваших потребностей в конфиденциальной и **строго регулируемой** защите.

Если предоставить учетным записям B2B путь для проверки подлинности в клиенте Azure AD, эти учетные записи не будут иметь доступ ко всей среде. Пользователи B2B и их учетные записи имеют доступ только к ресурсам, к ним (например, к файлам) в службах, предоставленных политиками условного доступа.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Обновление общих политик для поддержки и защиты гостевого и внешнего доступа

Чтобы защитить гостевой и внешний доступ с помощью учетных записей Azure AD B2B, на следующей схеме показано, какие политики следует добавлять или обновлять из общих политик доступа к удостоверениям и устройствам.

[![Сводка обновлений политики для защиты гостевого доступа](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[См. более крупную версию этого изображения](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

В следующей таблице перечислены политики, которые необходимо создать и обновить. Общие политики ссылались на связанные инструкции по настройке в статье "Общие политики доступа к удостоверениям [и устройствам".](identity-access-policies.md)

|Уровень защиты|Политики|Дополнительная информация|
|---|---|---|
|**Базовый уровень**|[Требовать многофаксную многофайловую многофайловую раз для гостевых и внешних пользователей](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Создайте эту новую политику и настройте: <ul><li> For **Assignments > Users and groups > Include,** choose **Select users and groups,** and then select All guest and external **users**. </li><li> Для **заданий > условий > входе** оставьте все параметры невызванными, чтобы всегда применять многофакторную проверку подлинности (MFA).</li>|
||[Требовать многофаксную оценку, если риск при входе средний *или* *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Измените эту политику, чтобы исключить гостевых и внешних пользователей.|
||[Требовать использования соответствующих политике компьютеров](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Измените эту политику, чтобы исключить гостевых и внешних пользователей.|

Чтобы включить или исключить гостевых и внешних пользователей в политиках **условного** доступа, для > Пользователей и групп > Включить или исключить, проверьте всех гостевых и **внешних пользователей.**

![снимок экрана элементов управления для исключения гостевых и внешних пользователей](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Дополнительная информация

### <a name="guest-and-external-access-with-microsoft-teams"></a>Гостевой и внешний доступ с помощью Microsoft Teams

Microsoft Teams определяет следующее:

- **Гостевой доступ** использует учетную запись Azure AD B2B, которую можно добавить в качестве участника команды и получить все разрешения на доступ к коммуникациям и ресурсам команды.

- **Внешний доступ** для внешнего пользователя без учетной записи B2B. Внешний доступ может включать приглашения и участие в звонках, чатах и собраниях, но не включает членство в команде и доступ к ресурсам команды.

Дополнительные сведения см. в сравнении гостевого и [внешнего доступа для команд.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Дополнительные сведения о защите политик доступа к удостоверениям и устройствам для Teams см. в рекомендациях по защите [чатов,](teams-access-policies.md) групп и файлов Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>Требовать многофаксную многофайловую многофайловую раз для гостевых и внешних пользователей

Эта политика побуждает гостей зарегистрироваться для MFA в клиенте независимо от того, зарегистрированы ли они для MFA в домашнем клиенте. При доступе к ресурсам в клиенте гостевых и внешних пользователей необходимо использовать MFA для каждого запроса.

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Исключение гостевых и внешних пользователей из MFA с учетом рисков

Хотя организации могут применять политики на основе рисков для пользователей B2B с помощью защиты идентификации Azure AD, существуют ограничения в реализации защиты идентификации Azure AD для пользователей совместной работы B2B в каталоге ресурсов из-за их удостоверений, существующих в их домашнем каталоге. Из-за этих ограничений Корпорация Майкрософт рекомендует исключить гостевых пользователей из политик MFA на основе рисков и требовать от них всегда использовать многофаксную многофаксную многофаксную.

Дополнительные сведения см. в сведениях об ограничениях [защиты идентификации для пользователей совместной работы B2B.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guest-and-external-users-from-device-management"></a>Исключение гостевых и внешних пользователей из системы управления устройствами

Управлять устройством может только одна организация. Если вы не исключите гостевых и внешних пользователей из политик, которые требуют соответствия устройств требованиям, эти политики заблокируют этих пользователей.

## <a name="next-step"></a>Следующий шаг

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Настройте политики условного доступа для:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
