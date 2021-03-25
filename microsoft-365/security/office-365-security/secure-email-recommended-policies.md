---
title: Безопасные политики электронной почты — Microsoft 365 для корпоративных | Документы Майкрософт
description: Описание рекомендаций Майкрософт по применению политик электронной почты и конфигураций.
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
ms.openlocfilehash: 5a705444c81d884c10b99e5f0d2bfbb9e4f057e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206548"
---
# <a name="policy-recommendations-for-securing-email"></a>Рекомендуемые политики для защиты электронной почты

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)


В этой статье описано, как реализовать рекомендуемые политики доступа к удостоверениям и устройствам для защиты корпоративных клиентов электронной почты и электронной почты, поддерживаюющих современную проверку подлинности и условный доступ. Это руководство строится на [общих](identity-access-policies.md) политиках доступа к удостоверениям и устройствам, а также содержит несколько дополнительных рекомендаций.

Эти рекомендации основаны на трех различных уровнях безопасности и защиты, которые могут применяться в зависимости от детализации ваших потребностей: базовый, чувствительный и строго **регулируемый**. Дополнительные данные об этих уровнях безопасности и рекомендуемых клиентских операционных системах, на которые ссылались эти рекомендации, можно узнать в рекомендуемых политиках безопасности и [введении конфигураций.](microsoft-365-policies-configurations.md)

Эти рекомендации требуют, чтобы пользователи использовали современные клиенты электронной почты, в том числе Outlook для iOS и Android на мобильных устройствах. Outlook для iOS и Android обеспечивает поддержку лучших функций Office 365. Эти мобильные приложения Outlook также имеют возможности безопасности, которые поддерживают мобильное использование и работают вместе с другими возможностями облачной безопасности Майкрософт. Дополнительные сведения см. [в обзоре Outlook для iOS и Android.](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Обновление общих политик, чтобы включить электронную почту

Чтобы защитить электронную почту, на следующей схеме показано, какие политики необходимо обновить из общих политик доступа к удостоверениям и устройствам.

[![Сводка обновлений политики для защиты доступа к Teams и зависимым службам](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Обратите внимание на добавление новой политики exchange Online для блокировки клиентов ActiveSync. Это заставляет использовать мобильный Outlook.

Если вы включили Exchange Online и Outlook в область политик при их настройках, необходимо создать новую политику для блокировки клиентов ActiveSync. Просмотрите политики, перечисленные в следующей таблице, и включив рекомендуемые дополнения или подтвердив, что они уже включены. Каждая политика ссылается на связанные инструкции по конфигурации в общих политиках удостоверений и [доступа к устройствам.](identity-access-policies.md)

|Уровень защиты|Политики|Дополнительные сведения|
|---|---|---|
|**Базовый уровень**|[Требовать MFA, когда риск входов средний *или* *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включив Exchange Online в назначение облачных приложений|
||[Блокирование клиентов, не поддерживающих современную проверку подлинности](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Включив Exchange Online в назначение облачных приложений|
||[Применение политик защиты данных APP](identity-access-policies.md#apply-app-data-protection-policies)|Убедитесь, что Outlook включен в список приложений. Не забудьте обновить политику для каждой платформы (iOS, Android, Windows)|
||[Требуются утвержденные приложения и защита ПРИЛОЖЕНИЯ](identity-access-policies.md#require-approved-apps-and-app-protection)|Включив Exchange Online в список облачных приложений|
||[Требовать использования соответствующих политике компьютеров](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Включив Exchange Online в список облачных приложений|
||[Блокировка клиентов ActiveSync](#block-activesync-clients)|Добавление этой новой политики|
|**Конфиденциально**|[Требовать MFA при *низком,* *среднем* или высоком риске *входов*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включив Exchange Online в назначение облачных приложений|
||[Требуются совместимые компьютеры *и мобильные* устройства](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Включив Exchange Online в список облачных приложений|
|**Строго контролируемый**|[*Всегда* требуется MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включив Exchange Online в назначение облачных приложений|
|

## <a name="block-activesync-clients"></a>Блокировка клиентов ActiveSync

Эта политика не позволяет клиентам ActiveSync обойти другие политики условного доступа. Конфигурация политики применяется только к клиентам ActiveSync. Выбрав политику **[защиты приложений Require,](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** эта политика блокирует клиентов ActiveSync. Сведения о создании этой политики можно найти в политике [защиты приложений require for cloud app access with Conditional Access.](/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Следуйте "Шаг 2. Настройка политики условного доступа Azure AD для Exchange Online с помощью ActiveSync (EAS)" в сценарии [1. Приложения Office 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)требуют утвержденных приложений с политиками защиты приложений, что не позволяет Exchange ActiveSync клиентам использовать базовую проверку подлинности от подключения к Exchange Online.

Вы также можете использовать политики проверки подлинности для отключения [базовой](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)проверки подлинности, что заставляет все запросы на доступ клиентов использовать современную проверку подлинности.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Ограничение доступа к Exchange Online из Outlook в Интернете

Вы можете ограничить возможность для пользователей скачивать вложения из Outlook в Интернете на устройствах с umnanaged. Пользователи на этих устройствах могут просматривать и редактировать эти файлы с помощью Office Online без утечки и хранения файлов на устройстве. Кроме того, можно заблокировать доступ пользователей к вложениям на неугодном устройстве.

Эти этапы описаны ниже.

1. [Подключение к сеансу Удаленной powerShell Exchange Online.](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Если у вас еще нет политики почтовых ящиков OWA, создайте ее с помощью [cmdlet New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)
3. Если вы хотите разрешить просмотр вложений, но не скачивать, используйте эту команду:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Если вы хотите заблокировать вложения, используйте эту команду:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. На портале Azure создайте новую политику условного доступа с этими настройками:

   **Назначения** \> **Пользователи и группы.** Выберите подходящих пользователей и групп, чтобы включить и исключить.

   **Назначения** \> **Облачные приложения или действия** \> **Облачные приложения** \> **Включай** \> **Выбор приложений:** **Выберите Office 365 Exchange Online**

   **Элементы управления доступом** \> **Сеанс:** **Выберите принудимые ограничения использования приложений**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Необходимо, чтобы устройства iOS и Android использовали Outlook

Чтобы пользователи устройств с iOS и Android могли получать доступ только к работе или школьному контенту с помощью Outlook для iOS и Android, необходима политика условного доступа, ориентированная на этих потенциальных пользователей.

Действия по настройке этой политики см. в обзоре Управление доступом к совместной работе с сообщениями с [помощью Outlook для iOS и Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Настройка шифрования сообщений

Благодаря новым возможностям шифрования сообщений Office 365, которые используют функции защиты в Azure Information Protection, ваша организация может легко обмениваться защищенными сообщениями с любым человеком на любом устройстве. Пользователи могут отправлять и получать защищенные сообщения с другими организациями Microsoft 365, а также с Outlook.com, Gmail и другими службами электронной почты.

Дополнительные сведения см. [в дополнительных сведениях о новых возможностях шифрования сообщений Office 365.](../../compliance/set-up-new-message-encryption-capabilities.md)

## <a name="next-steps"></a>Дальнейшие действия

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Настройка политик условного доступа для:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)