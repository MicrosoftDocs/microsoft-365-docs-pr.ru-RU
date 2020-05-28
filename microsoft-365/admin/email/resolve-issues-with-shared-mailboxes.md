---
title: Решение проблем с общими почтовыми ящиками
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Используйте эти решения при возникновении проблем с общими почтовыми ящиками.
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400020"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Решение проблем с общими почтовыми ящиками

Если вы видите сообщение об ошибке при создании или использовании общего почтового ящика, попробуйте эти решения. 

## <a name="error-when-creating-shared-mailboxes"></a>Ошибка при создании общих почтовых ящиков
<a name="bkmk_Fix"> </a>

Если отображается сообщение об ошибке, то **адрес прокси-сервера "SMTP: <общее имя почтового ящика \> " уже используется прокси-адресами или legacyExchangeDN " \<name> ". Выберите другой адрес прокси-сервера**, это означает, что вы пытаетесь присвоить общему почтовому ящику имя, которое уже используется. Например, предположим, что вам необходимо завести общие почтовые ящики с именами info@domain1 и info@domain2. Это можно сделать двумя способами:

  - Используйте Windows PowerShell. В этой записи блога приведены инструкции по [созданию общих почтовых ящиков с одинаковым псевдонимом в разных доменах](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365) .
    
  - Назовите второй общий почтовый ящик, который отличается от начального, чтобы получить сообщение об ошибке. Затем в центре администрирования переименуйте общий почтовый ящик в то, что нужно.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Ошибка при использовании общего почтового ящика при отсутствии разрешений на отправку

Если вы создали общий почтовый ящик, а затем попытаетесь отправить ему сообщение, вы можете сделать следующее:

**Не удалось отправить это сообщение. У вас нет разрешения на отправку сообщения от имени указанного пользователя.**

Это сообщение появляется, если в Microsoft 365 возникла проблема с задержкой репликации. Он должен отброситься в течение часа или таким образом, когда информация о новом общем почтовом ящике (или добавленном пользователе) реплицируется во всех наших центрах обработки данных. Подождите час и повторите попытку отправки сообщения.

## <a name="related-articles"></a>Связанные статьи

[Сведения об общих почтовых ящиках](about-shared-mailboxes.md)

[Создание общего почтового ящика](create-a-shared-mailbox.md)

[Настройка общего почтового ящика](configure-a-shared-mailbox.md)

[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md)

[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md)


    

