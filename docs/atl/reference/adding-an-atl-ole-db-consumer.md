---
title: ATL OLE DB コンシューマーの追加
ms.date: 05/09/2019
helpviewer_keywords:
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: c298a841bf0d37f90bcd6b53bc0c6cdf501f4dd3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921153"
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB コンシューマーの追加

::: moniker range="msvc-160"

ATL OLE DB コンシューマー ウィザードは、Visual Studio 2019 以降では使用できません。 ただし、この機能を手動で追加することは可能です。 詳細については、「[ウィザードを使用しないコンシューマーの作成](../../data/oledb/creating-a-consumer-without-using-a-wizard.md)」をご覧ください。

::: moniker-end

::: moniker range="<=msvc-150"

このウィザードを使用して、ATL OLE DB コンシューマーをプロジェクトに追加します。 ATL OLE DB コンシューマーは、OLE DB アクセサー クラスとデータ ソースにアクセスするために必要データ バインドで構成されます。 プロジェクトは、ATL COM アプリケーションとして作成されているか、ATL のサポート (ATL OLE DB コンシューマー ウィザードによって自動的に追加されます) を含む MFC または Win32 アプリケーションとして作成されている必要があります。

> [!NOTE]
> MFC プロジェクトに OLE DB コンシューマーを追加できます。 これを行った場合は、プロジェクトに必要な COM サポートが ATL OLE DB コンシューマー ウィザードによって追加されます。 これは、MFC プロジェクトの作成時に、 **[ActiveX コントロール]** チェック ボックス (MFC プロジェクト アプリケーション ウィザードの **[高度な機能]** ページ内) がオンになっていることを前提としています (このチェックボックスは既定でオンになっています)。 このオプションを選択することで、アプリケーションで `CoInitialize` と `CoUninitialize` が必ず呼び出されます。 MFC プロジェクトの作成時に **[ActiveX コントロール]** を選択しなかった場合は、メイン コードで `CoInitialize` と `CoUninitialize` を呼び出す必要があります。

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>プロジェクトに ATL OLE DB コンシューマーを追加するには

1. **クラス ビュー** で、プロジェクトを右クリックします。 ショートカット メニューの **[追加]** をクリックし、 **[クラスの追加]** をクリックします。

1. Visual C++ フォルダーで **[ATL OLE DB コンシューマー]** アイコンをダブルクリックするかそれを選択し、 **[開く]** をクリックします。

   ATL OLE DB コンシューマー ウィザードが開きます。

1. 「[ATL OLE DB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)」の説明に従って設定を定義します。

1. **[完了]** をクリックして、ウィザードを終了します。 新しく作成された OLE DB コンシューマー コードがプロジェクトに挿入されます。

::: moniker-end

## <a name="see-also"></a>こちらもご覧ください

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)
