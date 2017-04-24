---

copyright:

  years: 2015, 2017

lastupdated: "2017-03-03"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理使用者帳戶及存取權
{: #iamusermanage}

取決於您獲授權管理的存取選項，您可以檢視及管理帳戶或組織的使用者。身為帳戶擁有者，您可以管理您負責管理的任何存取選項中的使用者，以及在現行帳戶中使用者獲指派存取的選項（不論角色為何）。您可以在所管理的任何存取選項中，指派、編輯及移除使用者的存取權。{:shortdesc}

若要管理您帳戶中的使用者，請從功能表列中按一下**管理** &gt; **帳戶** &gt; **使用者**。「使用者」視窗即會顯示使用者清單，其中包含其電子郵件位址，以及其於您所管理帳戶中的現行狀態。從「使用者」視窗中，選取要管理的使用者，或按一下**動作**功能表中的**管理使用者**。您會看到您可以為該使用者管理之存取選項的原則表格。

## 管理身分及存取權啟用服務
{: #iammanidaccser}

如果使用者已獲指派**身分及存取權啟用服務**的存取權，您會在「管理使用者」視窗中看到獲指派原則的相關資訊。針對該使用者或群組所顯示的內容，取決於已指派的原則。如果未指派任何原則，您會看到一則訊息詢問您是否要指派原則。如果已指派原則，則會顯示原則清單，其中包含使用者或群組的角色，以及每一項原則的資源屬性說明。您可以按一下**指派服務原則**，以從「指派原則」頁面指派原則。如果您已獲授權可建立原則，則會啟用**指派服務原則**選項。若要管理現有原則，您可以按一下清單中的原則，或是在您要編輯的原則列中，按一下**動作**下的**編輯原則**。

## 管理 Cloud Foundry 服務存取
{: #iammancfser}

如果使用者已獲指派 **Cloud Foundry** 的存取權，您會在「管理使用者」視窗中看到已指派給使用者的組織及空間。您可以將使用者從組織移除，也可以變更已指派給組織或空間的角色。如果使用者還不是您所管理之另一個組織的成員，您可以按一下**指派組織**，將使用者新增至該組織。若要管理現有空間及組織角色，您可以在您要編輯的角色列中，按一下**編輯空間角色**或**編輯組織角色**。

### 管理原則
{: #iamusermanpol}

您可以為有**身分及存取權啟用服務**存取權的使用者指派及管理原則。原則會使用屬性組合來定義適用的資源集，將對資源集的一或數個角色指派給使用者。

當您將原則指派給使用者時，請先指定所要指派的服務。**服務**清單會提供特定服務的選項，包括指派所有可用服務的選項。您同時要選取所要指派的一或數個角色。

取決於您選取的服務，還有其他配置選項可供使用。您可以選取服務，以查看該服務的選項。

您可以縮短所顯示的服務選項清單。按一下**指定選用的服務環境定義**，以指定其他選項，例如地區及服務實例。您可能不想要指定顯示的所有選項，但您可以選擇要配置哪些選項。

如果您有適當的角色，可以指派及管理原則。下表顯示原則管理作業，以及各項作業所需的角色。


{: #iamui_table1}

| 動作 | 所需的角色 |
|----------|---------|
| 建立帳戶的原則 | 帳戶的管理者 |
| 建立帳戶中所有服務的原則 | 帳戶的管理者 |
| 建立帳戶中所有服務實例的原則 | 帳戶的管理者 |
| 建立帳戶中服務的原則 | 帳戶的管理者，或帳戶中服務的管理者 |
| 建立服務實例 | 帳戶的管理者或編輯者，或帳戶中服務的管理者或編輯者 |
| 建立服務實例的原則 | 帳戶的管理者、帳戶中服務的管理者，或服務實例的管理者 |
{: caption="表 1. 管理**已啟用身分及存取的服務**原則用的管理作業" caption-side="top"}

### 指派及管理角色
{: #iamusermanrol}

角色是動作的集合；對映至這些角色的動作是服務特有的。
因為動作會分組成各角色，所以您可以使用一小組已定義的角色來為任何服務及任何資源支援任何動作。例如，如果您需要虛擬機器、儲存空間及網路的管理者，您可以透過變更原則的目標，將使用者設為這三項的管理者。因此，您要將原則設定為包括虛擬機器管理者、儲存空間管理者及網路管理者。

資源不會建置在角色中，這樣才不會為系統中引進的每種資源類型建立新的角色名稱。例如，您不需要虛擬機器管理者角色、儲存空間管理者角色及網路管理者角色來負責管理虛擬機器、儲存空間及網路的資源。

除了使用者介面中提供的角色說明之外，下表還提供獲指派各角色之使用者可以執行的部分作業範例。

{: #iamui_table2}

| 角色 | 動作的說明 | 動作範例|
|:-----------------|:-----------------|:-----------------|
| 檢視者 | 執行不會變更狀態的動作；唯讀動作 | <ul><li>列出裝置</li><li>讀取儲存空間物件</li><li>執行查詢</li><li>執行搜尋</li></ul>|
| 編輯者 | 執行修改狀態的動作，以及建立或刪除子資源 |<ul><li>建立或刪除虛擬機器</li><li>連接儲存空間</li><li>重新開機</li><li>啟動或停止</li><li>重新命名</li></ul> |
| 管理者 | 執行所有動作，包括管理存取控制的能力 |<ul><li>邀請使用者</li><li>建立或刪除虛擬機器</li><li>更新使用者存取原則</li><li>列出裝置</li><li>連接儲存空間</li><li>重新開機</li><li>啟動或停止</li><li>重新命名</li><li>備份及還原</li></ul>|
{: caption="表 2. 管理**已啟用身分及存取的服務**原則用的管理作業" caption-side="top"}

如需獲指派可存取 Cloud Foundry 之使用者角色的特定相關資訊，請參閱[使用者角色](/docs/admin/users_roles.html#userrolesinfo)。

當您新增使用者時，必須至少選取一個角色，而且可以新增多個角色。當您選取角色時，會看到角色的定義，讓您可以判定所要提供的一或數個角色。您指派的角色具有不同的存取選項，但都是存取您指定的相同資源屬性。

如果您選取 **Cloud Foundry** 服務，則您指派的角色會與您選取的組織及空間相關聯。