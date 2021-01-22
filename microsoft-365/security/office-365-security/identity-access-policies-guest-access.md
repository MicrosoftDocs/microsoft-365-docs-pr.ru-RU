---
title: Политики доступа к удостоверениям и устройствам, разрешающие гостевому и внешнему пользователю доступ к B2B — Microsoft 365 для предприятий | Документы Майкрософт
description: Описывает рекомендуемый условный доступ и связанные политики для защиты доступа гостей и внешних пользователей.
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932614"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Политики, разрешающие гостевой доступ и доступ внешних пользователей B2B

В этой статье обсуждается настройка рекомендуемых политик доступа к устройствам и удостоверениям, чтобы разрешить доступ гостям и внешним пользователям с учетной записью Azure Active Directory (Azure AD) business-to-Business (B2B). Это руководство построено на [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)

Эти рекомендации предназначены для применения к **базовому уровню** защиты. Однако вы также можете скорректировать рекомендации в зависимости от конкретных потребностей в конфиденциальной **и** **строго регулируемой** защите.

Если предоставить учетным записям B2B путь для проверки подлинности в клиенте Azure AD, эти учетные записи не будут иметь доступ ко всей среде. Пользователи B2B и их учетные записи имеют доступ к службам и ресурсам, например файлам, доступ к ним делиться политикой условного доступа.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Обновление общих политик, чтобы разрешить и защитить гостей и доступ внешних пользователей

На этой схеме показано, какие политики необходимо добавить или обновить среди общих политик доступа к удостоверениям и устройствам для гостевого и внешнего доступа пользователей B2B.

[![Сводка обновлений политики для защиты гостевого доступа](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[См. более крупную версию этого изображения](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

В следующей таблице перечислены политики, которые необходимо создать и обновить. Общие политики ссылались на связанные инструкции по настройке в статье "Общие политики доступа к удостоверениям [и устройствам".](identity-access-policies.md)

|Уровень защиты|Политики|Дополнительная информация|
|---|---|---|
|**Базовый уровень**|[Всегда требовать многофаксную многофаксную раз для гостей и внешних пользователей](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Создайте эту новую политику и настройте: <ul><li>For **Assignments > Users and groups > Include,** choose **Select users and groups,** and then select All guest and external **users**.</li><li>Для **заданий > условий > входе** оставьте все параметры невызванными, чтобы всегда применять многофакторную проверку подлинности (MFA).</li></ul>|
||[Требовать многофаксную оценку, если риск при *входе* средний или *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Измените эту политику, чтобы исключить гостей и внешних пользователей.|
||[Требовать использования соответствующих политике компьютеров](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Измените эту политику, чтобы исключить гостей и внешних пользователей.|

Чтобы включить или исключить гостей и внешних пользователей в политиках условного доступа, для > пользователей и групп **> Включить** или исключить **всех** гостевых и **внешних пользователей.**

![снимок экрана элементов управления для исключения гостей и внешних пользователей](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Дополнительная информация

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Гостевой доступ и доступ внешних пользователей с помощью Microsoft Teams

Microsoft Teams определяет следующих пользователей:

- **Гостевой доступ** использует учетную запись Azure AD B2B, которую можно добавить в качестве участника команды и получить доступ к коммуникациям и ресурсам команды.

- **Внешний доступ** для внешнего пользователя без учетной записи B2B. Доступ внешних пользователей включает приглашения, звонки, чаты и собрания, но не включает членство в команде и доступ к ресурсам команды.

Дополнительные сведения см. в [сравнении гостевых и внешних пользователей с доступом к командам.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Дополнительные сведения о защите политик доступа к удостоверениям и устройствам для Teams см. в рекомендациях политики для защиты чатов, групп [и файлов Teams.](teams-access-policies.md)

### <a name="require-mfa-always-for-guest-and-external-users"></a>Всегда требовать многофаксную многофаксную раз для гостевых и внешних пользователей

Эта политика побуждает гостей зарегистрироваться для MFA в клиенте независимо от того, зарегистрированы ли они для MFA в домашнем клиенте. При доступе к ресурсам в клиенте гости и внешние пользователи должны использовать MFA для каждого запроса.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Исключение гостей и внешних пользователей из MFA с учетом рисков

Хотя организации могут применять политики на основе рисков для пользователей B2B с помощью защиты идентификации Azure AD, существуют ограничения в реализации защиты идентификации Azure AD для пользователей совместной работы B2B в каталоге ресурсов из-за их удостоверений, существующих в их домашнем каталоге. Из-за этих ограничений Корпорация Майкрософт рекомендует исключить гостей из политик MFA на основе риска и требовать от этих пользователей всегда использовать MFA.

Дополнительные сведения см. в сведениях об ограничениях [защиты идентификации для пользователей совместной работы B2B.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guests-and-external-users-from-device-management"></a>Исключение гостей и внешних пользователей из системы управления устройствами

Управлять устройством может только одна организация. Если вы не исключите гостей и внешних пользователей из политик, которые требуют соответствия устройств требованиям, эти политики заблокируют этих пользователей.

## <a name="next-step"></a>Следующий этап

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Настройте политики условного доступа для:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
