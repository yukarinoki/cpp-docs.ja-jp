---
title: ツリーのコントロールの項目のラベル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fc207dcff5002262c345b106be99a775ed626b9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953725"
---
# <a name="tree-control-item-labels"></a>ツリー コントロールの項目のラベル
ツリー コントロールに項目を追加するときに通常、項目のラベルのテキストを指定する ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))。 `InsertItem`メンバー関数に渡すことができます、 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456)ラベルのテキストを含む文字列を含む、アイテムのプロパティを定義する構造体。 `InsertItem` パラメーターのさまざまな組み合わせで呼び出すことができるいくつかのオーバー ロードがあります。  
  
 ツリー コントロールは各項目を格納するためのメモリを割り当てます項目のラベルのテキストは、このメモリのかなりの部分を取得します。 アプリケーションが、ツリー コントロール内の文字列のコピーを保持する場合を指定してコントロールのメモリ要件を減らすことができます、**保持するようにする**値で、 *pszText* のメンバー`TV_ITEM`または*lpszItem*ツリー コントロールに実際の文字列を渡すことではなくパラメーター。 使用して**保持するようにする**ツリー コントロールの項目が再描画する必要があるとき、アプリケーションから、項目のラベルのテキストを取得します。 テキストを取得するには、ツリー コントロールの送信、 [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518)通知メッセージのアドレスが含まれていますが、 [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418)構造体。 構造体の適切なメンバーを設定して応答する必要があります。  
  
 ツリー コントロールでは、ツリー コントロールを作成するプロセスのヒープから割り当てられたメモリを使用します。 ツリー コントロールの項目の最大数は、ヒープに使用可能なメモリの量に基づきます。 各項目は 64 バイトが使用されます。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

