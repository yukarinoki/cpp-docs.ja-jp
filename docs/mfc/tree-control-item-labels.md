---
description: 詳細については、「ツリーコントロール項目のラベル」を参照してください。
title: ツリー コントロールの項目のラベル
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
ms.openlocfilehash: 62113a7534bf234ac8dde1154d5732bc29df8387
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264070"
---
# <a name="tree-control-item-labels"></a>ツリー コントロールの項目のラベル

通常、項目をツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) に追加するときに、項目のラベルのテキストを指定します。 この `InsertItem` メンバー関数は、項目のプロパティを定義する [TVITEM](/windows/win32/api/commctrl/ns-commctrl-tvitemw) 構造体を渡すことができます。これには、ラベルのテキストを含む文字列も含まれます。 `InsertItem` には、パラメーターのさまざまな組み合わせで呼び出すことができるいくつかのオーバーロードがあります。

ツリーコントロールは、各項目を格納するためのメモリを割り当てます。項目ラベルのテキストは、このメモリの大部分を占めています。 アプリケーションでツリーコントロールに文字列のコピーを保持している場合は、実際の文字列をツリーコントロールに渡す代わりに 、の *psztext* メンバー `TV_ITEM` または *lpszitem* パラメーターに LPSTR_TEXTCALLBACK 値を指定することで、コントロールのメモリ要件を減らすことができます。 **LPSTR_TEXTCALLBACK** を使用すると、項目を再描画する必要があるときに、ツリーコントロールがアプリケーションから項目のラベルのテキストを取得します。 テキストを取得するために、ツリーコントロールは、 [Nmtvdispinfo](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow)構造体のアドレスを含む[TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo)通知メッセージを送信します。 対応する構造体の適切なメンバーを設定することによって応答する必要があります。

ツリーコントロールは、ツリーコントロールを作成するプロセスのヒープから割り当てられたメモリを使用します。 ツリーコントロール内の項目の最大数は、ヒープで使用可能なメモリの量に基づいています。 各項目には64バイトが必要です。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
