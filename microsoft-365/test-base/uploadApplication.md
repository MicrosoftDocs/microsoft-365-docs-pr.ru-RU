---
title: Передача пакета
description: Отправка приложений, сеянов и зависимостей на тестовую базу
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: e8b4323eda31c55bbf32de0996fc7bd48d54ade2
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323095"
---
# <a name="step-2-uploading-a-package"></a><span data-ttu-id="d19e7-103">Шаг 2. Отправка пакета</span><span class="sxs-lookup"><span data-stu-id="d19e7-103">Step 2: Uploading a Package</span></span>

<span data-ttu-id="d19e7-104">На странице портала Test Base перейдите к параметру Upload пакета на левой панели навигации, как показано ниже: Upload ![ новый пакет](Media/Upload-New-Package.png)</span><span class="sxs-lookup"><span data-stu-id="d19e7-104">On the Test Base portal page, navigate to the ‘Upload new package option on the left navigation bar as shown below: ![Upload a new package](Media/Upload-New-Package.png)</span></span>

<span data-ttu-id="d19e7-105">После этого выполните ниже действия, чтобы загрузить новый пакет.</span><span class="sxs-lookup"><span data-stu-id="d19e7-105">Once there, follow the steps below to upload a new package.</span></span>

## <a name="enter-details-for-your-package"></a><span data-ttu-id="d19e7-106">Ввод сведений для пакета</span><span class="sxs-lookup"><span data-stu-id="d19e7-106">Enter details for your package</span></span>

<span data-ttu-id="d19e7-107">На вкладке Сведения о тесте введите имя, версию и другие сведения пакета по запросу.</span><span class="sxs-lookup"><span data-stu-id="d19e7-107">On the Test details tab, type in your package's name, version and other details as requested.</span></span> 

<span data-ttu-id="d19e7-108">**Тестирование вне окна и** **функциональных функций** можно сделать с помощью этой панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d19e7-108">**Out-of-Box** and **Functional testing** can be done via this dashboard.</span></span>

<span data-ttu-id="d19e7-109">Ниже приводится руководство по заполняемой информации о пакете:</span><span class="sxs-lookup"><span data-stu-id="d19e7-109">The steps below provides a guide on how to fill out your package details:</span></span>

1.  <span data-ttu-id="d19e7-110">**Введите имя, которое будет предоставлено пакету в ```“Package name``` поле.**</span><span class="sxs-lookup"><span data-stu-id="d19e7-110">**Enter the name to be given your package in the ```“Package name``` field.**</span></span>

> [!Note]  
> <span data-ttu-id="d19e7-111">Введенное имя пакета и комбинация версий должны быть уникальными в организации.</span><span class="sxs-lookup"><span data-stu-id="d19e7-111">The package name and version combination entered must be unique within your organization.</span></span> <span data-ttu-id="d19e7-112">Эта проверка проверяется с помощью контрольного знака, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d19e7-112">This is validated by the checkmark as shown below.</span></span>
  
  - <span data-ttu-id="d19e7-113">Если вы решите повторно использовать имя пакета, номер версии должен быть уникальным (то есть никогда не использовался с таким именем).</span><span class="sxs-lookup"><span data-stu-id="d19e7-113">If you choose to re-use an package's name, then the version number must be unique (i.e. never been used with an package bearing that particular name).</span></span>
  - <span data-ttu-id="d19e7-114">Если сочетание имени пакета + версии не проходит проверку уникальности, вы увидите сообщение об ошибке, в котором говорится: "Пакет с этой версией пакета *уже существует".*</span><span class="sxs-lookup"><span data-stu-id="d19e7-114">If the combination of the package name + version does not pass the uniqueness check, you will see an error message which reads, *“Package with this package version already exists”*.</span></span> 

![Изображение для отправки инструкций по пакету](Media/Instructions.png)

2. <span data-ttu-id="d19e7-116">**Введите версию в поле "Пакетная версия".**</span><span class="sxs-lookup"><span data-stu-id="d19e7-116">**Enter a version in the “Package version” field.**</span></span>

![Версия пакета](Media/ApplicationVersion.png)

3.  <span data-ttu-id="d19e7-118">**Выберите тип теста, который необходимо выполнить в этом пакете**</span><span class="sxs-lookup"><span data-stu-id="d19e7-118">**Select the type of test you want to run on this package**</span></span>

    <span data-ttu-id="d19e7-119">Тест **Out-of-Box (OOB)** выполняет установку,   *запуск,* закрыть и удалить пакет. </span><span class="sxs-lookup"><span data-stu-id="d19e7-119">An **Out-of-Box (OOB)** test performs an *install*, *launch*, *close* and *uninstall* of your package.</span></span> <span data-ttu-id="d19e7-120">После установки процедура закрытия запуска повторяется 30 раз перед запуском единой системы.</span><span class="sxs-lookup"><span data-stu-id="d19e7-120">After the install, the launch-close routine is repeated 30 times before a single uninstall is run.</span></span> 
    
    <span data-ttu-id="d19e7-121">Этот тест OOB предоставляет стандартизированную телеметрию в пакете для сравнения Windows сборки.</span><span class="sxs-lookup"><span data-stu-id="d19e7-121">This OOB test provides you with standardized telemetry on your package to compare across Windows builds.</span></span>

    <span data-ttu-id="d19e7-122">Функциональный **тест** будет выполнять загруженный тестовый скрипт (s) в пакете.</span><span class="sxs-lookup"><span data-stu-id="d19e7-122">A **Functional test** would execute your uploaded test script(s) on your package.</span></span> <span data-ttu-id="d19e7-123">Сценарии выполняются в последовательности отправки, а сбой в конкретном скрипте остановит выполнение последующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="d19e7-123">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

