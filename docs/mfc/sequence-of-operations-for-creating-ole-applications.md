---
title: OLE アプリケーションの作成操作のシーケンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 412fa5c104d6e85bcaa6ba3703cc8c7ba535f25f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE アプリケーションの作成手順
次の表は、OLE をリンクして、埋め込みアプリケーションを作成して、フレームワークの役割分担を示します。 これらを実行する手順のシーケンスではなく使用可能なオプションを表します。  
  
### <a name="creating-ole-applications"></a>OLE アプリケーションの作成  
  
|タスク|そうですよね|フレームワークを動作します。|  
|----------|------------|------------------------|  
|COM コンポーネントを作成します。|MFC アプリケーション ウィザードを実行します。 選択**フル サーバー**または**ミニ サーバー**で、**複合ドキュメント サポート**タブです。|フレームワークは、COM コンポーネントの機能が有効になっていると、スケルトン アプリケーションを生成します。 すべての COM 機能は、わずかな変更のみを使用して既存のアプリケーションに転送できます。|  
|コンテナー アプリケーションを最初から作成します。|MFC アプリケーション ウィザードを実行します。 選択**コンテナー**で、**複合ドキュメント サポート**タブです。クラス ビューを使用して、、ソース コード エディターに移動します。 COM ハンドラー関数のコードを入力します。|フレームワークは、COM コンポーネント (サーバー) のアプリケーションによって作成された COM オブジェクトを挿入できる、スケルトン アプリケーションを生成します。|  
|最初からオートメーションをサポートするアプリケーションを作成します。|MFC アプリケーション ウィザードを実行します。 選択**オートメーション**から、**高度な機能**タブです。Automation 用のアプリケーションのメソッドとプロパティを公開するのにには、クラス ビューを使用します。|フレームワークは、スケルトン アプリケーションをアクティブ化し、他のアプリケーションによって自動化できますを生成します。|  
  
## <a name="see-also"></a>関連項目  
 [フレームワークでのビルド](../mfc/building-on-the-framework.md)   
 [MFC アプリケーションの作成操作のシーケンス](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [ActiveX コントロールの作成操作のシーケンス](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [データベース アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-database-applications.md)

