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
ms.openlocfilehash: 9a0199577ea46520c2eadc308812de8a1ce4b514
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685810"
---
# <a name="dialog-data-exchange"></a>ダイアログ データ エクスチェンジ

DDX 機構を使用する場合は、ダイアログオブジェクトのメンバー変数の初期値を設定します。通常は、@no__t 0 ハンドラーまたはダイアログコンストラクターで設定します。 ダイアログが表示される直前に、フレームワークの DDX 機構によって、メンバー変数の値がダイアログボックス内のコントロールに転送されます。このコントロールは、ダイアログボックス自体が `DoModal` または `Create` に応答して表示されるときに表示されます。 @No__t-1 の `OnInitDialog` の既定の実装では、クラス `CWnd` の `UpdateData` メンバー関数を呼び出して、ダイアログボックス内のコントロールを初期化します。

同じメカニズムによって、ユーザーが [OK] ボタンをクリックしたとき (または、引数が**TRUE**の `UpdateData` メンバー関数を呼び出すたびに、コントロールからメンバー変数に値が転送されます)。 ダイアログデータ検証メカニズムでは、検証規則を指定したすべてのデータ項目が検証されます。

次の図は、ダイアログデータエクスチェンジを示しています。

![ダイアログボックスの [データエクスチェンジ](../mfc/media/vc379d1.gif "] ダイアログボックスデータエクスチェンジ") <br/>
ダイアログ データ エクスチェンジ

`UpdateData` は、渡された**BOOL**パラメーターで指定されているように、双方向で動作します。 Exchange を実行するには、`UpdateData` によって @no__t 1 のオブジェクトが設定され、ダイアログクラスの `CDialog` の @no__t メンバー関数のオーバーライドが呼び出されます。 `DoDataExchange` は、型 `CDataExchange` の引数を受け取ります。 @No__t に渡される @no__t 0 オブジェクトは、exchange のコンテキストを表し、exchange の方向などの情報を定義します。

@No__t-0 をオーバーライドする (またはコードウィザード) 場合は、データメンバー (コントロール) ごとに1つの DDX 関数の呼び出しを指定します。 各 DDX 関数は、`UpdateData` によって @no__t に渡される @no__t 0 引数によって提供されるコンテキストに基づいて、双方向にデータを交換する方法を認識します。

MFC には、さまざまな種類の exchange 用の多数の DDX 関数が用意されています。 次の例は、2つの DDX 関数と1つの DDV 関数が呼び出される、@no__t 0 のオーバーライドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

@No__t-0 と @no__t 1 行はデータマップです。 例として、サンプルの DDX 関数と DDV 関数は、それぞれ、チェックボックスコントロールとエディットボックスコントロールを示しています。

ユーザーがモーダルダイアログボックスをキャンセルした場合、@no__t 0 のメンバー関数はダイアログボックスを終了し、`DoModal` は値**IDCANCEL**を返します。 この場合、ダイアログボックスとダイアログオブジェクトの間でデータが交換されることはありません。

## <a name="see-also"></a>関連項目

[ダイアログ データ エクスチェンジとダイアログ データ検証](../mfc/dialog-data-exchange-and-validation.md)<br/>
[MFC でのダイアログボックスの操作](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[ダイアログ データ検証](../mfc/dialog-data-validation.md)
