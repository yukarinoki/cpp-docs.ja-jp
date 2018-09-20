---
title: OLE アプリケーションの作成操作のシーケンス |Microsoft Docs
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
ms.openlocfilehash: 02542f8a4eb382ff4d7a88f98163b0052be09f75
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392522"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE アプリケーションの作成手順

次の表は、OLE リンク、埋め込みアプリケーションを作成することで、役割、およびフレームワークの役割を示します。 これらを実行する手順のシーケンスではなく使用できるオプションを表します。

### <a name="creating-ole-applications"></a>OLE アプリケーションの作成

|タスク|そうですよね|フレームワークを動作します。|
|----------|------------|------------------------|
|COM コンポーネントを作成します。|MFC アプリケーション ウィザードを実行します。 選択**フル サーバー**または**ミニ サーバー**で、**複合ドキュメント サポート**タブ。|フレームワークは、COM コンポーネントの機能が有効になっていると、スケルトン アプリケーションを生成します。 すべての COM 機能は、わずかな変更だけで、既存のアプリケーションに転送できます。|
|コンテナー アプリケーションをゼロから作成します。|MFC アプリケーション ウィザードを実行します。 選択**コンテナー**で、**複合ドキュメント サポート**タブ。クラス ビューを使用すると、ソース コード エディターに移動します。 COM ハンドラー関数のコードを入力します。|フレームワークでは、COM コンポーネント (サーバー) のアプリケーションによって作成された COM オブジェクトを挿入できる、スケルトン アプリケーションを生成します。|
|最初からオートメーションをサポートするアプリケーションを作成します。|MFC アプリケーション ウィザードを実行します。 選択**Automation**から、**高度な機能**タブ。お使いの automation のメソッドとプロパティを公開するのにには、クラス ビューを使用します。|フレームワークには、スケルトン アプリケーションをアクティブ化し、他のアプリケーションによって自動化できますが生成されます。|

## <a name="see-also"></a>関連項目

[フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)<br/>
[MFC アプリケーションの作成手順](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[データベース アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-database-applications.md)

