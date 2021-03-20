---
title: Сообщение нежелательной и фишинговой почты в Outlook для iOS и Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о встроенных нежелательных, а не нежелательных и фишинговых вариантах сообщений электронной почты в Outlook для iOS и Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eda0d8d43244834236a70374df6b7d6ccf0b69ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908822"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Сообщение нежелательной и фишинговой почты в Outlook для iOS и Android в Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В microsoft 365 организациях с почтовыми ящиками в Exchange [](../../enterprise/hybrid-modern-auth-overview.md)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные негативы (разрешена плохая электронная почта) и фишинговые сообщения в Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом

- Для наилучшего использования пользовательской отправки рекомендуется использовать надстройки Report Message и Report Phishing. Дополнительные [сведения см.](./enable-the-report-message-add-in.md) в [](./enable-the-report-phish-add-in.md) дополнительных сведениях.

- Если вы администратор в организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки в Центре & соответствия требованиям. Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)

- Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в статьи Политики отправки пользователей.](user-submission.md)

- Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Если нежелательное сообщение электронной почты отключено для Outlook в политике отправки пользователей, нежелательные или фишинговые сообщения будут перемещены в папку нежелательной почты и не будут сообщаться администратору или Корпорации Майкрософт.