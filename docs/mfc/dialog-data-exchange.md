---
title: ダイアログ データ エクスチェンジ
ms.date: 11/19/2018
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
ms.openlocfilehash: 338630aef358d9490461179288d5c45a2d3b821c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302314"
---
# <a name="dialog-data-exchange"></a>ダイアログ データ エクスチェンジ

DDX 機構を使用する場合、ダイアログ ボックスの初期値オブジェクトのメンバー変数を設定するでは通常、`OnInitDialog`ハンドラーまたはダイアログのコンス トラクター。 フレームワークの DDX 機構が表示されるダイアログ ボックスで、コントロールにメンバー変数の値を転送するダイアログ ボックスが表示される前にすぐにダイアログ ボックスが表示されたらへの応答で`DoModal`または`Create`します。 既定の実装`OnInitDialog`で`CDialog`呼び出し、`UpdateData`クラスのメンバー関数`CWnd` ダイアログ ボックス内のコントロールを初期化します。

同じメカニズムに転送メンバー変数に値がコントロールから、ユーザーが [ok] ボタンをクリックしたときに (または、呼び出すたびに、 `UpdateData` 、引数を持つメンバー関数**TRUE**)。 ダイアログ データ検証メカニズムは、検証規則が指定されているすべてのデータ項目を検証します。

ダイアログ データ エクス チェンジの図は、次のとおりです。

![ダイアログ ボックス データ エクス チェンジ](../mfc/media/vc379d1.gif " ダイアログ ボックス データ エクス チェンジ") <br/>
ダイアログ データ エクスチェンジ

`UpdateData` 指定された双方向で機能、 **BOOL**に渡されるパラメーター。 Exchange を実行するために`UpdateData`設定、`CDataExchange`オブジェクトと呼び出しダイアログ クラスのオーバーライド`CDialog`の`DoDataExchange`メンバー関数。 `DoDataExchange` 型の引数を受け取る`CDataExchange`します。 `CDataExchange`オブジェクトに渡される`UpdateData`exchange の方向として、このような情報を定義する、exchange のコンテキストを表します。

(またはコード ウィザード) をオーバーライドする場合`DoDataExchange`、データ メンバー (コントロール) ごとに 1 つの DDX 関数の呼び出しを指定します。 各 DDX 関数によって提供されるコンテキストに基づいて双方向にデータを交換する方法を知っている、`CDataExchange`に渡される引数、`DoDataExchange`によって`UpdateData`します。

MFC には、exchange のさまざまな種類の多くの DDX 関数が用意されています。 次の例は、`DoDataExchange`関数と 1 つの DDV 関数が呼び出されている 2 つの DDX の上書き。

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

`DDX_`と`DDV_`線は、データ マップします。 示されたサンプル DDX ルーチンおよび DDV 関数は、チェック ボックス コントロールおよび編集ボックス コントロールでは、それぞれです。

ユーザーが、モーダル ダイアログ ボックスをキャンセルした場合、`OnCancel`メンバー関数は、ダイアログ ボックスを終了します。 および`DoModal`値を返します**IDCANCEL**します。 その場合は、ダイアログ ボックスで、ダイアログ オブジェクト間で交換されるデータはありません。

## <a name="see-also"></a>関連項目

[ダイアログ データ エクスチェンジとダイアログ データ検証](../mfc/dialog-data-exchange-and-validation.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[ダイアログ データ検証](../mfc/dialog-data-validation.md)
