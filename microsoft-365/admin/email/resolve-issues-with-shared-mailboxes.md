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
description: При настройках общих почтовых ящиков могут возникнуть ошибки. Попробуйте эти решения, если у вас возникли проблемы с общими почтовыми ящиками.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706134"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Решение проблем с общими почтовыми ящиками

Если вы видите сообщения об ошибках при создании или использовании общего почтового ящика, попробуйте эти возможные решения. 

## <a name="error-when-creating-shared-mailboxes"></a>Ошибка при создании общих почтовых ящиков
<a name="bkmk_Fix"> </a>

Если вы видите сообщение об ошибке, прокси-адрес "smtp:<имя общего почтового ящика" уже используется прокси-адресами или **\> LegacyExchangeDN \<name> ". Выберите другой прокси-адрес,** это означает, что вы пытаетесь дать общему почтовому ящику имя, которое уже используется. Например, предположим, что вам необходимо завести общие почтовые ящики с именами info@domain1 и info@domain2. Это можно сделать двумя способами:

  - Используйте Windows PowerShell. Инструкции по созданию общих почтовых ящиков с одинаковыми псевдонимами в различных доменах см. в этой [записи блога.](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Назови второй общий почтовый ящик, который отличается от начала, чтобы обойти ошибку. Затем в центре администрирования переименуем общий почтовый ящик в нужный вам адрес.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Ошибка при не отправке разрешений при использовании общего почтового ящика

Если вы создали общий почтовый ящик, а затем попробуете отправить из него сообщение, вы можете получить это:

**Это сообщение не удалось отправить. У вас нет разрешения на отправку сообщения от имени указанного пользователя.**

Это сообщение появляется, Microsoft 365 возникает проблема задержки репликации. Он должен уйти примерно через час, когда сведения о новом общем почтовом ящике (или добавленных пользователях) будут реплицированы во всех центрах обработки данных. Подождите час, а затем попробуйте еще раз отправить сообщение.

## <a name="related-content"></a>См. также:

[Сведения об общих почтовых ящиках](about-shared-mailboxes.md) (статья)\
[Создание общего почтового ящика](create-a-shared-mailbox.md) (статья)\
[Настройка общего почтового ящика](configure-a-shared-mailbox.md) (статья)\
[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md) (статья)\
[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md) (статья)


    

