---
description: 詳細については、プロバイダーの作成に関するページを参照してください。
title: プロバイダーの作成
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 2b5a00f0a873575d9fe7b2b177bb34a6c74e193e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305436"
---
# <a name="creating-the-provider"></a>プロバイダーの作成

::: moniker range="msvc-160"

ATL OLE DB プロバイダー ウィザードは、Visual Studio 2019 以降では使用できません。

::: moniker-end

::: moniker range="<=msvc-150"

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB プロバイダー ウィザードで OLE DB プロバイダーを作成するには

1. プロジェクトを右クリックします。

1. ショートカットメニューの [ **追加**] をクリックし、[ **クラスの追加**] をクリックします。

1. **[クラスの追加]** ダイアログ ボックスで、**[インストール済み]** > **[Visual C++]** > **[ATL]** の下にある **[ATL OLEDB プロバイダー]** アイコンを選択し、**[開く]** をクリックします。

1. **ATL OLE DB プロバイダー ウィザード** で、**[短い名前]** ボックスにプロバイダーの短い名前を入力します。 以降のトピックでは、短い名前として *Custom* を使用しますが、別の名前を使用してもかまいません。 他の名前ボックスは、入力した名前に基づいて設定されます。

1. 必要に応じて、他の名前ボックスを編集します。 オブジェクト名やファイル名のほかにも、以下を編集できます。

   - **Coclass**: COM がプロバイダーを作成するために使用する名前。

   - **ProgID**: GUID の代わりに使用できるテキスト文字列であるプログラム識別子。

   - **Version**: バージョンに依存するプログラム ID を生成するために、ProgID およびコクラスと共に使用されます。

1. **[完了]** をクリックします。

::: moniker-end

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)
