---
title: Удаление лицензии из общего почтового ящика
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Удалите лицензию из общего почтового ящика, чтобы назначить ее другому пользователю или вернуть лицензию, чтобы вы не платили за нее. '
ms.date: 05/11/2021
ms.openlocfilehash: dd2d99d762a4a68a9b0400353d64dabb536a891c
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821432"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Удаление лицензии из общего почтового ящика

Общие почтовые ящики обычно не требуют лицензии. Следуйте этим инструкциям, чтобы удалить лицензию из общего почтового ящика, чтобы можно было назначить ее пользователю или вернуть лицензию, чтобы не платить за не нужная лицензия.

> [!NOTE]
>
> Лицензия требуется в следующих сценариях:
>
> 1. Общий почтовый ящик имеет более 50 ГБ используемого хранилища.
> 2. Общий почтовый ящик использует архивативную передачу на месте.
> 3. Общий почтовый ящик помещается в удержание судебного разбирательства.
> 4. Общий почтовый ящик имеет лицензию Microsoft Defender.

## <a name="remove-the-license"></a>Удаление лицензии

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

   > [!NOTE]
   > Необходимо удалить лицензию со страницы Активные пользователи. Вы не можете удалить лицензию со страницы Общих почтовых ящиков, так как лицензии — это параметры пользователя.
  
2. Выберите общий почтовый ящик.

3. Одна **вкладка Лицензии и Приложения,** развяжите **лицензии** и снимите поле для лицензии, необходимой для удаления.

4. Нажмите кнопку **Сохранить изменения**.

5. При возвращении на страницу **Активные** пользователи состояние общего почтового ящика будет **нелицензионным.**

6. Вы по-прежнему платите за лицензию. Чтобы перестать платить за это, [снимите лицензию из подписки.](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>См. также:

[Сведения об общих почтовых ящиках](about-shared-mailboxes.md) (статья)\
[Создание общего почтового ящика](create-a-shared-mailbox.md) (статья)\
[Настройка общего почтового ящика](configure-a-shared-mailbox.md) (статья)\
[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md) (статья)\
[Решение проблем с общими почтовыми ящиками](resolve-issues-with-shared-mailboxes.md) (статья)
