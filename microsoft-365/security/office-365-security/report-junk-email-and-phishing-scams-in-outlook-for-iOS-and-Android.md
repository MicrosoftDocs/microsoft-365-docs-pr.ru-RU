---
title: Сообщение о нежелательной и фишинговой почте в Outlook для iOS и Android
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
description: Администраторы могут узнать о встроенных вариантах отправки отчетов о нежелательной почте, а не о нежелательной почте и фишинговых сообщениях в Outlook для iOS и Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289177"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Сообщение о нежелательной и фишинговой почте в Outlook для iOS и Android в Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В организациях Microsoft 365 с почтовыми ящиками в Exchange [](../../enterprise/hybrid-modern-auth-overview.md)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете использовать встроенные параметры отчетов в Outlook для iOS и Android, чтобы отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные отрицательные результаты (разрешено использование нежелательной почты) и фишинговые сообщения в Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для наилучшего пользовательского интерфейса отправки рекомендуется использовать надстройки Report Message и Report Phishing. Дополнительные [сведения см.](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) в подстройки "Включить сообщение отчета" и "Включить надстройку report [Phishing".](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in)

- Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям. Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)

- Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик. Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)

- Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Если отчеты о нежелательной почте отключены для Outlook в политике отправки пользователей, нежелательные или фишинговые сообщения будут перемещены в папку нежелательной почты и не будут отправлены администратору или корпорации Майкрософт.