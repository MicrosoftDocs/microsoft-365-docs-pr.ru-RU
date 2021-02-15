---
title: Решение проблем с общими почтовыми ящиками
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Попробуйте эти решения, если возникают проблемы с общими почтовыми ящиками.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926490"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Решение проблем с общими почтовыми ящиками

Если при создании или использовании общего почтового ящика вы видите сообщения об ошибках, попробуйте использовать эти возможные решения. 

## <a name="error-when-creating-shared-mailboxes"></a>Ошибка при создании общих почтовых ящиков
<a name="bkmk_Fix"> </a>

Если вы видите сообщение об ошибке, прокси-адрес "smtp:<shared mailbox name" уже используется прокси-адресами или **\> LegacyExchangeDN \<name> ". Выберите другой прокси-адрес.** Это означает, что вы пытаетесь предоставить общему почтовому ящику имя, которое уже используется. Например, предположим, что вам необходимо завести общие почтовые ящики с именами info@domain1 и info@domain2. Это можно сделать двумя способами:

  - Используйте Windows PowerShell. Инструкции по созданию общих почтовых ящиков с одинаковым псевдонимом в разных доменах см. в этой записи [блога](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Назовем второй общий почтовый ящик чем-то другим, чтобы обойти ошибку. Затем в Центре администрирования переименуем общий почтовый ящик в нужный вам почтовый ящик.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Ошибка без разрешений на отправку при использовании общего почтового ящика

Если вы создали общий почтовый ящик и пытаетесь отправить из него сообщение, вы можете получить:

**Не удалось отправить это сообщение. У вас нет разрешения на отправку сообщения от имени указанного пользователя.**

Это сообщение появляется, когда в Microsoft 365 возникает проблема задержки репликации. Она должна пройти примерно через час, когда сведения о новом общем почтовом ящике (или добавленных пользователях) реплицированы во всех центрах обработки данных. Подождите час, а затем попробуйте еще раз отправить сообщение.

## <a name="related-articles"></a>Связанные статьи

[Сведения об общих почтовых ящиках](about-shared-mailboxes.md)

[Создание общего почтового ящика](create-a-shared-mailbox.md)

[Настройка общего почтового ящика](configure-a-shared-mailbox.md)

[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md)

[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md)


    

