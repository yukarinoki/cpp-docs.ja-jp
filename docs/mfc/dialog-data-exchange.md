---
description: 詳細については、「ダイアログデータエクスチェンジ」を参照してください。
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
ms.openlocfilehash: 7ed592e8e6a452d4c6958c3c5f7b573c1be7fe07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261477"
---
# <a name="dialog-data-exchange"></a>ダイアログ データ エクスチェンジ

DDX 機構を使用する場合は、ダイアログオブジェクトのメンバー変数の初期値 (通常は `OnInitDialog` ハンドラーまたはダイアログコンストラクター) を設定します。 ダイアログが表示される直前に、フレームワークの DDX 機構によって、メンバー変数の値がダイアログボックスのコントロールに転送されます。これらの変数は、ダイアログボックス自体がまたはに応答して表示されるときに表示され `DoModal` `Create` ます。 のの既定の実装では、 `OnInitDialog` `CDialog` `UpdateData` クラスのメンバー関数を呼び出して `CWnd` 、ダイアログボックス内のコントロールを初期化します。

ユーザーが [OK] ボタンをクリックしたとき、または `UpdateData` 引数が **TRUE** のメンバー関数を呼び出すと、同じメカニズムによってコントロールからメンバー変数に値が転送されます。 ダイアログデータ検証メカニズムでは、検証規則を指定したすべてのデータ項目が検証されます。

次の図は、ダイアログデータエクスチェンジを示しています。

![ダイアログ ボックス データ エクスチェンジ](../mfc/media/vc379d1.gif "ダイアログ ボックス データ エクスチェンジ") <br/>
ダイアログ データ エクスチェンジ

`UpdateData` は、渡される **BOOL** パラメーターで指定されているように、双方向で動作します。 Exchange を実行するには、によって `UpdateData` オブジェクトが設定さ `CDataExchange` れ、ダイアログクラスのメンバー関数のオーバーライドが呼び出さ `CDialog` `DoDataExchange` れます。 `DoDataExchange` 型の引数を受け取り `CDataExchange` ます。 `CDataExchange`に渡されるオブジェクトは、exchange の `UpdateData` コンテキストを表し、exchange の方向などの情報を定義します。

(またはコードウィザードで) をオーバーライドする場合は `DoDataExchange` 、データメンバー (コントロール) ごとに1つの DDX 関数の呼び出しを指定します。 各 DDX 関数は、によって渡された引数によって提供されるコンテキストに基づいて、双方向にデータを交換する方法を認識 `CDataExchange` `DoDataExchange` `UpdateData` します。

MFC には、さまざまな種類の exchange 用の多数の DDX 関数が用意されています。 次の例は、 `DoDataExchange` 2 つの DDX 関数と1つの DDV 関数が呼び出されるオーバーライドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#49](codesnippet/cpp/dialog-data-exchange_1.cpp)]

`DDX_`行と `DDV_` 行はデータマップです。 例として、サンプルの DDX 関数と DDV 関数は、それぞれ、チェックボックスコントロールとエディットボックスコントロールを示しています。

ユーザーがモーダルダイアログボックスをキャンセルした場合、 `OnCancel` メンバー関数はダイアログボックスを終了し、 `DoModal` 値 **IDCANCEL** を返します。 この場合、ダイアログボックスとダイアログオブジェクトの間でデータが交換されることはありません。

## <a name="see-also"></a>関連項目

[ダイアログデータエクスチェンジと検証](dialog-data-exchange-and-validation.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)<br/>
[ダイアログデータの検証](dialog-data-validation.md)
