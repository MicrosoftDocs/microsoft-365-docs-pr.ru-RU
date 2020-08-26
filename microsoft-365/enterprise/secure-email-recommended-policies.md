---
title: Рекомендуемые политики безопасной почты — Microsoft 365 для предприятий | Документы Майкрософт
description: Описание рекомендаций Майкрософт по применению политик электронной почты и конфигураций.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
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
ms.openlocfilehash: 9c289006fc1501865b0cf5529c308a0986895504
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898144"
---
# <a name="policy-recommendations-for-securing-email"></a>Рекомендуемые политики для защиты электронной почты

В этой статье описывается, как реализовать рекомендуемые политики удостоверений и доступа к устройствам для защиты электронной почты организации и почтовых клиентов, поддерживающих современные проверки подлинности и условный доступ. Это руководство создает [Общие политики идентификации и доступа к устройствам](identity-access-policies.md) , а также включает несколько дополнительных рекомендаций.

Эти рекомендации основаны на трех различных уровнях безопасности и защиты, которые можно применять в зависимости от степени детализации ваших потребностей: **базовый**, **чувствительный**и **строго регулируемый**. Дополнительные сведения об этих уровнях безопасности и клиентских операционных системах, на которые указывают эти рекомендации, можно узнать в статье [Рекомендуемые политики безопасности и конфигурации](microsoft-365-policies-configurations.md).

Для этих рекомендаций пользователям необходимо использовать современные почтовые клиенты, в том числе Outlook для iOS и Android на мобильных устройствах. Outlook для iOS и Android обеспечивает поддержку лучших возможностей Office 365. Эти приложения для мобильных устройств Outlook также основаны на возможностях обеспечения безопасности, которые поддерживают использование мобильных устройств и работают совместно с другими функциями безопасности Microsoft Cloud. Дополнительные сведения можно найти в статье [вопросы и ответы по Outlook для iOS и Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Обновление общих политик для включения электронной почты

На следующей схеме показаны общие политики идентификации и доступа к устройствам, а также указаны политики, которые необходимо обновить для защиты электронной почты. Обратите внимание на добавление нового правила для Exchange Online для блокирования клиентов ActiveSync. Это приводит к принудительному использованию Outlook Mobile.

![Сводка обновлений политик для защиты электронной почты](../media/identity-access-ruleset-mail.png)

[Просмотреть увеличенную версию этого изображения](https://raw.githubusercontent.com/MicrosoftDocs/microsoft-365-docs/public/microsoft-365/media/identity-access-ruleset-mail.png)

Если вы включили Exchange Online и Outlook в область политик при их настройке, вам потребуется создать новую политику, чтобы заблокировать только клиентов ActiveSync. Ознакомьтесь с политиками, приведенными в следующей таблице, и либо сделайте Рекомендуемые дополнения, либо подтвердите, что они уже включены. Каждое правило связывается со связанными инструкциями по настройке в общих правилах [идентификации и доступа к устройствам](identity-access-policies.md).

|Уровень защиты|Политики|Дополнительная информация|
|:---------------|:-------|:----------------|
|**Базовый уровень**|[Требовать, чтобы риск входа в систему был *средним* или *высоким*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включение Exchange Online в назначение облачных приложений|
|        |[Блокирование клиентов, не поддерживающих современную проверку подлинности](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Включение Exchange Online в назначение облачных приложений|
|        |[Применение политик защиты данных приложений](identity-access-policies.md#apply-app-data-protection-policies)|Убедитесь, что Outlook включен в список приложений. Обязательно обновите политику для каждой платформы (iOS, Android, Windows).|
|        |[Требовать утвержденные приложения и защиту приложений](identity-access-policies.md#require-approved-apps-and-app-protection)|Включение Exchange Online в список облачных приложений|
|        |[Требовать использования соответствующих политике компьютеров](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Включение Exchange Online в список облачных приложений|
|        |[Блокировка клиентов ActiveSync](#block-activesync-clients)|Добавление новой политики| 
|**Конфиденциально**|[Требовать, когда риск входа в систему *мал*, *средний* или *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Включение Exchange Online в назначение облачных приложений|
|         |[Требовать соответствующие компьютеры *и* мобильные устройства](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Включение Exchange Online в список облачных приложений|
|**Строго контролируемый**|[*Всегда* требовать MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включение Exchange Online в назначение облачных приложений|

## <a name="block-activesync-clients"></a>Блокировка клиентов ActiveSync

Эта политика запрещает клиентам ActiveSync обходить другие правила условного доступа. Настройка правил применяется только к клиентам ActiveSync. Выбрав **[параметр требовать политику защиты приложений](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, эта политика блокирует клиентов ActiveSync. Подробные сведения о создании этой политики можно найти в этой политике: " [требовать политику защиты приложений для облачного доступа к облачному приложению с условным доступом](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)".

1. Выполните команду "шаг 2: Настройка политики условного доступа Azure AD для Exchange Online с помощью ActiveSync (EAS)" в [сценарии 1: приложения Office 365 требуют утвержденных приложений с политиками защиты приложений](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), что не позволяет клиентам Exchange ActiveSync использовать обычную проверку подлинности для подключения к Exchange Online.

## <a name="set-up-message-encryption"></a>Настройка шифрования сообщений

Благодаря новым возможностям Microsoft 365 Message encryption (OME), которые используют функции защиты в Azure Information Protection, ваша организация может легко обмениваться защищенной электронной почтой с другими пользователями на любом устройстве. Пользователи могут отправлять и получать защищенные сообщения с другими организациями Microsoft 365, а также без клиентов, использующих Outlook.com, Gmail и другие службы электронной почты.

Дополнительные сведения см. в статье [Настройка новых возможностей шифрования сообщений Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Дальнейшие действия

[Узнайте о рекомендуемых политиках для защиты сайтов и файлов SharePoint](sharepoint-file-access-policies.md)
