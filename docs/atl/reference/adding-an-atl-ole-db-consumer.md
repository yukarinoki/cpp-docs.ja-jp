---
title: ATL OLE DB コンシューマーの追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95d0f16f88006c1e639b1f4a02965ad8dea6b818
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764281"
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB コンシューマーの追加

このウィザードを使用すると、プロジェクトに ATL OLE DB コンシューマーを追加します。 ATL OLE DB コンシューマーは、OLE DB アクセサー クラスとデータ バインディングのデータ ソースへのアクセスに必要なので構成されます。 ATL COM アプリケーションまたは ATL のサポート (ATL OLE DB コンシューマー ウィザードが自動的に追加します) を含む MFC または Win32 アプリケーションとして、プロジェクトが作成されましたがする必要があります。

**注**MFC プロジェクトに OLE DB コンシューマーを追加することができます。 場合は、ATL OLE DB コンシューマー ウィザードは、プロジェクトに必要な COM サポートを追加します。 これは、MFC プロジェクトを作成したときに選択した前提としています。、 **ActiveX コントロール**チェック ボックスをオン (で、**高度な機能**、MFC アプリケーション ウィザードのページ)、既定でチェックされます。 アプリケーションを呼び出すことにより、このオプションを選択する**CoInitialize**と**CoUninitialize**します。 選択しなかった場合**ActiveX コントロール**MFC プロジェクトを作成したときに、呼び出す必要があります。 **CoInitialize**と**CoUninitialize** 、メインのコードにします。

### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>ATL OLE DB コンシューマーをプロジェクトに追加するには

1. クラス ビューでプロジェクトを右クリックします。 ショートカット メニューで、**追加** をクリックし、**クラスの追加**します。

2. Visual C フォルダーで、ダブルクリック、 **ATL OLE DB コンシューマー**アイコンを選択し、クリックしてまたは**オープン**。

     ATL OLE DB コンシューマー ウィザードが開きます。

3. 」の説明に従って設定を定義[ATL OLE DB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)します。

4. クリックして**完了**ウィザードを閉じます。 新しく作成された OLE DB コンシューマー コードは、プロジェクトに挿入されます。

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)

