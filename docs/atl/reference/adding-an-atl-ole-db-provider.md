---
title: ATL OLE DB プロバイダーの追加
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB, adding ATL OLE DB provider to projects
- ATL projects, adding ATL OLE DB providers
- ATL OLE DB providers
ms.assetid: 26fba1e3-880f-4bc6-90e5-2096a48a3a6c
ms.openlocfilehash: 78f26f43d11471c83bf9efcfc3aa55a23f0fbf3e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524610"
---
# <a name="adding-an-atl-ole-db-provider"></a>ATL OLE DB プロバイダーの追加

::: moniker range="vs-2019"

ATL OLE DB プロバイダー ウィザードは、Visual Studio 2019 以降では使用できません。

::: moniker-end

::: moniker range="vs-2017"

このウィザードを使用して、ATL OLE DB プロバイダーをプロジェクトに追加します。 ATL OLE DB プロバイダーは、データ ソース、セッション、コマンド、および行セット クラスで構成されます。 プロジェクトは、ATL COM アプリケーション プロジェクトとして作成されている必要があります。

## <a name="to-add-an-atl-ole-db-provider-to-your-project"></a>プロジェクトに ATL OLE DB プロバイダーを追加するには

1. **クラス ビュー**で、プロジェクトを右クリックします。 ショートカット メニューの **[追加]** をクリックし、 **[クラスの追加]** をクリックします。

1. **Visual C++** フォルダーで **[ATL OLE DB プロバイダー]** アイコンをダブルクリックするかそれを選択し、 **[開く]** をクリックします。

   ATL OLE DB プロバイダー ウィザードが開きます。

1. 「[ATL OLE DB プロバイダー ウィザード](../../atl/reference/atl-ole-db-provider-wizard.md)」の説明に従って設定を定義します。

1. **[完了]** をクリックしてウィザードを閉じます。これにより、新しく作成された OLE DB プロバイダーのコードがプロジェクトに挿入されます。

::: moniker-end

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)
