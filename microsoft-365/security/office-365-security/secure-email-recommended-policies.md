---
title: Рекомендуемые политики защиты электронной почты — Microsoft 365 для предприятий | Документы Майкрософт
description: Описание рекомендаций Майкрософт по применению политик электронной почты и конфигураций.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 653b16b7b3f6637440e3740830ffe9f9a51c6dd8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166511"
---
# <a name="policy-recommendations-for-securing-email"></a>Рекомендуемые политики для защиты электронной почты

**Область применения**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)


В этой статье описано, как реализовать рекомендуемые политики доступа к удостоверениям и устройствам для защиты почтовых клиентов организации, которые поддерживают современную проверку подлинности и условный доступ. Это руководство построено на общих политиках доступа к [удостоверениям](identity-access-policies.md) и устройствам, а также содержит несколько дополнительных рекомендаций.

Эти рекомендации основаны на трех различных уровнях безопасности и защиты, которые можно применять в зависимости от степени детализации ваших потребностей: базовый, конфиденциальный и строго **регулируемый.** Вы можете узнать больше об этих уровнях безопасности и рекомендуемых клиентских операционных системах, на которые ссылались эти рекомендации в рекомендуемых политиках безопасности и [конфигурациях.](microsoft-365-policies-configurations.md)

Эти рекомендации требуют, чтобы пользователи использовали современные почтовые клиенты, включая Outlook для iOS и Android на мобильных устройствах. Outlook для iOS и Android обеспечивает поддержку лучших функций Office 365. Эти мобильные приложения Outlook также имеют возможности безопасности, которые поддерживают мобильное использование и работают вместе с другими возможностями облачной безопасности Майкрософт. Дополнительные сведения см. в [outlook для iOS и Android.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Обновление общих политик для поддержки электронной почты

Чтобы защитить электронную почту, на следующей схеме показано, какие политики следует обновить из общих политик доступа к удостоверениям и устройствам.

[![Сводка обновлений политики для защиты доступа к Teams и зависимым службам](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[См. более крупную версию этого изображения](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Обратите внимание на добавление новой политики для Exchange Online для блокировки клиентов ActiveSync. Это привносят использование Outlook Mobile.

Если вы включили Exchange Online и Outlook в область политик при их создании, вам потребуется создать новую политику, чтобы заблокировать клиенты ActiveSync. Просмотрите политики, перечисленные в следующей таблице, и либо сделайте рекомендуемые дополнения, либо убедитесь, что они уже включены. Каждая политика ссылается на связанные инструкции по настройке в [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)

|Уровень защиты|Политики|Дополнительные сведения|
|---|---|---|
|**Базовый уровень**|[Требовать многофаксную оценку, если риск при *входе* средний или *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включить Exchange Online в назначение облачных приложений|
||[Блокирование клиентов, не поддерживающих современную проверку подлинности](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Включить Exchange Online в назначение облачных приложений|
||[Применение политик защиты данных APP](identity-access-policies.md#apply-app-data-protection-policies)|Убедитесь, что Outlook включен в список приложений. Обязательно обновите политику для каждой платформы (iOS, Android, Windows)|
||[Требовать утвержденные приложения и защиту приложений](identity-access-policies.md#require-approved-apps-and-app-protection)|Включить Exchange Online в список облачных приложений|
||[Требовать использования соответствующих политике компьютеров](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Включить Exchange Online в список облачных приложений|
||[Блокировка клиентов ActiveSync](#block-activesync-clients)|Добавление новой политики|
|**Конфиденциально**|[Требовать многофаксную оценку, если риск при входе *низкий,* *средний* или *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включить Exchange Online в назначение облачных приложений|
||[Требовать совместимые компьютеры *и мобильные* устройства](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Включить Exchange Online в список облачных приложений|
|**Строго контролируемый**|[Всегда требуется многофаксная многофаксная *многофаксная*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включить Exchange Online в назначение облачных приложений|
|

## <a name="block-activesync-clients"></a>Блокировка клиентов ActiveSync

Эта политика не позволяет клиентам ActiveSync обходить другие политики условного доступа. Конфигурация политики применяется только к клиентам ActiveSync. При выборе политики **["Требовать защиты приложений"](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** эта политика блокирует клиенты ActiveSync. Подробные сведения о создании этой политики можно найти в политике "Требовать защиту приложений для доступа к облачным приложениям [с помощью условного доступа".](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Выполните шаг 2. Настройте политику условного доступа Azure AD для Exchange Online с помощью ActiveSync (EAS) в сценарии [1. Приложения Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)требуют утвержденных приложений с политиками защиты приложений, что не позволяет Exchange ActiveSync клиентам, которые используют базовую проверку подлинности, подключаться к Exchange Online.

Вы также можете использовать политики проверки подлинности, [чтобы](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)отключить базовую проверку подлинности, которая заставляет все запросы клиентского доступа использовать современную проверку подлинности.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Ограничение доступа к Exchange Online из Outlook в Интернете

Вы можете запретить пользователям скачивать вложения из Outlook в Интернете на устройствах с подмагизами. Пользователи на этих устройствах могут просматривать и редактировать эти файлы с помощью Office Online без утечки и хранения файлов на устройстве. Вы также можете заблокировать для пользователей просмотр вложений на неугодном устройстве.

Необходимо выполнить следующие шаги.

1. [Подключение к удаленному сеансу PowerShell в Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Если у вас еще нет политики почтовых ящиков OWA, создайте ее с помощью cmdlet [New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)
3. Если вы хотите разрешить просмотр вложений, но не загружать их, используйте команду:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Чтобы заблокировать вложения, используйте команду:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. На портале Azure создайте новую политику условного доступа с помощью указанных здесь параметров.

   **Назначения** \> **Пользователи и группы:** выберите подходящих пользователей и группы, которые необходимо включить и исключить.

   **Назначения** \> **Облачные приложения или действия** \> **Облачные приложения** \> **Включить** \> **Выбор приложений:** выбор **Office 365 Exchange Online**

   **Элементы управления доступом** \> **Session**: Select **Use app enforced restrictions**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Требовать, чтобы устройства с iOS и Android использовали Outlook

Чтобы пользователи устройств с iOS и Android могли получать доступ только к содержимому работы или учебного заведения с помощью Outlook для iOS и Android, необходима политика условного доступа, ориентированная на этих потенциальных пользователей.

См. действия по настройке этой политики в области управления доступом к совместной работе с сообщениями [с помощью Outlook для iOS и Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Настройка шифрования сообщений

Благодаря новым возможностям шифрования сообщений Office 365 (OME), которые используют функции защиты в Azure Information Protection, ваша организация может легко делиться защищенной электронной почтой с любыми на любом устройстве. Пользователи могут отправлять и получать защищенные сообщения с другими организациями Microsoft 365, а также с пользователями, не Outlook.com, Gmail и другими службами электронной почты.

Дополнительные сведения см. в настройках новых возможностей шифрования [сообщений Office 365.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)

## <a name="next-steps"></a>Дальнейшие действия

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Настройте политики условного доступа для:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
