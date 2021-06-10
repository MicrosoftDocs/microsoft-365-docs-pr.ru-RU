---
title: Рекомендуемые политики безопасных документов — Microsoft 365 для корпоративных | Документы Майкрософт
description: Описание рекомендаций Майкрософт по защите доступа к файлам SharePoint.
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204978"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Рекомендации политики для защиты SharePoint сайтов и файлов

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- SharePoint Online 


В этой статье описано, как реализовать рекомендуемые политики доступа к удостоверениям и устройствам для защиты SharePoint и OneDrive для бизнеса. Это руководство строится на [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)

Эти рекомендации основаны на трех различных уровнях безопасности и защиты для SharePoint файлов, которые могут применяться в зависимости от детализации ваших потребностей: базовый, чувствительный и строго регулируемый .  Дополнительные сведения об этих уровнях безопасности и рекомендуемых клиентских операционных системах, на которые ссылались эти рекомендации в [обзоре.](microsoft-365-policies-configurations.md)

В дополнение к реализации этого руководства не забудьте настроить SharePoint сайты с нужным объемом защиты, включая установку соответствующих разрешений для конфиденциального и строго регулируемого контента.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Обновление общих политик для SharePoint и OneDrive для бизнеса

Чтобы защитить файлы в SharePoint и OneDrive, на следующей схеме показано, какие политики должны обновляться из общих политик доступа к удостоверениям и устройствам.

[![Сводка обновлений политики для защиты доступа к Teams зависимым службам](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Если вы включили SharePoint при создании общих политик, необходимо создать только новые политики. Для политик условного доступа SharePoint включает OneDrive.

Новые политики реализуют защиту устройств для конфиденциального и строго регулируемого контента, применяя особые требования к доступу SharePoint сайтов, которые вы указываете.

В следующей таблице перечислены политики, которые необходимо просмотреть и обновить или создать новые для SharePoint. Общие политики ссылались на связанные инструкции по конфигурации в статье Общие политики доступа к удостоверениям [и устройствам.](identity-access-policies.md)

|Уровень защиты|Политики|Дополнительные сведения|
|---|---|---|
|**Базовый уровень**|[Требовать MFA, когда риск входов средний *или* *высокий*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включаем SharePoint в назначение облачных приложений.|
||[Блокирование клиентов, не поддерживающих современную проверку подлинности](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Включаем SharePoint в назначение облачных приложений.|
||[Применение политик защиты данных APP](identity-access-policies.md#apply-app-data-protection-policies)|Убедитесь, что все рекомендуемые приложения включены в список приложений. Не забудьте обновить политику для каждой платформы (iOS, Android, Windows).|
||[Требовать использования соответствующих политике компьютеров](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Включаем SharePoint в список облачных приложений.|
||[Используйте принудимые ограничения приложения в SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Добавьте эту новую политику. В этом Azure Active Directory (Azure AD) использовать параметры, указанные в SharePoint. Эта политика применяется ко всем пользователям, но влияет только на доступ к сайтам, включенным SharePoint политикам доступа.|
|**Конфиденциально**|[Требовать MFA при *низком,* *среднем* или высоком риске *входов*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включаем SharePoint в назначения облачных приложений.|
||[Требуются совместимые компьютеры *и мобильные* устройства](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Включи SharePoint в список облачных приложений.|
||[SharePoint](#sharepoint-access-control-policies)управления доступом. Разрешить доступ только для браузера к определенным сайтам SharePoint с неугодных устройств.|Это предотвращает редактирование и скачивание файлов. Используйте PowerShell для указания сайтов.|
|**Строго контролируемый**|[*Всегда* требуется MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включаем SharePoint в назначение облачных приложений.|
||[SharePoint](#use-app-enforced-restrictions-in-sharepoint)управления доступом: блокировать доступ к определенным SharePoint сайтам с неугодных устройств.|Используйте PowerShell для указания сайтов.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>В SharePoint

Если вы реализуете элементы управления доступом в SharePoint, необходимо создать эту политику условного доступа в Azure AD, чтобы сообщить Azure AD, чтобы обеспечить выполнение политик, настроенных в SharePoint. Эта политика применяется ко всем пользователям, но влияет только на доступ к сайтам, которые вы указываете с помощью PowerShell при создании элементов управления доступом в SharePoint.

Чтобы настроить эту политику, см. в рублях "Блокировка или ограничение доступа к определенным SharePoint или учетным OneDrive учетным записям" в control [access from unmanaged devices.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>SharePoint политики управления доступом

Корпорация Майкрософт рекомендует защищать контент на SharePoint с конфиденциальным и строго регулируемым контентом с помощью элементов управления доступом к устройствам. Это необходимо, создав политику, которая определяет уровень защиты и сайты, к которые необходимо применять защиту.

- Конфиденциальные сайты. Разрешить доступ только для браузера. Это не позволяет пользователям изменять и скачивать файлы.
- Строго регулируемые сайты: блокируют доступ к неурегулированным устройствам.

См. в рублях "Блокировка или ограничение доступа к определенным SharePoint или OneDrive учетным записям" в [control access from unmanaged devices.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>Совместное работу этих политик

Важно понимать, что разрешения SharePoint обычно основаны на бизнес-потребности в доступе к сайтам. Эти разрешения управляются владельцами сайтов и могут быть очень динамичными. Использование SharePoint политик доступа к устройствам обеспечивает защиту этих сайтов независимо от того, назначены ли пользователи группе Azure AD, связанной с базовой, чувствительной или строго регулируемой защитой.

На следующем рисунке приводится пример того, SharePoint политики доступа к устройствам защищают доступ к сайтам для пользователя.

[![Пример защиты SharePoint для политик доступа к устройствам](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[См. более крупную версию этого изображения](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

Джеймсу назначены базовые политики условного доступа, но ему может быть предоставлен доступ SharePoint сайтов с конфиденциальной или строгой защитой.

- Если Джеймс имеет доступ к конфиденциальному или строго регулируемом сайту, он является участником использования своего компьютера, его доступ предоставляется до тех пор, пока его компьютер соответствует требованиям.
- Если Джеймс получает доступ к конфиденциальному сайту, он является участником использования его неугодного телефона, что разрешено для базовых пользователей, он получит доступ только для браузера к конфиденциальному сайту из-за политики доступа к устройству, настроенной для этого сайта.
- Если Джеймс имеет доступ к строго регулируемому сайту, он является участником использования своего неурегулированного телефона, он будет заблокирован из-за политики доступа, настроенной для этого сайта. Он может получить доступ к этому сайту только с помощью управляемого и совместимый ПК.

## <a name="next-step"></a>Следующий этап

![Шаг 4. Политики для Microsoft 365 облачных приложений](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Настройка политик условного доступа для:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)