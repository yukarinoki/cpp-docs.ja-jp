---
title: 仮想リスト コントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b580e455aab7ff95beb85c02b8e3ca79dfa8a46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384193"
---
# <a name="virtual-list-controls"></a>仮想リスト コントロール
仮想リスト コントロールがリスト ビュー コントロールを持つ、 **LVS_OWNERDATA**スタイル。 このスタイルに最大項目数をサポートするために制御を有効にする`DWORD`(既定のアイテム数だけまでの`int`)。 ただし、このスタイルで指定された最大の利点は、任意の時点で、メモリ内のデータ項目のサブセットをのみが機能です。 これにより、場所データにアクセスする方法が既に定められて貸与すること自体については、大規模なデータベースで使用するために仮想のリスト ビュー コントロール。  
  
> [!NOTE]
>  仮想一覧の機能を提供するだけでなく`CListCtrl`、MFC で同じ機能も用意されています。、 [CListView](../mfc/reference/clistview-class.md)クラスです。  
  
 問題があります互換性仮想リスト コントロールを開発するときに注意してください。 詳細については、Windows SDK のリスト ビュー コントロールのトピックの互換性の問題」セクションを参照してください。  
  
## <a name="handling-the-lvngetdispinfo-notification"></a>LVN_GETDISPINFO 通知の処理  
 仮想リスト コントロールでは、ほとんどの項目の情報を維持します。 項目の選択とフォーカス情報を除くすべての項目情報は、コントロールの所有者によって管理されます。 情報を使用して、フレームワークによって要求、 **LVN_GETDISPINFO**通知メッセージです。 要求された情報を提供するには、仮想リスト コントロール (または、コントロール自体) の所有者はこの通知を処理する必要があります。 これを行う簡単に、[プロパティ] ウィンドウを使用して (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。 結果のコードは次の例のようになります (ここで`CMyDialog`仮想リスト コントロール オブジェクトを所有していると、ダイアログ ボックスは、通知の処理)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]  
  
 ハンドラーで、 **LVN_GETDISPINFO**通知メッセージをどのような種類の情報が要求されているかを確認する必要があります。 次の値を指定できます。  
  
-   `LVIF_TEXT` `pszText`メンバーを入力する必要があります。  
  
-   `LVIF_IMAGE` `iImage`メンバーを入力する必要があります。  
  
-   **LVIF_INDENT** 、 *iIndent*メンバーを入力する必要があります。  
  
-   `LVIF_PARAM` *LParam*メンバーを入力する必要があります。 (存在しないのサブ項目です。)  
  
-   `LVIF_STATE` *状態*メンバーを入力する必要があります。  
  
 どのような情報をフレームワークに戻す要求を指定する必要があります。  
  
 (リスト コントロール オブジェクトの通知のハンドラーの本体から取得した) 次の例は、テキスト バッファーと項目のイメージに関する情報を指定することによって、1 つの可能なメソッドを示します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]  
  
## <a name="caching-and-virtual-list-controls"></a>キャッシュおよび仮想リスト コントロール  
 この種類のリスト コントロールには、大きなデータ セットとしているために、検索のパフォーマンスを向上させるために要求された項目のデータをキャッシュすることをお勧めします。 フレームワークが送信することによって、キャッシュを最適化するキャッシュ ヒント メカニズムを提供する**LVN_ODCACHEHINT**通知メッセージです。  
  
 次の例では、ハンドラー関数に渡された範囲でキャッシュを更新します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]  
  
 準備およびキャッシュのメンテナンスについての詳細については、Windows SDK のリスト ビュー コントロールのトピックのキャッシュ管理セクションを参照してください。  
  
## <a name="finding-specific-items"></a>特定の項目を検索します。  
 **ある**特定のリスト コントロール項目を検索する必要がある場合、仮想リスト コントロールによって通知メッセージが送信されます。 リスト ビュー コントロールがクイック キーへのアクセスを受信すると、または受信したときに、通知メッセージが送信される、**する**メッセージ。 形式で送信される情報の検索、**保持**メンバーである構造体の**NMLVFINDITEM**構造体。 オーバーライドすることによってこのメッセージを処理、 `OnChildNotify` 、一覧の関数は、コントロール オブジェクトをし、ハンドラーの本体での確認、**ある**メッセージ。 場合検出で、適切な操作を実行します。  
  
 リスト ビュー コントロールから提供された情報に一致する項目の検索を準備する必要があります。 一致する項目が見つからない場合は、成功した場合、項目のインデックスを返す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

