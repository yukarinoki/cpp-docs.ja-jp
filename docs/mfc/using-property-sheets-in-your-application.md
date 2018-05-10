---
title: プロパティ シートを使用して、アプリケーションで |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74e63faf5b1cac5e0cb841a28fd59ecee47c9970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-property-sheets-in-your-application"></a>アプリケーションでのプロパティ シートの使用
プロパティ シートをアプリケーションで使用するには、次の手順を実行します。  
  
1.  各プロパティ ページのダイアログ テンプレート リソースを作成します。 ユーザー可能性があります 1 つのページからに切り替えて、各レイアウト ページ限り同じように注意してください。  
  
     すべてのページのダイアログ テンプレートは同じサイズではありません。 フレームワークでは、最大のページのサイズを使用して、プロパティ ページのプロパティ シートで割り当てる領域の量を決定します。  
  
     プロパティ ページのダイアログ テンプレート リソースを作成する場合は、ダイアログのプロパティのプロパティ シートで、次のスタイルを指定する必要があります。  
  
    -   設定、**キャプション**の編集ボックス、**全般**をこのページのタブに表示するテキスト ページ。  
  
    -   設定、**スタイル**のリスト ボックス、**スタイル**へのページングを**子**です。  
  
    -   設定、**罫線**のリスト ボックス、**スタイル**へのページングを**Thin**です。  
  
    -   いることを確認、 **Titlebar**チェック ボックスをオン、**スタイル**ページを選択します。  
  
    -   いることを確認、**無効になっている**チェック ボックスをオン、**他のスタイル**ページを選択します。  
  
2.  作成、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)の各プロパティ ページ ダイアログ テンプレートに対応するクラスを派生します。 参照してください[クラスの追加](../ide/adding-a-class-visual-cpp.md)です。 選択`CPropertyPage`基底クラスとして。  
  
3.  メンバーに、このプロパティ ページの値を保持する変数を作成します。 プロパティ ページにメンバー変数を追加する手順は、プロパティ ページが特別なダイアログ ボックスであるため正確に ダイアログ ボックスでは、メンバー変数を追加すると同じです。 詳細については、次を参照してください。[ダイアログ コントロールのメンバー変数を定義する](../windows/defining-member-variables-for-dialog-controls.md)です。  
  
4.  構築、 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)ソース コード内のオブジェクト。 通常を構築する、`CPropertySheet`プロパティ シートを表示するコマンドのハンドラーは、内のオブジェクト。 このオブジェクトは、プロパティ シート全体を表します。 持つモーダル プロパティ シートを作成する場合、 [DoModal](../mfc/reference/cpropertysheet-class.md#domodal)関数、フレームワークは、既定では次の 3 つのコマンド ボタンを提供します。 [ok]、[キャンセル]、適用します。 フレームワークを作成しませんコマンド ボタンでモードレス プロパティ シートが作成されたため、[作成](../mfc/reference/cpropertysheet-class.md#create)関数。 クラスを派生する必要はありません`CPropertySheet`(プレビュー ウィンドウ) などその他のコントロールを追加するか、モードレス プロパティ シートを表示する場合を除き、します。 プロパティ シートを閉じるために使用できる既定のコントロールが含まれていないために、この手順はモードレス プロパティ シートの必要があります。  
  
5.  プロパティ シートに追加するには、各ページには、次の操作を行います。  
  
    -   ごとに 1 つのオブジェクトを構築`CPropertyPage`-このプロセスの前半で作成したクラスを派生します。  
  
    -   呼び出す[が](../mfc/reference/cpropertysheet-class.md#addpage)ページごとにします。  
  
     通常、オブジェクトを作成する、`CPropertySheet`も作成、`CPropertyPage`このステップでのオブジェクト。 ただし、実装する場合、 `CPropertySheet`-派生クラスに埋め込むことができます、`CPropertyPage`内のオブジェクト、`CPropertySheet`オブジェクトと呼び出し`AddPage`からページごとに、 `CPropertySheet`-派生したクラスのコンス トラクターです。 `AddPage` 追加、`CPropertyPage`オブジェクトのページのプロパティ シートの一覧には、そのページは、ウィンドウを実際には作成されません。 そのため、ウィンドウの作成、プロパティ シートを呼び出すまで待機する必要はありません`AddPage`; 呼び出せます`AddPage`プロパティ シートのコンス トラクターからです。  
  
     既定では、プロパティ シート、プロパティ シートの 1 つの行に収まらないのタブがある場合、タブは複数の行に積み重ねられます。 重なりを無効にするを呼び出す[CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs)パラメーターを設定した**FALSE**です。 呼び出す必要があります`EnableStackedTabs`プロパティ シートを作成する場合。  
  
6.  呼び出す[する](../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../mfc/reference/cpropertysheet-class.md#create)プロパティ シートを表示します。 呼び出す`DoModal`モーダル ダイアログ ボックスとしてプロパティ シートを作成します。 呼び出す**作成**モードレス ダイアログ ボックスとしてプロパティ シートを作成します。  
  
7.  プロパティ ページおよびプロパティ シートの所有者の間でデータを交換します。 アーティクルの詳細については[データの交換](../mfc/exchanging-data.md)です。  
  
 プロパティ シートを使用する方法の例は、MFC 標準サンプルを参照してください。 [PROPDLG](../visual-cpp-samples.md)です。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

