---
title: Что изменится после перехода на Office 365 службы в новых немецких регионах центра обработки данных
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Сводка. Сведения о том, что изменилось для перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.
ms.openlocfilehash: e503df16cfdbe0985e635b07cb6b4a45bc55d367
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930407"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Что изменится после перехода на Office 365 службы в новых немецких регионах центра обработки данных

Миграции клиентов предназначены для минимального влияния на администраторов и пользователей. Однако для каждой рабочей нагрузки следует учитывать ряд моментов. Просмотрите следующие разделы, чтобы лучше понять опыт миграции для рабочих нагрузок.

Ниже ключевых различий между Microsoft Cloud Deutschland и службами Office 365 в новых немецких регионах центра обработки данных.

| Категория | Microsoft Cloud для Германии (Microsoft Cloud Deutschland) | Службы Office 365 в новых регионах центров обработки данных в Германии |
|:-------|:-----|:-------|
| Службы Microsoft 365, доступные для подписки только на один клиент Office 365 | 15 служб | 29 служб <br><br> Дополнительные сведения см. в дополнительных сведениях о доступности служб между различными Office 365 [облачными службами?.](ms-cloud-germany-transition.md#serv-avail) |
| Новые функции | Новые функции не будут доступны. | Новые функции будут доступны в соответствии с Office 365 службами. |
| Доверенное лицо для данных | Да | Нет |
| Взаимодействие между клиентами и глобальными клиентами Office 365 | Нет | Да |
| Размещение данных клиента | Данные клиентов будут храниться исключительно в немецких центрах обработки данных. | Microsoft будет хранить следующие данные клиентов в покое исключительно в Германии: <ul><li> Exchange Online почтовых ящиков (тело электронной почты, записи календаря и содержимое вложений электронной почты) </li><li> SharePoint Содержимое веб-сайта и файлы, хранимые на этом сайте, и файлы, загруженные в OneDrive для бизнеса </li></ul> |
| Применимые условия использования | [Термины Online Services с](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) этим [дополнением](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Условия использования веб-служб](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Что не меняется:

- Начальный домен клиента (например) с ИД клиента (GUID) и пользовательскими доменами сохранится `contoso.onmicrosoft.de` после миграции. 

- Запросы на проверку подлинности для ресурсов, переносимых в Office 365 службы, Office 365 службы проверки подлинности Azure `login.microsoftonline.com` ( ). Во время миграции ресурсы, которые остаются в Office 365 Германии, аутентификация в существующей службе Germany Azure `login.microsoftonline.de` ().

Соображения, которые следует отметить:

- Для управляемых учетных записей домена после копирования начального клиента Azure Active Directory (Azure AD) завершен (что является первым этапом миграции Azure AD в службу Azure AD Office 365), изменения паролей, изменения самообслуживающихся паролей (SSPR) и сброс паролей администраторами должны быть сделаны с порталов Office 365 служб. Запросы на обновление паролей из службы Германии на данный момент не увенчаются успехом, так как клиент Azure AD был перенесен в Office 365 службы. Сбросы федераированных паролей домена не влияют, так как они завершались в локальном каталоге.

- Входы Azure представлены на портале, на котором пользователь пытается получить доступ. Журналы аудита доступны только из конечной точки Office 365 служб после перехода. Перед переносом до завершения миграции необходимо сохранить журналы входа и аудита с портала Microsoft Cloud Deutschland.

- Сброс пароля, изменения пароля, сброс пароля администратором управляемых организаций (не использующих службы федерации Active Directory) должны выполняться через портал Office 365 служб. Попытки пользователей, которые имеют доступ к порталам Microsoft Cloud Deutschland для сброса паролей, не увенчаются неудачей.

- Общие запросы субъектов защиты данных (GDPR) выполняются с портала администрирования Office 365 служб Azure для будущих запросов. Любые устаревшие или нестандартные диагностические данные, проживающие в Microsoft Cloud Deutschland, удаляются за 30 дней.

## <a name="subscriptions--licenses"></a>Подписки & лицензии

- Office 365 и Dynamics из Microsoft Cloud Deutschland переходят в немецкий регион с помощью переноса Azure AD. Затем организация обновляется с учетом новых Office 365 служб. Во время краткого процесса передачи подписки изменения подписки блокируют.

- По мере перехода клиента на Office 365 службы его подписки и лицензии в Германии стандартизуются с помощью новых Office 365 услуг. Соответствующие Office 365 службы приобретаются для переданных подписок Германии. Пользователям, у которых есть лицензии в Германии, Office 365 лицензии на службы. По завершении работы устаревшие подписки в Германии отменяются и удаляются из текущего клиента Office 365 служб.

- После переноса отдельных рабочих нагрузок дополнительные функции Office 365 служб (таких как Microsoft Planner и Microsoft Flow) из-за новых Office 365 служб. Если это подходит для вашей организации, клиент или администратор лицензирования может отключить новые планы службы при планировании управления изменениями для внедрения новых служб. Инструкции по отключению планов служб, назначаемой лицензиям пользователей, см. в Microsoft 365 доступа к службам [пользователей.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

## <a name="exchange-online"></a>Exchange Online

- Exchange URL-адреса ресурсов переходят с устаревшей конечной точки Германии на конечную точку Office 365 служб `outlook.office.de` `outlook.office365.com` после миграции. Пользователи могут получать доступ к перенесенным почтовым ящикам с помощью устаревшего URL-адреса до завершения миграции. Клиенты должны как можно скорее перейти на новый URL-адрес после того, как Exchange миграция начнет влиять на выход из среды Германии. URL Office 365 службы для Outlook становятся доступными только после Exchange миграции.

- Почтовые ящики переносят в качестве процесса отыгрывки. Пользователи в вашей организации могут быть в Microsoft Cloud Deutschland или в немецком регионе во время перехода и являются частью одной Exchange организации (в том же глобальном списке адресов).

- Пользователи веб-Outlook Web App, которые имеют доступ к службе с помощью URL-адреса, где их почтовый ящик не находится, увидят дополнительные запросы на проверку подлинности. Например, если почтовый ящик пользователя находится в службе Office 365, а подключение Outlook Web App пользователя использует устаревшую конечную точку, пользователь сначала пройдет проверку подлинности, а затем `outlook.office.de` `login.microsoftonline.de` — `login.microsoftonline.com` . После завершения миграции пользователь может получить доступ к новому URL-адресу (), и он увидит только один ожидаемый запрос `https://outlook.office365.com` на вход. 

## <a name="sharepoint-online"></a>SharePoint Online

В SharePoint Online и OneDrive для бизнеса вы можете обмениваться элементами через Outlook. После нажатия Outlook кнопку создается и выталковыв в новое сообщение в Outlook Web App.

Обмен элементами в SharePoint Online и OneDrive для бизнеса через Outlook больше не работает после завершения миграции SharePoint Online. Мы признаем, что это известная проблема. Однако, поскольку Outlook находится на пути обесценения, исправление проблемы не планируется до тех пор, пока не будет откат.

## <a name="office-services"></a>Office Службы

Office Онлайн-службы доступны до `office.de` и во время перехода. После перехода почтовых ящиков пользователей в службы Office 365 пользователи должны начать использовать URL-адреса Office 365 служб. По мере переноса последующих Office 365 служб их интерфейс с office.com портала начнет работать.

Самая недавно используемая (MRU) служба в Office является переходом от Microsoft Cloud Deutschland к глобальным службам Office 365, а не к миграции. После миграции с портала Office.com будут видны только ссылки на MRU Office 365 глобальной службы. Ссылки MRU из Microsoft Cloud Deutschland не видны в качестве ссылок MRU в Office 365 глобальных службах. В Office 365 глобальных службах ссылки MRU доступны только после того, как миграция клиента достигла этапа 9.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Функции back-end Exchange Online Protection (EOP) копируется в новом регионе Германии.
- Office 365 Пользователям Центра безопасности и соответствия требованиям необходимо перейти к использованию глобальных URL-адресов в рамках `https://protection.office.com` миграции.

## <a name="skype-for-business-online"></a>Skype для бизнеса Online

Существующие клиенты Skype для бизнеса Online будут переходить в Microsoft Teams. Дополнительные сведения [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) см. в .

## <a name="office-365-video"></a>Office 365 Видео

Office 365 С 1 марта 2021 г. видео будет снято, и Office 365 видео не будет поддерживаться после завершения переноса SharePoint Online в новые немецкие регионы центра обработки данных. Содержимое Office 365 видео будет перенесено в рамках миграции SharePoint Online. Однако видео в Office 365 видео не будет отыграться в пользовательском интерфейсе Office 365 видео после SharePoint миграции. Дополнительные сведения о временной шкале миграции [в Office 365 видео в обзоре Microsoft Stream (классический).](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Следующий этап

[Понимание действий и последствий этапов миграции](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Сведения о программе миграции Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here)
