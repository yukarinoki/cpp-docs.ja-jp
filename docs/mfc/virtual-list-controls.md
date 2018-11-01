---
title: 仮想リスト コントロール
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: b9da918017d300d7af61b1fd3ab27869e136bb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573676"
---
# <a name="virtual-list-controls"></a>仮想リスト コントロール

仮想リスト コントロールは、LVS_OWNERDATA スタイルがリスト ビュー コントロールです。 このスタイルには、最大アイテム数をサポートするためにコントロールができるように、 **DWORD** (既定の項目数はのみに拡張、 **int**)。 ただし、このスタイルによって提供される最大の利点は、データ項目のサブセットを一度にメモリにのみが機能です。 これにより、データへのアクセスの特定のメソッドが既にインプレース変更がないものについては、大規模なデータベースで使用するために仮想リスト ビュー コントロール。

> [!NOTE]
>  仮想リスト機能を提供するだけでなく`CListCtrl`、MFC は、同じ機能も用意されています。、 [CListView](../mfc/reference/clistview-class.md)クラス。

仮想リスト コントロールを開発するときに注意する必要がある互換性の問題があります。 詳細については、Windows SDK のリスト ビュー コントロールのトピックの互換性の問題に関するセクションを参照してください。

## <a name="handling-the-lvngetdispinfo-notification"></a>LVN_GETDISPINFO 通知の処理

仮想リスト コントロールでは、ほとんどの項目情報を維持します。 項目の選択およびフォーカス情報を除くすべての項目情報は、コントロールの所有者によって管理されます。 LVN_GETDISPINFO 通知メッセージを使用して、フレームワークによって情報が要求されます。 要求された情報を提供するには、仮想リスト コントロール (または、コントロール自体) の所有者は、この通知を処理する必要があります。 これは簡単に行うことができます、[プロパティ] ウィンドウを使用して (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。 結果コードは次の例のようになります (場所`CMyDialog`仮想リスト コントロール オブジェクトを所有していると、ダイアログは、通知の処理)。

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

LVN_GETDISPINFO 通知メッセージのハンドラーでは、情報の種類が要求されているを確認する必要があります。 次の値を指定できます。

- `LVIF_TEXT` *PszText*メンバーを入力する必要があります。

- `LVIF_IMAGE` *画像を*メンバーを入力する必要があります。

- `LVIF_INDENT` *IIndent*メンバーを入力する必要があります。

- `LVIF_PARAM` *LParam*メンバーを入力する必要があります。 (存在しないサブ項目の。)

- `LVIF_STATE` *状態*メンバーを入力する必要があります。

フレームワークにすべての情報が要求を指定する必要があります。

(リスト コントロール オブジェクトの通知ハンドラーの本体から引用した) 次の例では、テキスト バッファーと項目のイメージに関する情報を指定して 1 つの可能なメソッドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>キャッシュおよび仮想リスト コントロール

この種類のリスト コントロールには、大規模なデータ セットとしているために、検索のパフォーマンスを向上させるために要求された項目のデータをキャッシュすることをお勧めします。 フレームワークは、キャッシュ ヒント LVN_ODCACHEHINT 通知メッセージを送信することによって、キャッシュの最適化を支援するメカニズムを提供します。

次の例では、ハンドラー関数に渡された範囲でキャッシュを更新します。

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

準備とキャッシュを維持する方法の詳細については、Windows SDK のリスト ビュー コントロールのトピックのキャッシュ管理セクションを参照してください。

## <a name="finding-specific-items"></a>特定の項目を検索します。

特定のリスト コントロール項目を検索する必要がある場合、仮想リスト コントロールである通知メッセージが送信されます。 リスト ビュー コントロールがクイック キーへのアクセスを受信すると、またはするメッセージを受信すると、通知メッセージが送信されます。 形式で検索情報が送信される、**保持**メンバーである構造体の**NMLVFINDITEM**構造体。 オーバーライドすることで、このメッセージを処理、`OnChildNotify`一覧の関数がオブジェクトを制御し、ハンドラーの本文内であるメッセージを確認します。 場合検出で、適切な操作を実行します。

リスト ビュー コントロールから提供された情報に一致する項目の検索を準備する必要があります。 一致する項目が見つからない場合は、成功した場合、項目のインデックスを返す必要があります。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

