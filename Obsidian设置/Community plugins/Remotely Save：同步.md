我没用过这个，一直用[[Git：同步|Git：同步]]进行同步。之前没有选择它主要是因为有一些功能要付费。不过今天稍微了解了下这个插件，感觉其实还可以，原因如下：

第一个是虽然Remotely Save支持的云存储服务基本都要付费，或者需要自己搭建服务器的间接成本，但一般云存储服务商提供的免费存储都要5~15G，对于个人笔记实际上完全够用。所以不一定需要付费

第二，我才知道云存储商一般都支持版本控制，webdav协议也支持。之前用Git有一个重要原因就是Git的版本控制功能，我以为其他方式不支持。而且配合Obsidian自带的[[Core plugins#6. File recovery|文件快照]]功能，通过remotely save支持的云储存实际也能实现接近Git的版本控制，虽然做不到Git那样极致

第三，Git插件同步的一个很大缺点是移动端支持性差，仓库稍微大一点就会导致程崩溃，基本没法用。目前解决方案是通过play商店中的gitsync这个软件进行同步，但似乎也不是很好用。而remotely save支持的云存储应该能解决这个问题

话说回来，我没用过remotely save，所以暂时没什么发言权，等之后用过再回来更新吧

下面是remotel save的设置项介绍（选择不同的云存储服务会有不同选项，这里以S3为例）

![[Pasted image 20250602095301.png]]


1. **Choose A Remote Service (选择远程服务):**
    
    - 此选项已预设为 "S3 or compatible"，表明配置目标是与 S3 协议兼容的存储服务。此类服务包括 Amazon Web Services (AWS) S3 本身，以及其他提供 S3 兼容接口的云存储，如 Cloudflare R2、Backblaze B2、腾讯云 COS、阿里云 OSS 或自建的 MinIO 服务等。
2. **Disclaimer (免责声明):**
    
    - 此部分声明插件非亚马逊官方出品。
    - 强调配置信息，特别是敏感凭证，将存储于本地设备。同时警示，本地设备上其他具有潜在风险的插件可能存在读取这些信息的风险。
    - 建议在检测到任何非预期访问时，应立即在相应的云服务提供商（AWS 或其他 S3 服务商）的账户设置中撤销或删除相关的访问密钥。
3. **Some Amazon S3 official docs for references (一些亚马逊 S3 官方文档参考):**
    
    - 此处提供了两个超链接，分别指向亚马逊官方关于 Endpoint 和 Region (终端节点和区域) 以及 Access Key ID 和 Secret Access Key (访问密钥 ID 和秘密访问密钥) 的说明文档，供用户查阅以获取更详细的官方解释。
4. **Endpoint (终端节点):**
    
    - **定义：** 指代 S3 服务 API 的网络访问地址 (URL)。不同的 S3 兼容服务提供商拥有各自独立的终端节点。对于 AWS S3，终端节点通常与特定区域关联，但也存在全局终端节点。
    - **填写内容：** 需要填入从所选 S3 服务提供商处获取的准确终端节点地址。例如，AWS S3 的典型格式为 `s3.<region>.amazonaws.com`，而其他服务商（如腾讯云 COS）则有其特定格式，例如 `cos.<Region>.myqcloud.com`。部分服务可能要求在地址前添加 `https://` 协议头。
5. **Region (区域):**
    
    - **定义：** 表示 S3 存储桶 (Bucket) 实际所在的地理位置或数据中心集群。例如 `us-east-1` (美国东部 - 弗吉尼亚北部)、`ap-northeast-1` (亚太 - 东京) 等。
    - **填写内容：** 需要指定存储桶创建时选定的区域代码。若不确定，插件提示可尝试 `us-east-1`，但此值并非通用，应以实际存储桶所在区域为准。正确的区域信息对连接成功及数据传输性能至关重要。
6. **Access Key ID (访问密钥 ID):**
    
    - **定义：** 身份验证凭证对中的公开部分，用于标识发起访问请求的账户或用户。
    - **填写内容：** 此处应填入从 S3 服务提供商处创建并获取的访问密钥 ID。插件会将其及其他配置信息保存在本地。
7. **Secret Access Key (秘密访问密钥):**
    
    - **定义：** 身份验证凭证对中的私密部分，与访问密钥 ID 配合使用，以验证访问权限。
    - **填写内容：** 此处应填入在创建访问密钥对时一同生成的秘密访问密钥。此密钥通常仅在创建时完整显示一次，因此需要用户妥善保管。插件同样会将其及其他配置信息保存在本地。该输入字段旁通常有关闭/显示输入内容的功能图标。
8. **Bucket Name (存储桶名称):**
    
    - **定义：** S3 中用于组织和存储对象的顶级容器，可类比为文件系统中的根目录。
    - **填写内容：** 需要输入已在 S3 服务上预先创建的、用于同步 Obsidian 笔记数据的存储桶的准确名称。存储桶名称在其服务范围内（如 AWS S3 的全局范围或特定服务商的范围）通常具有唯一性。若尚无可用存储桶，则需先通过服务商的管理控制台进行创建。

![[Pasted image 20250602095503.png]]

9. **S3 URL style (S3 URL 样式):**
    
    - **定义：** 此设置项决定插件在访问 S3 对象时使用的 URL 格式。
    - **选项：**
        - **Virtual Hosted-Style (default - 虚拟托管样式 - 默认):** 这种格式将存储桶名称作为主机名的一部分，例如 `https://<bucket-name>.s3.amazonaws.com/<key>`。这是 AWS S3 推荐和常用的样式。
        - **Path-Style (路径样式):** 这种格式将存储桶名称作为 URL 路径的一部分，例如 `https://s3.amazonaws.com/<bucket-name>/<key>`。对于某些较旧的 S3 实现或特定的 S3 兼容服务，可能需要或仅支持此样式。
    - **说明：** 通常情况下，保持默认的 "Virtual Hosted-Style" 即可，除非所连接的 S3 兼容服务明确要求使用路径样式。
10. **Parts Concurrency (分片并发数):**
    
    - **定义：** 此设置控制在上传大文件时，插件将文件分割成多少个小分片 (parts) 并行上传的最大数量。S3 的分片上传 (Multipart Upload) 功能允许将大文件分割成多个部分独立上传，以提高上传速度和可靠性。
    - **默认值：** 20。
    - **说明：** 增加并发数可能会提高大文件上传速度，但也可能消耗更多本地计算资源和网络带宽，并可能增加对 S3 服务的 API 请求频率。如果遇到上传问题或希望控制资源消耗，可以调整此数值。通常默认值适用于大多数情况。
11. **Use Accurate MTime (使用精确的修改时间):**
    
    - **定义：** 此选项决定插件是否尝试从 S3 端读取对象上传后的精确最后修改时间 (MTime)，以用于更精确的同步算法。
    - **选项：**
        - **Disable (禁用 - 默认):** 禁用此功能。
        - **Enable (启用):** 启用此功能。
    - **说明：** 启用此功能可以帮助插件更准确地判断文件是否需要同步，特别是在跨设备或跨时区操作时。然而，如插件说明所述，这会导致额外的 API 请求，从而可能增加同步所需的时间和潜在的费用（取决于 S3 服务提供商的计费策略）。如果对同步的精确性有极高要求，可以考虑启用，否则保持禁用以减少 API 调用。
12. **Change The Remote Prefix (experimental - 更改远程前缀 - 实验性功能):**
    
    - **定义：** 此实验性功能允许用户更改在 S3 存储桶中存储笔记文件的远程路径前缀。
    - **默认行为：** 默认情况下，文件直接保存在存储桶的根目录下（或者根据 "Bucket Name" 字段指定的路径下，如果该字段本身就包含了前缀）。
    - **如何使用：** 在此输入框中输入期望的远程前缀路径（例如 `notes/` 或 `myobsidian/vault/`）。如果将输入框留空并点击 "Confirm" (确认)，则会重置为默认行为（无额外前缀）。
    - **说明：** 这是一个实验性功能，使用时应注意其潜在影响。它允许用户将 Obsidian 仓库的文件组织到存储桶内的特定子目录中。
13. **S3 Reverse Proxy (No Sign) Url (experimental - S3 反向代理 (无签名) URL - 实验性功能):**
    
    - **定义：** 此实验性功能用于配置一个反向代理 URL，该 URL 用于访问 S3 对象，但插件不会对通过此 URL 的请求进行标准的 AWS 签名。
    - **适用场景：** 当用户通过一个自定义的反向代理访问 S3 存储桶，并且该反向代理本身负责处理身份验证和授权，或者访问的是公开内容，不需要原始 AWS 签名时，此设置可能有用。
    - **如何使用：** 输入反向代理的 URL。插件说明提示不要包含 `http(s)://` 前缀。如果不需要此功能，则将此字段留空。
    - **警告：** 这是一个高级且实验性的功能，普通用户通常不需要配置此项。不正确的配置可能导致安全风险或连接失败。
14. **Generate Folder Object Or Not (是否生成文件夹对象):**
    
    - **定义：** 此选项控制插件在同步时是否为文件夹在 S3 中显式创建一个零字节的对象来代表该文件夹。
    - **背景：** S3 本质上是一个扁平的对象存储系统，没有传统文件系统意义上的“真实”文件夹。文件夹的概念通常是通过对象键名中的 `/` 来模拟的。
    - **选项：**
        - **Not generate (default - 不生成 - 默认):** 插件在新版本中默认跳过生成代表文件夹的零字节对象。
        - **Generate (生成):** 如果选择此项（或使用的是旧版本插件的逻辑），插件会创建一个以 `/` 结尾的零字节对象来表示一个文件夹。
    - **说明：** 某些 S3 浏览器或工具可能依赖于这种零字节文件夹对象来正确显示文件夹结构。但对于大多数现代 S3 应用和 `Remotely Save` 插件的当前同步逻辑，通常不需要显式创建这些文件夹对象。保持默认设置通常是合适的。
15. **Check Connectivity (检查连接性):**
    
    - **按钮功能：** 点击 "Check" (检查) 按钮，插件会尝试使用当前配置的参数连接到指定的 S3 服务。
    - **目的：** 用于验证所填写的 Endpoint、Region、Access Keys、Bucket Name 等信息是否正确，以及网络是否通畅，插件是否能够成功与 S3 服务建立通信。
    - **反馈：** 插件通常会给出连接成功或失败的提示。

![[Pasted image 20250602095553.png]]

16. **Encryption Password (加密密码):**
    
    - **定义：** 此设置项用于配置端到端加密 (E2E encryption) 的密码。如果设置了密码，文件在上传到远程服务器之前会在本地进行加密。
    - **填写内容：** 输入用于加密和解密的密码。如果留空，则表示不启用加密。设置或更改密码后，需要点击 "Confirm" (确认) 按钮。
    - **重要提示：** 插件明确指出，密码和其他信息保存在本地。更改密码后，需要手动删除远程位置的所有文件，并重新同步以上传加密后的文件。如果忘记此密码，加密的文件将无法恢复。
    - 输入框旁边的眼睛图标通常表示可以点击来显示或隐藏输入的密码内容。
17. **Schedule For Auto Run (自动运行计划):**
    
    - **定义：** 此选项允许用户设置一个自动同步的计划。插件会尝试在每个设定的时间间隔后运行同步。
    - **设置方式：** 点击下拉菜单选择预设的时间间隔（例如，每30分钟，每小时等），或选择 "not set" (未设置) 以禁用基于计划的自动运行。
    - **提示：** 插件说明提到，自动运行可能会影响设备的电池续航。
18. **Run Once On Start Up Automatically (启动时自动运行一次):**
    
    - **定义：** 此设置项控制插件是否在 Obsidian 启动时自动执行一次同步操作。
    - **设置方式：** 点击下拉菜单选择 "Enable" (启用) 或 "not set" (未设置，即禁用)。
    - **与“自动运行计划”的区别：** 此设置是在 Obsidian 启动时触发一次同步，而“自动运行计划”是根据设定的时间间隔周期性地触发同步。
19. **Sync On Save (experimental - 保存时同步 - 实验性功能):**
    
    - **定义：** 这是一个实验性功能，启用后，当用户修改并保存文件时，插件会尝试触发一次同步。
    - **选项：**
        - **Disable (default - 禁用 - 默认):** 禁用此功能。
        - **Enable (启用):** 启用此功能。
    - **说明：** 此功能可以更即时地将更改同步到远程服务器，但由于是实验性的，可能存在不稳定的情况或导致频繁的同步操作。
20. **Skip Large Files (跳过大文件):**
    
    - **定义：** 此设置允许用户定义一个文件大小阈值，超过此阈值的文件将在同步过程中被跳过。
    - **设置方式：** 输入文件大小的阈值。插件说明中提到 "Here 1 MB = 10^6 bytes" (此处 1MB 等于 10^6 字节)。如果选择 "not set" (未设置) 或输入0，则表示不跳过任何文件（除非有其他同步服务的限制）。
    - **目的：** 用于避免同步非常大的文件，这些文件可能会消耗大量时间和带宽，或者超出某些云服务的限制。
21. **Show Last Successful Sync In Status Bar (在状态栏显示上次成功同步时间):**
    
    - **定义：** 启用此选项后，插件会在 Obsidian 的状态栏显示上一次成功同步的时间。
    - **开关：** 通过拨动开关来启用或禁用此功能。
22. **Reset Last Successful Sync Time (重置上次成功同步时间):**
    
    - **按钮功能：** 点击 "Reset" (重置) 按钮，会清除插件记录的上次成功同步的时间戳。
    - **用途：** 在某些特殊情况下，例如手动更改了远程文件或解决了冲突后，可能需要重置此时间，以确保插件在下次同步时能正确评估文件状态。
23. **Regex Of Paths To Ignore (要忽略的路径的正则表达式):**
    
    - **定义：** 此区域允许用户定义一系列正则表达式，用于匹配不想被同步的文件夹或文件的路径。
    - **规则：** 每行一个正则表达式。路径是相对于仓库根目录的，且不包含开头的斜杠。插件说明提到，非空路径和非空忽略路径会一起生效。
    - **用途：** 可以用来排除特定的文件夹（如包含缓存文件、临时文件或高度敏感信息且不希望上传的文件夹）或特定类型的文件。
24. **Regex Of Paths To Allow (允许的路径的正则表达式):**
    
    - **定义：** 此区域允许用户定义一系列正则表达式，用于匹配_只_希望被同步的文件夹或文件的路径。
    - **规则：** 每行一个正则表达式。路径是相对于仓库根目录的，且不包含开头的斜杠。
    - **行为：** 如果此设置不为空，则只有匹配这些正则表达式的路径才会被同步，包括 `.obsidian` 配置文件目录（除非 `.obsidian` 目录被明确地通过忽略规则排除，或者此允许规则没有包含它）。如果此设置为空，则默认同步所有未被忽略规则排除的文件和文件夹。插件说明提到，非空允许路径和非空忽略路径会一起生效（即，文件必须同时满足允许规则且不满足忽略规则才会被同步）。
    - **用途：** 用于更精细地控制只同步仓库中的特定部分内容。

![[Pasted image 20250602095712.png]]

25. **Concurrency (并发数):**
    
    - **定义：** 此设置项用于控制在下载或上传文件时，插件最多可以并行处理多少个文件。
    - **默认值：** 5。
    - **说明：** 较高的并发数可能会加快同步速度，尤其是在有大量小文件时。但插件也提示，如果遇到诸如速率限制（某些云服务对API请求频率有限制）之类的问题，可以尝试降低此并发数值。
26. **Sync _ Files Or Folders (同步以下划线开头的文件或文件夹):**
    
    - **定义：** 此选项决定是否同步那些名称以下划线 (`_`) 开头的文件或文件夹。
    - **选项：**
        - **Disable (禁用 - 默认):** 禁用后，名称以下划线开头的文件或文件夹将不会被同步。
        - **Enable (启用):** 启用后，这些文件或文件夹也将被同步。
    - **说明：** 在某些约定中，以下划线开头的文件或文件夹可能被视为私有或临时的，此选项提供了是否包含它们到同步范围的控制。
27. **Sync Config Dir (experimental - 同步配置目录 - 实验性功能):**
    
    - **定义：** 此实验性功能用于控制是否同步 Obsidian 仓库的配置目录（通常是 `.obsidian` 文件夹）。此目录包含了 Obsidian 的设置、插件、主题、工作区布局等信息。
    - **选项：**
        - **Disable (禁用 - 默认):** 禁用后，`.obsidian` 目录（以及内部的 `inner folder .git` 和 `node_modules`，如果存在）将被忽略。
        - **Enable (启用):** 启用后，`.obsidian` 目录将被同步。
    - **警告：** 插件明确提示，启用此选项可能会影响所有插件或 Obsidian 的设置，并且可能需要在 Obsidian 重启后才能生效。用户需要自行承担启用此功能的风险。
28. **Sync Bookmarks (experimental - 同步书签 - 实验性功能):**
    
    - **定义：** 此实验性功能控制是否同步 Obsidian 的书签文件（通常是 `.obsidian/bookmarks.json`）。
    - **选项：**
        - **Disable (禁用 - 默认):** 禁用后，书签文件将根据 "Sync Config Dir" 的设置来决定是否同步（如果 "Sync Config Dir" 被禁用，书签也不会同步）。
        - **Enable (启用):** 启用后，即使 "Sync Config Dir" 被禁用，书签文件 (`.obsidian/bookmarks.json`) 也会被单独同步。如果 "Sync Config Dir" 本身就是启用的，则此选项将被忽略并视为启用状态。
29. **Deletion Destination (删除目标):**
    
    - **定义：** 此设置项决定当插件在同步过程中需要删除文件时，这些文件应被如何处理。
    - **选项：**
        - **system trash (default - 系统回收站 - 默认):** 删除的文件将被移至操作系统的回收站。
        - **obsidian trash (.trash folder - Obsidian 回收站):** 删除的文件将被移至 Obsidian 仓库内的 `.trash` 文件夹。
        - **permanently delete (永久删除):** 文件将被直接永久删除，无法从回收站恢复。
    - **说明：** 选择合适的删除目标有助于防止意外永久删除重要文件。
30. **Action For Conflict (冲突处理行为):**
    
    - **定义：** 当一个文件自上次更新以来在本地和远程都被修改过，就会发生冲突。此设置决定插件如何处理这种情况。
    - **选项：**
        - **newer version survives (default - 新版本保留 - 默认):** 保留最后修改时间较新的那个版本的文件。
        - **local version survives (本地版本保留):** 无论修改时间如何，始终保留本地版本。
        - **remote version survives (远程版本保留):** 无论修改时间如何，始终保留远程版本。
        - **generate duplicated files (生成重复文件):** 保留两个版本的文件，通常会在其中一个文件名后附加标识以示区别（例如，通过智能冲突功能）。
    - **适用范围：** 插件说明提到此功能仅对双向同步 (bidirectional sync) 有效。
31. **Clear Duplicated Files By Smart Conflict (通过智能冲突清理重复文件):**
    
    - **按钮功能：** "Start Scanning" (开始扫描)。
    - **定义：** 如果用户之前使用过智能冲突解决功能（可能导致生成了重复文件，例如文件名后带有特定冲突标记），此功能允许用户扫描并清理这些由插件生成的重复文件。
    - **警告：** 插件强烈提示用户，**在确定重复文件不再需要之后**，才可以使用此功能清除它们。
32. **Abort Sync If Modification Above Percentage (当修改超过百分比时中止同步):**
    
    - **定义：** 此设置提供了一种安全机制，如果检测到将要被删除或修改的文件数量超过了仓库总文件数的某个百分比，则中止同步操作。
    - **默认值：** 50 (即 50%)。
    - **设置范围：** 可以设置为 0 到 100 之间的值。设置为 100 表示禁用此保护（除非所有文件都被修改/删除）。设置为 0 则表示始终阻止同步（这通常不是期望的行为，除非用于特殊测试）。
    - **目的：** 用于防止因意外操作或配置错误导致大量文件被意外删除或更改。
33. **Sync Direction (experimental - 同步方向 - 实验性功能):**
    
    - **定义：** 此实验性功能允许用户选择同步操作的方向。
    - **选项：**
        - **Bidirectional (default - 双向 - 默认):**
            1. **双向推送：** 本地的更改（新增、修改）同步到远程。
            2. **双向拉取：** 远程的更改（新增、修改）同步到本地。
            3. **增量推送和删除：** 本地创建或修改的文件复制到远程，本地删除的操作也会在远程执行。
            4. **增量拉取和删除：** 远程创建或修改的文件复制到本地，远程删除的操作也会在本地执行。
        - **Incremental Push:** 仅将本地创建或修改的文件复制到远程。
        - **Incremental Pull:** 仅将远程创建或修改的文件复制到本地。
    - **警告：** 插件提示用户注意，选择非双向同步时，只有基于时间和大小判断出的**已更改**文件才会被复制。此为实验性功能，需谨慎选择。

![[Pasted image 20250602095823.png]]

34. **Import and Export Partial Settings (导入和导出部分设置):**
    
    - **整体目的：** 此区域的功能是允许用户导出当前 `Remotely Save` 插件的特定配置部分，或导入之前导出的配置。这对于在不同设备间迁移设置、备份特定服务配置或与他人共享配置非常有用。
35. **Export (导出):**
    
    - **定义：** 此部分用于将插件的设置导出为二维码 (QR code) 或统一资源标识符 (URI)。
    - **功能：** 通过点击右侧的一系列按钮，可以选择导出不同部分的配置：
        - **Export Basic And Advanced Part (导出基础和高级部分):** 导出“基础设置”和“高级设置”部分的配置信息。
        - **Export S3 Part (导出 S3 部分):** 导出与 Amazon S3 或兼容 S3 服务相关的配置信息（如 Endpoint, Region, Access Keys, Bucket Name 以及 S3 特有的高级设置）。
        - **Export Dropbox Part (导出 Dropbox 部分):** 导出与 Dropbox 服务相关的配置信息。
        - **Export OneDrive (App Folder) Part (导出 OneDrive (应用文件夹) 部分):** 导出与 OneDrive (应用文件夹模式) 相关的配置信息。
        - **Export OneDrive (Full) Part (导出 OneDrive (完整模式) 部分):** 导出与 OneDrive (完整访问模式) 相关的配置信息。
        - **Export Webdav Part (导出 Webdav 部分):** 导出与 WebDAV 服务相关的配置信息。
        - **Export Webdis Part (导出 Webdis 部分):** 导出与 Webdis 服务（通过 HTTP 提供 Redis 接口的服务）相关的配置信息。
        - **Export Google Drive Part (导出 Google Drive 部分):** 导出与 Google Drive 服务相关的配置信息。
        - **Export Box Part (导出 Box 部分):** 导出与 Box 服务相关的配置信息。
        - **Export pCloud Part (导出 pCloud 部分):** 导出与 pCloud 服务相关的配置信息。
        - **Export Yandex Disk Part (导出 Yandex Disk 部分):** 导出与 Yandex Disk 服务相关的配置信息。
        - **Export Koofr Part (导出 Koofr 部分):** 导出与 Koofr 服务相关的配置信息。
        - **Export Azure Blob Storage Part (导出 Azure Blob Storage 部分):** 导出与 Azure Blob Storage 服务相关的配置信息。
    - **操作流程：** 点击相应的导出按钮后，插件通常会生成一个包含配置信息的二维码图像和一个 URI 字符串。用户可以扫描二维码或复制 URI 以便后续导入。
36. **Import (导入):**
    
    - **定义：** 此部分用于导入之前通过上述导出功能生成的配置。
    - **操作流程：**
        - **通过 URI 导入：** 将导出的 URI 字符串粘贴到 `obsidian://remotely-save?` 后面的输入框中。
        - **通过二维码导入：** 用户也可以使用支持扫描二维码的设备或应用扫描导出的二维码，扫描结果通常是一个 URI，然后可以按上述方式粘贴。或者，插件本身可能集成了通过摄像头扫描二维码的功能（具体取决于插件版本和 Obsidian 环境）。
        - **确认导入：** 粘贴 URI 后，点击 "Confirm" (确认) 按钮，插件会尝试解析 URI 并应用其中包含的配置设置。
    - **说明：** 导入配置会覆盖当前对应的设置项。例如，如果导入的是 "S3 Part" 的配置，则插件中当前的 S3 相关设置将被导入的配置所替代。

![[Pasted image 20250602095919.png]]

37. **Account (for PRO features) (账户 - 用于专业版功能):**
    
    - **核心信息：** 此部分说明了 `Remotely Save` 插件的基础功能是免费的，并且不需要用户创建账户。
    - **PRO 功能说明：** 然而，要使用插件的某些“PRO (专业版)”功能，例如“智能冲突 (smart conflict)”处理等，则需要用户拥有一个在线账户并为此付费。
    - **账户注册/登录流程概述：**
        - **第一步：** 用户需要点击提供的按钮或链接（`https://remotelysave.com`）跳转到 `Remotely Save` 的官方网站进行注册或登录。插件特别指出，这个账户与 Obsidian 官方账户是不同的，并且两者之间没有关联。
        - **第二步：** 在网站上注册并登录账户后，用户需要将本地设备上的插件与这个在线账户进行“连接 (connect)”。
38. **Remotely Save Online Account (Remotely Save 在线账户):**
    
    - **按钮：** "Sign Up / Sign In" (注册 / 登录)。
    - **功能：** 点击此按钮会引导用户跳转到 `Remotely Save` 插件的官方网站，以便用户可以在该网站上创建新账户或登录已有账户。
39. **Connect (连接):**
    
    - **说明文本：** “在您注册并登录网站上的账户后，您需要在此处将您的插件连接到在线账户。请点击按钮进行连接。” (After you sign up and sign in the account on the website, you need to connect your plugin here to the online account. Please click the button to connect.)
    - **按钮：** "Connect" (连接)。
    - **功能：** 当用户已经在 `Remotely Save` 官方网站上成功登录账户后，返回到 Obsidian 插件的此设置界面，点击此 "Connect" 按钮，插件会尝试与用户的在线账户建立连接。成功连接后，付费的 PRO 功能（如果用户已订阅）才会在插件中解锁和激活。

![[Pasted image 20250602100008.png]]

40. **Debug (调试):**
    
    - **整体目的：** 此区域包含一系列用于问题排查、获取详细同步信息、管理插件内部数据以及性能分析的工具和选项。
41. **Alter Notice Level (更改通知级别):**
    
    - **定义：** 此设置项用于调整插件在同步过程中输出信息的详细程度。
    - **选项：**
        - **info (默认):** 默认级别，提供常规的同步信息。
        - **debug:** 调试级别，会输出更详尽、更冗长的同步过程信息，有助于开发者或用户诊断问题。
    - **说明：** 当遇到同步问题时，将通知级别更改为 "debug" 可以获取更多上下文信息。
42. **Output Current Settings From Disk To Console (将当前磁盘设置输出到控制台):**
    
    - **按钮：** "Output" (输出)。
    - **功能：** 插件的设置保存在磁盘上，并且可能是经过编码的。点击此按钮会将当前保存在磁盘上的设置解码后输出到 Obsidian 的开发者控制台中。
    - **用途：** 用于查看插件实际加载和使用的原始配置数据，有助于调试配置相关的问题。
43. **Obfuscate The Setting File Or Not (是否混淆设置文件):**
    
    - **定义：** 此选项决定插件的设置文件 (`data.json`) 是否进行混淆处理。
    - **选项：**
        - **Enable (启用 - 默认):** 启用混淆。
        - **Disable (禁用):** 禁用混淆。
    - **说明：** 设置文件中可能包含敏感信息（如 API 密钥）。插件强烈建议启用混淆以避免意外读取和修改。如果用户确定需要直接查看或手动编辑未混淆的设置文件，可以禁用此选项，但需自行承担风险。
44. **View Console Log (查看控制台日志):**
    
    - **说明：** 此部分提供了查看插件日志的指引。
        - **桌面端：** 用户可以按 `Ctrl+Shift+I` (Windows/Linux) 或 `Cmd+Option+I` (macOS) 打开开发者工具来查看控制台日志。
        - **移动端：** 插件建议安装第三方插件 `Logstravaganza` 以便将控制台日志导出到一个笔记中进行查看。
45. **Export Sync Plans (导出同步计划):**
    
    - **定义：** 同步计划是在每次触发同步之后、实际执行同步之前创建的。它记录了插件计划如何处理文件（哪些文件将被上传、下载或删除等）。
    - **按钮功能：**
        - **Export latest 1 (change part) (导出最近1次的变更部分):** 导出最近一次同步计划中涉及变更的部分。
        - **Export latest 5 (change part) (导出最近5次的变更部分):** 导出最近五次同步计划中涉及变更的部分。
        - **Export latest 1 (导出最近1次):** 导出最近一次完整的同步计划。
        - **Export latest 5 (导出最近5次):** 导出最近五次完整的同步计划。
        - **Export All (全部导出):** 导出所有存储的同步计划。
    - **用途：** 有助于了解在特定同步操作中，插件具体打算执行哪些操作，对于分析同步行为非常有用。
46. **Delete Sync Plans History In DB (删除数据库中的同步计划历史):**
    
    - **按钮：** "Delete Sync Plans History" (删除同步计划历史)。
    - **功能：** 点击此按钮会删除插件数据库中存储的所有同步计划历史记录。
47. **Delete Prev Sync Details In DB (删除数据库中的先前同步详情):**
    
    - **定义：** 同步算法会将上一次的同步信息保存在数据库中，以判断文件的变更情况。
    - **按钮：** "Delete Prev Sync Details" (删除先前同步详情)。
    - **功能：** 点击此按钮会删除这些先前同步的详细信息。这样做会导致插件在下一次同步时将所有文件视为新创建的文件进行处理。
    - **用途：** 在某些特殊情况下，例如需要强制重新全面比对所有文件时，可以使用此功能。
48. **Export Profiler Results (导出分析器结果):**
    
    - **定义：** 插件的分析器 (Profiler) 会记录同步过程中各个步骤所花费的时间。
    - **按钮：** "Export All" (全部导出)。
    - **功能：** 点击此按钮可以将这些性能分析数据导出，以便用户了解哪个同步步骤比较耗时。
49. **Enable Profiler (启用分析器):**
    
    - **定义：** 此选项决定是否收集插件同步过程中的性能数据。
    - **选项：**
        - **Disable (禁用 - 默认):** 禁用分析器。
        - **Enable (启用):** 启用分析器。
    - **说明：** 启用分析器后，插件才会记录各步骤的耗时，之后才能导出分析结果。这对于诊断同步缓慢的问题可能有所帮助。

![[Pasted image 20250602100105.png]]

50. **Enable Profiler Printing (启用分析器打印):**
    
    - **定义：** 此选项决定是否在每次（分析器）插入操作时将分析器结果打印到开发者控制台。
    - **选项：**
        - **Disable (禁用 - 默认):** 不在控制台打印每次插入的分析器结果。
        - **Enable (启用):** 在控制台打印每次插入的分析器结果。
    - **说明：** 当启用分析器 ("Enable Profiler") 后，此选项可以提供更实时的性能数据反馈到控制台，但可能会产生大量日志信息。
51. **Enable Profiler Recording Size (启用分析器记录大小):**
    
    - **定义：** 此选项决定分析器 (Profiler) 是否记录对象的大小。
    - **选项：**
        - **Disable (禁用 - 默认):** 分析器不记录对象大小。
        - **Enable (启用):** 分析器记录对象大小。
    - **说明：** 记录对象大小可以为性能分析提供更多维度的数据，例如分析大对象的处理时间。
52. **Output Vault Base Path And Randomly Assigned ID (输出仓库基础路径和随机分配的ID):**
    
    - **按钮：** "Output" (输出)。
    - **功能：** 点击此按钮会将当前 Obsidian 仓库的基础路径以及插件为该仓库随机分配的一个内部ID输出到开发者控制台。
    - **用途：** 主要用于调试目的，帮助开发者或高级用户识别特定仓库及其在插件内部的标识符。
53. **Reset Local Internal Cache/Databases (重置本地内部缓存/数据库):**
    
    - **按钮：** "Reset" (重置)。
    - **功能：** 点击此按钮会重置插件在本地存储的内部缓存和数据库。这些缓存/数据库可能包含同步状态、文件索引等临时或辅助数据。
    - **重要提示：** 插件说明指出，重置此项后需要重新加载插件 (reload the plugin)。同时强调，此选项**不会**清空核心的远程服务配置信息（例如 S3 设置、密码等）。
    - **用途：** 用于调试目的，例如当怀疑本地缓存数据损坏或导致同步行为异常时，可以尝试重置。
