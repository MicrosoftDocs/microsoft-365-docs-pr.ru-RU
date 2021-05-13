---
title: Microsoft Information Protection в Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Внедрение Microsoft Information Protection (MIP) для защиты конфиденциальной информации в любом расположении, где она находится или куда перемещается.
ms.openlocfilehash: a68f8dee00117af1fa4d7be5f459ed5c850a5100
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332754"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection в Microsoft 365

>*[Лицензирование для Центра безопасности и соответствия требованиям Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Внедрение Microsoft Information Protection (MIP) для поиска, классификации и защиты конфиденциальной информации в любом расположении, где она находится или куда перемещается.

Возможности MIP включены в Соответствие требованиям Microsoft 365 и обеспечивают инструменты, с помощью которых можно [узнать структуру своих данных](#know-your-data), [защитить их](#protect-your-data) и [предотвратить потерю данных](#prevent-data-loss).

![Изображение того, как MIP помогает находить, классифицировать и защищать конфиденциальные данные](../media/powered-by-intelligent-platform.png)

Сведения об управлении данными см. в статье [Microsoft Information Governance в Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Изучение данных

> [!NOTE]
> Сведения о классификации данных и присвоении им меток в Azure Purview (в настоящее время доступно в предварительной версии) см. в статье [Автоматическое применение меток к содержимому в Azure Purview](/azure/purview/create-sensitivity-label).
> 
> Объявления о выпуске Azure Purview см. в следующих записях блога: [Microsoft Information Protection и Microsoft Azure Purview: вместе еще лучше](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) и [Azure Purview на весенней конференции Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).


Чтобы ознакомиться с ландшафтом данных и идентифицировать важные данные в гибридной среде, используйте следующие возможности:
 
|Возможность|Устраняемая проблема|Начало работы|
|:------|:------------|:--------------------|
|[Типы конфиденциальной информации](sensitive-information-type-learn-about.md)| Определение конфиденциальных данных с помощью встроенных или пользовательских регулярных выражений либо функции. Прямое свидетельство включает ключевые слова, доверительные уровни и расстояние.| [Настройка встроенных типов конфиденциальной информации](customize-a-built-in-sensitive-information-type.md)|
|[Обучаемые классификаторы](classifier-learn-about.md)| Определение конфиденциальных данных с помощью использования примеров интересующих вас данных, а не определения частей элемента (сопоставления шаблонов). Вы можете использовать встроенные классификаторы или обучить классификатор с помощью собственного контента.| [Начало работы с обучаемыми классификаторами](classifier-get-started-with.md) |
|[Классификация данных](data-classification-overview.md) | Графическая идентификация элементов в вашей организации, помеченных меткой конфиденциальности, меткой хранения или классифицированных. Вы также можете использовать эти сведения, чтобы получить аналитику действий, выполняемых вашими пользователями с этими элементами. | [Начало работы с обозревателем содержимого](data-classification-content-explorer.md)<br /><br /> [Начало работы с обозревателем действий](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Защита данных

Чтобы применить гибкие действия по защите, включающие шифрование, ограничение доступа и визуальную маркировку, используйте следующие возможности:

|Возможность|Устраняемая проблема|Начало работы|
|:------|:------------|---------------------|
|[Метки конфиденциальности](sensitivity-labels.md)| Единое решение для приложений, служб и устройств, предназначенное для добавления меток и защиты данных в процессе их перемещения внутри организации и за ее пределами. <br /><br />Примеры сценариев: <br /> [Управление метками конфиденциальности для приложений Office](sensitivity-labels-office-apps.md)<br /> [Шифрование документов и сообщений электронной почты](encryption-sensitivity-labels.md )<br /> [Применение и просмотр меток в Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> Полный список сценариев для меток конфиденциальности см. в документации по началу работы.|[Начало работы с метками конфиденциальности](get-started-with-sensitivity-labels.md) |
|[Клиент унифицированных меток Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2)| Расширение применения меток конфиденциальности для дополнительных функций и возможностей на компьютерах Windows, включая добавление меток и защиту всех типов файлов из проводника и PowerShell<br /><br /> Примеры дополнительных возможностей: [Настраиваемые конфигурации для клиента унифицированных меток Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Руководство администратора по клиенту унифицированных меток Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Шифрование с двойным ключом](double-key-encryption.md)| В любых обстоятельствах только ваша организация сможет расшифровать защищенное содержимое. В соответствии с нормативными требованиями может потребоваться хранить ключи шифрования в определенных географических границах. | [Развертывание шифрования с двойным ключом](double-key-encryption.md#deploy-dke)|
|[Шифрование сообщений Office 365 (OME)](ome.md)| Шифрование сообщений электронной почты и вложенных документов, отправленных любому пользователю на любое устройство, позволяющее только авторизованным получателям прочитать отправленную информацию.  <br /><br />Пример сценария: [Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений](revoke-ome-encrypted-mail.md) | [Настройка новых возможностей шифрования сообщений](set-up-new-message-encryption-capabilities.md)|
|[Шифрование службы с помощью ключа клиента](customer-key-overview.md) | Защита от просмотра данных неавторизованными системами или сотрудниками и добавление шифрования диска BitLocker в центры обработки данных Microsoft. | [Настройка ключа клиента для Office 365](customer-key-set-up.md)|
|[Управление правами на доступ к данным (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Защита списков и библиотек SharePoint: при извлечении документов только авторизованные пользователи могут просматривать и использовать скачанные файлы в соответствии с заданными политиками. | [Настройка управления правами на доступ к данным (IRM) в Центре администрирования SharePoint](set-up-irm-in-sp-admin-center.md)|
[Соединитель управления правами](/azure/information-protection/deploy-rms-connector) |Только защита существующих локальных развертываний, использующих Exchange либо SharePoint Server, или файловых серверов, на которых запущены Windows Server и инфраструктура классификации файлов (FCI). | [Шаги по развертыванию соединителей RMS](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Сканер унифицированных меток Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Поиск, добавление меток и защита конфиденциальной информации, находящейся в локальных хранилищах данных. | [Настройка и установка сканера унифицированных меток Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Поиск, добавление меток и защита конфиденциальной информации, находящейся в облачных хранилищах данных. | [Поиск, классификация, добавление меток и защита регламентированных и конфиденциальных данных, хранящихся в облаке](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Пакет SDK для Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|Расширение применения меток конфиденциальности для сторонних приложений и служб.  <br /><br /> Пример сценария: [Задание и получение метки конфиденциальности (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Настройка пакета SDK для Microsoft Information Protection (MIP)](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Защита от потери данных

Чтобы предотвратить случайное предоставление неограниченного общего доступа к конфиденциальной информации, воспользуйтесь следующими возможностями:


|Возможность|Устраняемая проблема|Начало работы|
|:------|:------------|:---------------------|
|[Защита от потери данных](dlp-learn-about-dlp.md)| Предотвращение непреднамеренного предоставления общего доступа к конфиденциальным элементам. | [Начало работы со стандартной политикой защиты от потери данных](get-started-with-the-default-dlp-policy.md)|
|[Защита от потери данных в конечной точке](endpoint-dlp-learn-about.md)| Расширение возможностей DLP для элементов, которые используются и к которым предоставляется общий доступ на компьютерах с Windows 10. | [Начало работы с функцией защиты от потери данных в конечной точке](endpoint-dlp-getting-started.md)|
|[Расширение соответствия требованиям Майкрософт (предварительная версия)](dlp-chrome-learn-about.md) | Расширение возможностей защиты от потери данных в браузере Chrome | [Начало работы с расширением соответствия требованиям Майкрософт (предварительная версия)](dlp-chrome-get-started.md)|
|[Локальный сканер для защиты от потери данных Microsoft 365 (предварительная версия)](dlp-on-premises-scanner-learn.md)|Расширяет возможности защиты от потери данных по отслеживанию действий и защитных мер для файлов в локальных общих папках, а также в папках и библиотеках документов SharePoint.|[Начало работы с локальным сканером для защиты от потери данных Microsoft 365 (предварительная версия)](dlp-on-premises-scanner-get-started.md)|
|[Защита конфиденциальной информации в чатах и сообщениях каналов Microsoft Teams](dlp-microsoft-teams.md) | Расширяет некоторые функции защиты от потери данных для чатов и сообщений каналов Teams | [Сведения о политике защиты от потери данных по умолчанию в Microsoft Teams (предварительная версия)](dlp-teams-default-policy.md)|
