---
title: Технологии Microsoft Desktop управляемых
description: В этом разделе перечислены технологии и используется в Microsoft Desktop управляемых приложений.
keywords: Службы Microsoft Desktop управляемых, Microsoft 365, документация
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870644"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии Microsoft Desktop управляемых

В этом разделе перечислены технологии и используется в Microsoft Desktop управляемых приложений.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 E5 лицензии (или аналогичной) является обязательным для службы Microsoft управляемых Desktop. Ниже приведены все компоненты, которые включены в эту лицензию и как использует Microsoft Desktop управляемых каждого компонента с Microsoft Desktop управляемых устройств.  В разделах Microsoft Desktop управляемых приведено подробное описание конкретных ролей и обязанностей для каждой области. 

Microsoft 365 E5 включает в себя 3 компонента: Office 365 E5, Windows 10 Enterprise и E5, мобильности Enterprise + E5 безопасности.  

## <a name="office-365-e5"></a>Office 365 E5
 |
 --- | ---
Office 365 Standard Suite (64-разрядная) * | Стандартный пакет приложений Office приложений отправляется с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Скайп для бизнеса, OneNote.<br><br>64-разрядная щелкните, чтобы выполнить полный версий Microsoft Project и Microsoft Visio (C2R) не включаются в стандартный набор Office 365.  Тем не менее с момента установки этих приложений, зависят от стандартной установки набора приложений Office, управляемых Microsoft Desktop создан развертываний Intune по умолчанию и группы безопасности, клиент будет использовать для развертывания этих приложений конечные пользователи с корпоративным лицензированием.  
Приложения в магазине |    Microsoft Sway, группами Майкрософт, рабочий стол Power BI (не Pro) не поставляемым с устройством. Эти приложения доступны для загрузки из хранилища Microsoft.
Приложения Win32 |    Power BI Pro, Azure сведения о защите клиента и планировщик работы Microsoft не поставляемым с устройства и упаковывать для развертывания клиента. 
Веб-приложений |  Yammer, Office Online Delve, поток StaffHub, PowerApps не поставляются вместе с устройством. Пользователи могут получить доступ к веб-версия этих приложений с помощью браузера.
Скайп для бизнеса облачные УАТС | Эта функция доступна через Office 365 E5. Microsoft Desktop управляемых не будет управлять любыми аспектами этой службы

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Защита учетных данных |  Microsoft Desktop управляемых будет ознакомиться с рекомендациями и управление ими аспектов облачной этой функции
Защита устройства (управления приложения Защитник Windows)   | Microsoft Desktop управляемых будет создать политику. Клиент будет управлять подписей
Управление AppLocker |  Microsoft Desktop управляемых будет создать политику. Клиент будет управлять подписей
Виртуализация приложений (App-V) |    Microsoft Desktop управляемых не поддерживает этот тип развертывания, как он не поддерживается на Intune.
Виртуализация интерфейса пользователя (значение V) | Этот параметр не используется с рабочего стола Microsoft управляемых управляемых устройств
Управляемые пользовательского интерфейса  | Не используется с рабочего стола Microsoft управляемых управляемых устройств. MDM используется в качестве решения для управления устройствами
Advanced Threat Protection в Защитнике Windows |   Используется с рабочего стола управляемых Майкрософт для управления политики безопасности устройств. 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
Enterprise Mobility + Security E3<br>P2 Premium Azure Active Directory |    Все аспекты мобильности Enterprise + E3 безопасности и AADP могут быть использованы для управления устройствами MDM
Microsoft Cloud App Security |  Это дополнительная функция, которая клиентов можно использовать со службой управляемых Microsoft Desktop.
Защита P2 Azure сведения  |Это дополнительная функция, которая клиентов можно использовать со службой управляемых Microsoft Desktop.