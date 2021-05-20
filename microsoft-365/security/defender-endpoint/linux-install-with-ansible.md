---
title: Развертывание Microsoft Defender для конечной точки на Linux с Ansible
ms.reviewer: ''
description: Описывает, как развернуть Microsoft Defender для конечной точки на Linux с помощью Ansible.
keywords: Microsoft, защитник, Microsoft Defender для Конечной точки, Linux, установка, развертывание, удаление, марионетка, аноскоп, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572733"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="50cbf-104">Развертывание Microsoft Defender для конечной точки на Linux с Ansible</span><span class="sxs-lookup"><span data-stu-id="50cbf-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50cbf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="50cbf-105">**Applies to:**</span></span>
- [<span data-ttu-id="50cbf-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="50cbf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="50cbf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50cbf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50cbf-108">Хотите испытать Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="50cbf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="50cbf-109">Подпишитесь на бесплатную пробную версию.</span><span class="sxs-lookup"><span data-stu-id="50cbf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="50cbf-110">В этой статье описывается, как развернуть Defender for Endpoint на Linux с помощью Ansible.</span><span class="sxs-lookup"><span data-stu-id="50cbf-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="50cbf-111">Успешное развертывание требует выполнения всех следующих задач:</span><span class="sxs-lookup"><span data-stu-id="50cbf-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="50cbf-112">Скачать бортовой пакет</span><span class="sxs-lookup"><span data-stu-id="50cbf-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="50cbf-113">Создание файлов Ansible YAML</span><span class="sxs-lookup"><span data-stu-id="50cbf-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="50cbf-114">Развертывание</span><span class="sxs-lookup"><span data-stu-id="50cbf-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="50cbf-115">References</span><span class="sxs-lookup"><span data-stu-id="50cbf-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="50cbf-116">Предпосылки и системные требования</span><span class="sxs-lookup"><span data-stu-id="50cbf-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="50cbf-117">Перед началом работы с основным [защитником конечной точки на странице Linux](microsoft-defender-endpoint-linux.md) можно получить описание предпосылок и системных требований к текущей версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="50cbf-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="50cbf-118">Кроме того, для развертывания Ansible необходимо ознакомиться с задачами управления Ansible, настроить Ansible и знать, как развертывать игровые игры и задачи.</span><span class="sxs-lookup"><span data-stu-id="50cbf-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="50cbf-119">Ansible имеет много способов для выполнения той же задачи.</span><span class="sxs-lookup"><span data-stu-id="50cbf-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="50cbf-120">Эти инструкции предполагают наличие поддерживаемых модулей Ansible, таких как *apt* *и unarchive* для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="50cbf-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="50cbf-121">Организация может использовать другой рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="50cbf-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="50cbf-122">Для получения [подробной информации обратитесь к документации Ansible.](https://docs.ansible.com/)</span><span class="sxs-lookup"><span data-stu-id="50cbf-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="50cbf-123">Ansible должен быть установлен по крайней мере на одном компьютере (Ansible называет это узел управления).</span><span class="sxs-lookup"><span data-stu-id="50cbf-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="50cbf-124">SSH должен быть настроен для учетной записи администратора между узлом управления и всеми управляемыми узлами (устройства, на которых будет установлен Defender for Endpoint), и рекомендуется настроить его с помощью общедоступной проверки подлинности ключей.</span><span class="sxs-lookup"><span data-stu-id="50cbf-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="50cbf-125">Следующее программное обеспечение должно быть установлено на всех управляемых узлах:</span><span class="sxs-lookup"><span data-stu-id="50cbf-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="50cbf-126">локон</span><span class="sxs-lookup"><span data-stu-id="50cbf-126">curl</span></span>
  - <span data-ttu-id="50cbf-127">питон-apt</span><span class="sxs-lookup"><span data-stu-id="50cbf-127">python-apt</span></span>

- <span data-ttu-id="50cbf-128">Все управляемые узлы должны быть перечислены в следующем формате в соответствующем `/etc/ansible/hosts` файле:</span><span class="sxs-lookup"><span data-stu-id="50cbf-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="50cbf-129">Пинг-тест:</span><span class="sxs-lookup"><span data-stu-id="50cbf-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="50cbf-130">Скачать бортовой пакет</span><span class="sxs-lookup"><span data-stu-id="50cbf-130">Download the onboarding package</span></span>

<span data-ttu-id="50cbf-131">Загрузите бортовой пакет из Центр безопасности в Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="50cbf-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="50cbf-132">В Центр безопасности в Microsoft Defender, перейдите **на Параметры > управления устройствами > борту**.</span><span class="sxs-lookup"><span data-stu-id="50cbf-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="50cbf-133">В первом меню для высадки выберите **Linux Server в** качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="50cbf-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="50cbf-134">Во втором меню для высадки выберите **предпочтительный инструмент управления конфигурацией Linux** в качестве метода развертывания.</span><span class="sxs-lookup"><span data-stu-id="50cbf-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="50cbf-135">Выберите **Скачать бортовой пакет**.</span><span class="sxs-lookup"><span data-stu-id="50cbf-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="50cbf-136">Сохраните файл в WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="50cbf-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Центр безопасности в Microsoft Defender скриншот](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="50cbf-138">Из подсказки команды убедитесь, что у вас есть файл.</span><span class="sxs-lookup"><span data-stu-id="50cbf-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="50cbf-139">Извлекайте содержимое архива:</span><span class="sxs-lookup"><span data-stu-id="50cbf-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="50cbf-140">Создание файлов Ansible YAML</span><span class="sxs-lookup"><span data-stu-id="50cbf-140">Create Ansible YAML files</span></span>

<span data-ttu-id="50cbf-141">Создайте подзапись или файлы ролевых игр, которые вносят свой вклад в воспроизведение или задачу.</span><span class="sxs-lookup"><span data-stu-id="50cbf-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="50cbf-142">Создайте бортовое `onboarding_setup.yml` задание:</span><span class="sxs-lookup"><span data-stu-id="50cbf-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="50cbf-143">Добавьте репозиторий Defender for Endpoint и `add_apt_repo.yml` ключ:</span><span class="sxs-lookup"><span data-stu-id="50cbf-143">Add the Defender for Endpoint repository and key, `add_apt_repo.yml`:</span></span>

    <span data-ttu-id="50cbf-144">Защитник для Конечной точки на Linux может быть развернут из одного из следующих каналов (обозначенных ниже *как «канал»):* *инсайдеры-быстрые,* *инсайдеры-медленные,* *или prod*. Каждый из этих каналов соответствует репозиторию программного обеспечения Linux.</span><span class="sxs-lookup"><span data-stu-id="50cbf-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="50cbf-145">Выбор канала определяет тип и частоту обновлений, которые предлагаются вашему устройству.</span><span class="sxs-lookup"><span data-stu-id="50cbf-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="50cbf-146">Устройства в *инсайдеры-быстрые* являются первыми, чтобы получить обновления и новые функции, а затем *инсайдеры медленно* и, наконец, *prod*.</span><span class="sxs-lookup"><span data-stu-id="50cbf-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="50cbf-147">Для того, чтобы просмотреть новые функции и обеспечить раннюю обратную связь, рекомендуется настроить некоторые устройства на предприятии, чтобы использовать либо *инсайдеров быстро* *или инсайдеров медленно*.</span><span class="sxs-lookup"><span data-stu-id="50cbf-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="50cbf-148">Переключение канала после первоначальной установки требует переустановки продукта.</span><span class="sxs-lookup"><span data-stu-id="50cbf-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="50cbf-149">Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство, чтобы использовать новый канал, и следуйте шагам в этом документе, чтобы установить пакет из нового местоположения.</span><span class="sxs-lookup"><span data-stu-id="50cbf-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="50cbf-150">Обратите внимание на дистрибутив и версию и определите ближайшую запись для него под `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="50cbf-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="50cbf-151">В следующих командах *замените «дистро»* *и «версию»* информацией, которую вы определили.</span><span class="sxs-lookup"><span data-stu-id="50cbf-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50cbf-152">В случае Oracle Linux *замените «дистрибутив»* на «rhel».</span><span class="sxs-lookup"><span data-stu-id="50cbf-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="50cbf-153">Создайте Ansible и удалите файлы YAML.</span><span class="sxs-lookup"><span data-stu-id="50cbf-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="50cbf-154">Для дистрибутивов на основе apt используйте следующий файл YAML:</span><span class="sxs-lookup"><span data-stu-id="50cbf-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="50cbf-155">Для дистрибутивов на основе dnf используйте следующий файл YAML:</span><span class="sxs-lookup"><span data-stu-id="50cbf-155">For dnf-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="50cbf-156">Развертывание</span><span class="sxs-lookup"><span data-stu-id="50cbf-156">Deployment</span></span>

<span data-ttu-id="50cbf-157">Теперь запустите файлы задач под `/etc/ansible/playbooks/` соответствующим каталогом.</span><span class="sxs-lookup"><span data-stu-id="50cbf-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="50cbf-158">установка:</span><span class="sxs-lookup"><span data-stu-id="50cbf-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="50cbf-159">Когда продукт запускается в первый раз, он загружает последние определения противомамальных программ.</span><span class="sxs-lookup"><span data-stu-id="50cbf-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="50cbf-160">В зависимости от подключения к Интернету это может занять до нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="50cbf-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="50cbf-161">Проверка/конфигурация:</span><span class="sxs-lookup"><span data-stu-id="50cbf-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="50cbf-162">Удаление:</span><span class="sxs-lookup"><span data-stu-id="50cbf-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="50cbf-163">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="50cbf-163">Log installation issues</span></span>

<span data-ttu-id="50cbf-164">Дополнительные [сведения о том,](linux-resources.md#log-installation-issues) как найти автоматически генерируемый журнал, созданный установщиком при ошибке, можно найти в журнале log.</span><span class="sxs-lookup"><span data-stu-id="50cbf-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="50cbf-165">Модернизация операционной системы</span><span class="sxs-lookup"><span data-stu-id="50cbf-165">Operating system upgrades</span></span>

<span data-ttu-id="50cbf-166">При обновлении операционной системы до новой основной версии, вы должны сначала удалить Защитник для конечной точки на Linux, установить обновление, и, наконец, перенастроить Защитник для конечной точки на Linux на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="50cbf-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="50cbf-167">Ссылки</span><span class="sxs-lookup"><span data-stu-id="50cbf-167">References</span></span>

- [<span data-ttu-id="50cbf-168">Добавление или удаление репозиториев YUM</span><span class="sxs-lookup"><span data-stu-id="50cbf-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="50cbf-169">Управление пакетами с менеджером пакета dnf</span><span class="sxs-lookup"><span data-stu-id="50cbf-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="50cbf-170">Добавление и удаление репозиториев APT</span><span class="sxs-lookup"><span data-stu-id="50cbf-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="50cbf-171">Управление apt-пакетами</span><span class="sxs-lookup"><span data-stu-id="50cbf-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="50cbf-172">См. также</span><span class="sxs-lookup"><span data-stu-id="50cbf-172">See also</span></span>
- [<span data-ttu-id="50cbf-173">Исследование проблем работоспособности агента</span><span class="sxs-lookup"><span data-stu-id="50cbf-173">Investigate agent health issues</span></span>](health-status.md)
