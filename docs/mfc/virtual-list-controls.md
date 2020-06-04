---
title: 仮想リスト コントロール
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: 1ade5f404e134cf6de20756dcc5af169fefdec76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375516"
---
# <a name="virtual-list-controls"></a>仮想リスト コントロール

仮想リスト コントロールは、LVS_OWNERDATA スタイルを持つリスト ビュー コントロールです。 このスタイルを使用すると、コントロールは**DWORD**までの項目数をサポートできます (既定の項目数は int にしか及**びません**)。 ただし、このスタイルで提供される最大の利点は、一度にメモリ内のデータ項目のサブセットのみを持つ機能です。 これにより、仮想リスト ビュー コントロールは、データにアクセスする特定の方法が既に整っている大規模な情報データベースで使用できます。

> [!NOTE]
> で仮想リスト機能を提供するだけでなく`CListCtrl`、MFC は[CListView](../mfc/reference/clistview-class.md)クラスでも同じ機能を提供します。

仮想リスト コントロールを開発する際には、互換性に関する問題がいくつかあります。 詳細については、Windows SDK のリスト ビュー コントロールのトピックの互換性の問題セクションを参照してください。

## <a name="handling-the-lvn_getdispinfo-notification"></a>LVN_GETDISPINFO通知の処理

仮想リスト コントロールは、アイテム情報をほとんど保持しないです。 項目の選択とフォーカス情報を除き、すべての項目情報はコントロールの所有者によって管理されます。 情報は、LVN_GETDISPINFO通知メッセージを介してフレームワークによって要求されます。 要求された情報を提供するには、仮想リスト コントロールの所有者 (またはコントロール自体) がこの通知を処理する必要があります。 これは[クラス ウィザード](reference/mfc-class-wizard.md)を使用して簡単に行うことができます (「[関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)」を参照)。 結果のコードは、次の例のようになります (仮想リスト`CMyDialog`コントロール オブジェクトを所有し、ダイアログが通知を処理している場合)。

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

LVN_GETDISPINFO通知メッセージのハンドラーで、要求されている情報の種類を確認する必要があります。 指定できる値は、

- `LVIF_TEXT`*pszText*メンバーに入力する必要があります。

- `LVIF_IMAGE`*iImage*メンバーは、入力する必要があります。

- `LVIF_INDENT`*iIndent*メンバーは、入力する必要があります。

- `LVIF_PARAM`*lParam*メンバーは、入力する必要があります。 (サブアイテムには存在しません。

- `LVIF_STATE`*状態*メンバーは入力する必要があります。

その後、フレームワークに要求された情報を提供する必要があります。

次の例 (リスト コントロール オブジェクトの通知ハンドラーの本文から取得) は、テキスト バッファーと項目のイメージの情報を提供することによって、1 つの可能なメソッドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>キャッシュと仮想リスト コントロール

このタイプのリスト コントロールは大規模なデータ セットを対象としているため、取得パフォーマンスを向上させるために要求された項目データをキャッシュすることをお勧めします。 フレームワークは、LVN_ODCACHEHINT通知メッセージを送信することによってキャッシュを最適化するためのキャッシュヒントメカニズムを提供します。

ハンドラー関数に渡された範囲でキャッシュを更新する例を次に示します。

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

キャッシュの準備と保守の詳細については、Windows SDK の「リスト ビュー コントロール」の「キャッシュ管理」セクションを参照してください。

## <a name="finding-specific-items"></a>特定のアイテムを検索する

LVN_ODFINDITEM通知メッセージは、特定のリスト コントロール項目が見つかる必要があるときに、仮想リスト コントロールによって送信されます。 通知メッセージは、リスト ビュー コントロールがクイック キー アクセスを受け取ったとき、またはLVM_FINDITEM メッセージを受信したときに送信されます。 検索情報は **、NMLVFINDITEM**構造体のメンバーである**LVFINDINFO**構造体の形式で送信されます。 リスト コントロール オブジェクトの`OnChildNotify`関数をオーバーライドし、ハンドラーの本体内で、このメッセージを処理するには、LVN_ODFINDITEM メッセージを確認します。 見つかった場合は、適切なアクションを実行します。

リスト ビュー コントロールによって指定された情報と一致する項目を検索する準備が必要です。 成功した場合はアイテムのインデックスを返し、一致するアイテムが見つからない場合は -1 を返します。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
