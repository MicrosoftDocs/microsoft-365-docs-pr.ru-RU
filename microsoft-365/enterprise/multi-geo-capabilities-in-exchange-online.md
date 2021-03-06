---
title: Exchange с поддержкой нескольких регионов
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Узнайте о возможностях нескольких geo в Exchange Online, таких как ограничения функций и размещение почтовых ящиков.
ms.openlocfilehash: c7c7699906b92e09f88f59bb9d34d1c3b2c36135
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229807"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Поддержка нескольких регионов в Exchange Online

В среде с поддержкой нескольких регионов можно выбирать расположение содержимого почтового ящика Exchange Online (неактивных данных) для отдельных пользователей.

Вы можете размещать почтовые ящики в периферийных расположениях, используя следующие способы:

- Создание нового почтового ящика Exchange Online непосредственно в периферийном расположении.

- Перемещение существующего почтового ящика Exchange Online в периферийное расположение путем изменения предпочтительного расположения данных пользователя.

- Перенос почтового ящика из локальной организации Exchange непосредственно в периферийное расположение.

## <a name="mailbox-placement-and-moves"></a>Размещение и перенос почтового ящика

После завершения корпорацией Майкрософт необходимых действий по настройке поддержки нескольких регионов Exchange Online будет учитывать атрибут **PreferredDataLocation** объектов пользователей в Azure AD.

Exchange Online синхронизирует свойство **PreferredDataLocation** из Azure AD в свойство **MailboxRegion** в службе каталогов Exchange Online. Значение свойства **MailboxRegion** определяет географическое расположение, в котором размещаются почтовые ящики пользователей и все связанные архивные почтовые ящики. Нельзя настроить размещение основного почтового ящика пользователя и архивных почтовых ящиков в разных географических расположениях. Для каждого объекта user можно настроить только одно географическое расположение.

- Если свойство **PreferredDataLocation** настраивается для пользователя с существующим почтовым ящиком, почтовый ящик помещается в очередь перемещения и автоматически переносится в указанное географическое расположение.

- Если свойство **PreferredDataLocation** настраивается для пользователя без почтового ящика, при подготовке почтового ящика он будет располагаться в указанном географическом расположении.

- Если свойство **PreferredDataLocation** не указано для пользователя, при подготовке почтового ящика он будет располагаться в центральном географическом расположении.

- Если код **PreferredDataLocation** неверен (например, опечатка NAN вместо NAM), почтовый ящик будет расположен в центральном географическом расположении.

**Примечание.** Функция поддержки нескольких регионов и собрания Skype для бизнеса Online, проводящиеся с учетом региона, используют свойство **PreferredDataLocation** объектов user для расположения служб. Если вы настроите значения **PreferredDataLocation** объектов user для собраний, проводящихся с учетом региона, почтовый ящик для этих пользователей будет автоматически перемещен в указанное географическое расположение после включения поддержки нескольких регионов в клиенте Microsoft 365.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Ограничения функций для поддержки нескольких регионов в Exchange Online

- Функции безопасности и соответствия требованиям (например, аудит и обнаружение электронных данных), доступные в Центре администрирования Exchange (EAC), недоступны в организациях с поддержкой нескольких регионов. Вместо этого требуется использовать [Центр безопасности и соответствия требованиям Microsoft 365](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) для настройки функций безопасности и соответствия требованиям.

- Пользователи Outlook для Mac могут столкнуться с временной потерей доступа к своей папке серверного архива при перемещении почтового ящика в новое географическое расположение. Это состояние возникает, когда основной и архивный почтовые ящики пользователя находятся в разных географических расположениях, так как перемещение почтовых ящиков в разных регионах может выполняться в разное время.

- Пользователи не могут делиться *папками почтового ящика* между разными географическими расположениями в Outlook в Интернете (прежнее название — Outlook Web App или OWA). Например, пользователь из Европейского союза не может использовать Outlook в Интернете, чтобы открыть общую папку в почтовом ящике, расположенном в Соединенных Штатах. Однако пользователи Outlook в Интернете могут открывать *другие почтовые ящики* в разных географических расположениях, используя отдельное окно браузера, как описано в разделе [Открытие почтового ящика другого пользователя в отдельном окне браузера в Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).

  **Примечание**. Предоставление общего доступа к папке почтового ящика для разных географических расположений поддерживается в Outlook для Windows.

- В организациях с несколькими регионами поддерживаются общедоступные папки. Однако общедоступные папки должны оставаться в центральном географическом расположении. Вам не удастся переместить общедоступные папки в периферийные географические расположения.

- В среде с несколькими регионами аудит почтовых ящиков для разных географических расположений не поддерживается. Например, если пользователю назначены разрешения на доступ к общему почтовому ящику в другом географическом расположении, действия с почтовым ящиком, выполняемые этим пользователем, не регистрируются в журнале аудита почтовых ящиков общего почтового ящика. Дополнительные сведения см. в статье [Управление аудитом почтовых ящиков](../compliance/enable-mailbox-auditing.md).
