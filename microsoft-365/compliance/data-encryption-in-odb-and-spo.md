---
title: Шифрование данных в OneDrive для бизнеса и SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
description: Понимание основных элементов шифрования данных для обеспечения их защиты в OneDrive для бизнеса и SharePoint Online.
ms.openlocfilehash: c8ac6f0a4364117c475637e0288d7a1a790d57c2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089602"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="f23ad-103">Шифрование данных в OneDrive для бизнеса и SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f23ad-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="f23ad-104">Понимание основных элементов шифрования данных для обеспечения их защиты в OneDrive для бизнеса и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f23ad-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="overview"></a><span data-ttu-id="f23ad-105">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="f23ad-105">Overview</span></span>

<span data-ttu-id="f23ad-p101">Office 365  высокобезопасная среда, обеспечивающая расширенную защиту на нескольких уровнях: физическую безопасность центра обработки данных, сетевую безопасность, безопасность доступа, безопасность приложений и данных. Данная статья посвящена вопросам защиты данных, которые хранятся и передаются, благодаря их шифрованию для OneDrive для бизнеса и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p101">Office 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security. This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="f23ad-108">Описание безопасности Office 365 в целом приведено [в статье Security in office 365 White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span><span class="sxs-lookup"><span data-stu-id="f23ad-108">For a description of Office 365 security as a whole, see [Security in Office 365 White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span></span>
  
<span data-ttu-id="f23ad-109">Посмотрите видео о принципах шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="f23ad-109">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="f23ad-110">Шифрование транзитных данных</span><span class="sxs-lookup"><span data-stu-id="f23ad-110">Encryption of data in transit</span></span>

<span data-ttu-id="f23ad-111">В OneDrive для бизнеса и SharePoint Online используются два сценария для входящих и исходящих данных в центрах данных.</span><span class="sxs-lookup"><span data-stu-id="f23ad-111">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="f23ad-p102">**Связь клиента с сервером.** Для связи с OneDrive для бизнеса через Интернет используются подключения на основе SSL/TLS. Все SSL-подключения устанавливаются с помощью 2048-битных ключей.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p102">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="f23ad-p103">**Перемещение данных между центрами данных.** Георепликация для обеспечения возможности аварийного восстановления данных  основная причина такого перемещения. Например, по этому каналу передаются разностные файлы хранилищ BLOB-объектов и журналы транзакций SQL Server. Хотя эти данные передаются по частной сети, они дополнительно защищены лучшим в своем классе шифрованием.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p103">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="f23ad-117">Шифрование статических данных</span><span class="sxs-lookup"><span data-stu-id="f23ad-117">Encryption of data at rest</span></span>

<span data-ttu-id="f23ad-118">Шифрование статических включает два компонента: шифрование BitLocker на уровне диска и пофайловое шифрование клиентского контента.</span><span class="sxs-lookup"><span data-stu-id="f23ad-118">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="f23ad-119">Развертывание BitLocker выполняется для OneDrive для бизнеса и SharePoint Online в службе.</span><span class="sxs-lookup"><span data-stu-id="f23ad-119">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="f23ad-120">Шифрование на основе файлов также можно искать в OneDrive для бизнеса и SharePoint Online в Office 365 с несколькими клиентами и новыми выделенными средами, созданными для технологии с несколькими клиентами.</span><span class="sxs-lookup"><span data-stu-id="f23ad-120">Per-file encryption is also in OneDrive for Business and SharePoint Online in Office 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="f23ad-p105">BitLocker шифрует все данные на диске, но пофайловое шифрование еще более эффективно благодаря использованию уникального ключа шифрования для каждого файла (а также каждого его обновления). Перед сохранением ключи к зашифрованному контенту хранятся отдельно от контента. На каждом этапе шифрования используется стандарт шифрования AES с 256-разрядными ключами, который соответствует федеральному стандарту обработки информации FIPS 140-2. Зашифрованный контент распределяется между несколькими контейнерами в центре обработки данных, каждый из которых имеет уникальные учетные данные. Эти учетные данные хранятся отдельно от контента или ключей к нему.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p105">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="f23ad-127">Дополнительные сведения о соответствии требованиям FIPS 140-2 приведены в статье [соответствие требованиям стандарта fips 140-2](https://go.microsoft.com/fwlink/?LinkId=517625).</span><span class="sxs-lookup"><span data-stu-id="f23ad-127">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="f23ad-p106">При шифрование статических данных на уровне файлов используется хранилище больших двоичных объектов, которое обеспечивает практически неограниченный размер виртуального хранилища и высокий уровень защиты. Весь пользовательский контент в OneDrive для бизнеса и SharePoint Online будет перенесен в хранилище больших двоичных объектов. Вот как осуществляется защита данных:</span><span class="sxs-lookup"><span data-stu-id="f23ad-p106">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="f23ad-p107">Весь контент шифруется (возможно, с помощью нескольких ключей) и распределяется в центре данных. Каждый сохраняемый файл, в зависимости от размера, разбивается на один или несколько блоков. Затем каждый блок шифруется с использованием своего уникального ключа. Аналогичным образом происходит шифрование обновлений: пакеты изменений (дельты), отправляемые пользователем, разбиваются на блоки, каждый из которых шифруется собственным ключом.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="f23ad-p108">Все эти блоки (файлы, фрагменты файлов, дельты обновлений) сохраняются как большие двоичные объекты в хранилище больших двоичных объектов. Они также распределяются между несколькими контейнерами больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="f23ad-137">"Карта", используемая для повторной сборки файла из компонентов, хранится в базе данных контента.</span><span class="sxs-lookup"><span data-stu-id="f23ad-137">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="f23ad-p109">Каждый контейнер больших двоичных объектов использует собственные уникальные учетные данные для каждого типа доступа (на чтение, запись, перечисление и удаление). Каждый набор учетных данных содержится в безопасном хранилище ключей и регулярно обновляется.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="f23ad-140">Другими словами, в пофайловом статическом шифровании задействованы три различных типа хранилищ, каждое со своими определенными функциями:</span><span class="sxs-lookup"><span data-stu-id="f23ad-140">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="f23ad-p110">Контент хранится в виде зашифрованных больших двоичных объектов в хранилище больших двоичных объектов. Ключ для каждого блока контента зашифрован и хранится отдельно в базе данных контента. Сам контент не содержит никакой информации о его расшифровке.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="f23ad-p111">База данных контента  это база данных SQL Server. Она содержит карту, необходимую для нахождения и повторной сборки всех больших двоичных объектов контента, содержащихся в хранилище больших двоичных объектов, а также ключи для расшифровки этих объектов.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p111">The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="f23ad-p112">Каждый из этих трех компонентов хранения  хранилище больших двоичных объектов, база данных контента и хранилище ключей  физически отделены друг от друга. Информация, хранящаяся в каждом из компонентов, не может использоваться самостоятельно. Это обеспечивает исключительный уровень безопасности. Без доступа ко всем трем хранилищам невозможно извлечь ключи для блоков, расшифровать ключи и сделать их пригодными для использования, связать ключи с соответствующими блоками, расшифровать любой из блоков или воссоздать документ из составляющих его блоков.</span><span class="sxs-lookup"><span data-stu-id="f23ad-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>