> [!Note]
> <span data-ttu-id="d19e7-124">**Все** скрипты работают не более 80 минут.</span><span class="sxs-lookup"><span data-stu-id="d19e7-124">**All** scripts run for 80 minutes at the most.</span></span> 
    
4.  <span data-ttu-id="d19e7-125">**Выберите тип обновления ОС**</span><span class="sxs-lookup"><span data-stu-id="d19e7-125">**Select the OS update type**</span></span>

   - <span data-ttu-id="d19e7-126">"Обновления безопасности" позволяют протестировать пакет на фоне дополнительных отмывок Windows ежемесячных обновлений безопасности.</span><span class="sxs-lookup"><span data-stu-id="d19e7-126">The ‘Security updates’ enables your package to be tested against incremental churns of Windows pre-release monthly security updates.</span></span> 
   - <span data-ttu-id="d19e7-127">Обновления функций позволяют протестировать пакет на Windows двухлетки обновлений функций, которые будут создаваться из Windows insider Program.</span><span class="sxs-lookup"><span data-stu-id="d19e7-127">The ‘Feature updates’ enables your package to be tested against Windows pre-release bi-annual feature updates builds from the Windows Insider Program.</span></span>
<!---
Change to the correct picture
-->
![Тип обновления ОС](Media/OSUpdateType.png)

5.  <span data-ttu-id="d19e7-129">**Выберите версию ОС (s) для тестов обновления безопасности.**</span><span class="sxs-lookup"><span data-stu-id="d19e7-129">**Select the OS version(s) for Security update tests.**</span></span>

<span data-ttu-id="d19e7-130">В многофакторном отсеве выберите версию осмия (ы) Windows пакет будет установлен.</span><span class="sxs-lookup"><span data-stu-id="d19e7-130">In the multi-select dropdown, select the OS version(s) of Windows your package will be installed on.</span></span> 

  - <span data-ttu-id="d19e7-131">Чтобы проверить пакет только Windows клиентских OSes, выберите применимые Windows 11 версий ОС из списка меню.</span><span class="sxs-lookup"><span data-stu-id="d19e7-131">To test your package against Windows Client OSes only, select the applicable Windows 11 OS versions from the menu list.</span></span>
  - <span data-ttu-id="d19e7-132">Чтобы протестировать пакет только Windows серверных OSes, выберите применимые Windows версии ОС сервера из списка меню.</span><span class="sxs-lookup"><span data-stu-id="d19e7-132">To test your package against Windows Server OSes only, select the applicable Windows Server OS versions from the menu list.</span></span>
  - <span data-ttu-id="d19e7-133">Чтобы протестировать пакет Windows клиентских и серверных OSes, выберите все применимые OSes из списка меню.</span><span class="sxs-lookup"><span data-stu-id="d19e7-133">To test your package against Windows Client and Server OSes, select all applicable OSes from the menu list.</span></span> 

> [!Note]
> <span data-ttu-id="d19e7-134">Если вы выберете для проверки пакета как серверные, так и клиентские OSes, убедитесь, что пакет совместим и может работать на обоих OSes</span><span class="sxs-lookup"><span data-stu-id="d19e7-134">If you select to test your package against both Server and Client OSes, please make sure that the package is compatible and can run on both OSes</span></span>


![Выбор версии ОС](Media/OSVersion.png)
<!---
Change to the correct picture
-->
6.  <span data-ttu-id="d19e7-136">**Выберите параметры для тестов обновления функций:**</span><span class="sxs-lookup"><span data-stu-id="d19e7-136">**Select options for Feature update tests:**</span></span>

  - <span data-ttu-id="d19e7-137">В параметре "Выбор канала инсайдеров" выберите сборку, с которой необходимо ```Windows Insider Program Channel``` протестировать пакеты.</span><span class="sxs-lookup"><span data-stu-id="d19e7-137">On the option to “Select Insider Channel”, select the ```Windows Insider Program Channel``` as the build which your packages should be tested against.</span></span>
  
    <span data-ttu-id="d19e7-138">В настоящее время мы используем сборки, слетаемые в бета-канале insider.</span><span class="sxs-lookup"><span data-stu-id="d19e7-138">We currently use builds flighted in the Insider Beta Channel.</span></span>

  - <span data-ttu-id="d19e7-139">При выборе базовой версии ОС для Insight выберите Windows оси, которая будет использоваться в качестве базовой для сравнения результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="d19e7-139">On the option to “Select OS baseline for Insight”, select the Windows OS version to be used as a baseline in comparing your test results.</span></span> 

> [!Note]
> <span data-ttu-id="d19e7-140">В настоящее время мы не поддерживаем тестирование обновлений функций для OSes сервера</span><span class="sxs-lookup"><span data-stu-id="d19e7-140">We DO NOT support Feature update testing for Server OSes at this time</span></span>
<!---
Note to actual note format for markdown
-->
<!---
Change to the correct picture
-->
![Тестирование обновления функций](Media/FeatureUpdate.png)

7.  <span data-ttu-id="d19e7-142">Завершенная страница сведений о тесте должна выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="d19e7-142">A completed Test details page should look like this:</span></span> 

![Просмотр сведений о тесте](Media/TestDetails.png)
## <a name="next-steps"></a><span data-ttu-id="d19e7-144">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="d19e7-144">Next steps</span></span>

<span data-ttu-id="d19e7-145">В следующей статье описывается отправка ваших binaries в нашу serivce.</span><span class="sxs-lookup"><span data-stu-id="d19e7-145">Our next article covers Uploading your Binaries to our serivce.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d19e7-146">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="d19e7-146">Next step</span></span>](binaries.md)

<!---
Add button for next page
-->

