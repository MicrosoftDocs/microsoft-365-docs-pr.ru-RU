---
title: Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: Прежде чем приступить к работе с EOP, необходимо знать несколько моментов.
ms.openlocfilehash: c86d8dbf71cdfddf0562e9c572dc8d65043e1c69
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032868"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection

Добро пожаловать в службу фильтрации почты, размещенную в Microsoft Exchange Online Protection (EOP). Прежде чем начать работу с EOP и использовать это содержимое, необходимо знать следующее.

- Чтобы узнать больше о EOP, ознакомьтесь с [описанием службы Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Другие материалы: [Обзор Exchange Online Protection](exchange-online-protection-overview.md), [Общие вопросы и ответы EOP](eop-general-faq.md)и [функции EOP](eop-features.md), а также [Домашняя страница Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

- Чтобы приступить к работе с EOP, новые клиенты должны заголовков, чтобы [настроить службу EOP](set-up-your-eop-service.md). В этом разделе описываются действия, которые помогут вам получить EOP и запустить его.

- Если вам необходима дополнительная помощь или вы хотите поделиться идеями, посетите [форум EOP](https://go.microsoft.com/fwlink/?LinkId=285351).

## <a name="eop-help-for-administrators"></a>Справка по службе EOP для администраторов

Содержимое справки EOP для администраторов состоит из следующих категорий верхнего уровня.

- [Обзор Exchange Online Protection](exchange-online-protection-overview.md): в этой статье представлены сведения о том, как работает EOP и приведены ссылки на дополнительные сведения.

- [Функции EOP](eop-features.md): предоставляет список функций, доступных в EOP.

- [Настройте службу EOP](set-up-your-eop-service.md): в этой статье приведены инструкции по настройке службы EOP и ссылки на дополнительные сведения.

- [Переключитесь на EOP из Google Postini, с помощью Barracuda спама и антивирусного брандмауэра или Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): описывает процесс переключения на EOP из другой программы защиты электронной почты.

- [Управление получателями и группами ролей администраторов в EOP](manage-recipients-and-admin-role-groups-in-eop.md): инструкции по управлению получателями и назначению пользователям групп ролей администраторов.

- [Почтовый ящик в EOP: в](mail-flow-in-eop.md)этой статье описано, как настроить пользовательские сценарии обработки почты с помощью соединителей, как управлять доменами, связанными со службой, и как включить функцию пограничной блокировки на основе каталогов (DBEB).

- Рекомендации [по настройке EOP](best-practices-for-configuring-eop.md): в этой статье описываются рекомендуемые параметры конфигурации и рекомендации по настройке и подготовке службы.

- [Политика обмена сообщениями и соответствие требованиям в EOP](messaging-policy-and-compliance-in-eop.md): в этой статье описано, как использовать правила для обработки почтовых ящиков Exchange (также называемые правилами транспорта) для применения определенных нормативных положений и политик компании, а также как использовать отчеты аудита для отслеживания изменений конфигурации службы.

- [Защита от нежелательной почты и вредоносных программ в Office 365](anti-spam-and-anti-malware-protection.md): Описывает фильтрацию нежелательной почты и фильтрацию вредоносных программ, а также показывает, как настроить их для лучшего соответствия потребностям вашей организации. Кроме того, в этом разделе описываются задачи, которые администраторы и конечные пользователи могут выполнить для сообщений, помещенных в карантин.

- [Отчеты и трассировка сообщений в Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): в этой статье описываются доступные средства отчетов и устранения неполадок.

- [Центр администрирования Exchange в Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md): в этой статье описывается, как получить доступ к интерфейсу управления центра администрирования Exchange и перемещаться по нему для управления службой EOP.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): содержит сведения об удаленной оболочке PowerShell, которая позволяет управлять службой EOP из командной строки.

- [Справка и поддержка для EOP](help-and-support-for-eop.md) В этом разделе представлены сведения о том, как получить помощь и техническую поддержку.

## <a name="eop-help-for-end-users"></a>Справки по службе EOP для конечных пользователей

Содержимое справки, которое поможет конечным пользователям EOP управлять нежелательной почтой, состоит из следующих разделов:

- [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md)

- Конечные пользователи могут добавлять отправители в список надежных отправителей или блокировать список отправителей в Outlook или Outlook в Интернете. Администраторы также могут изменять эти списки в почтовых ящиках пользователей. Дополнительные сведения см в разделе [о параметрах нежелательной почты в Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook).

- [Справка и поддержка для EOP](help-and-support-for-eop.md) В этом разделе представлены сведения о том, как получить помощь и техническую поддержку.
