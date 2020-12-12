---
description: 詳細については、アプリケーションでのプロパティシートの使用に関するページを参照してください。
title: アプリケーションでのプロパティ シートの使用
ms.date: 11/04/2016
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
ms.openlocfilehash: 3bc1e21d99eb4a1688247524749b44028762892d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322687"
---
# <a name="using-property-sheets-in-your-application"></a>アプリケーションでのプロパティ シートの使用

アプリケーションでプロパティシートを使用するには、次の手順を実行します。

1. 各プロパティページのダイアログテンプレートリソースを作成します。 ユーザーがページ間を切り替える可能性があることに注意してください。したがって、各ページはできるだけ一貫して配置してください。

   すべてのページのダイアログテンプレートは、同じサイズである必要はありません。 フレームワークは、最大ページサイズを使用して、プロパティページのプロパティシートで割り当てられる領域を決定します。

   プロパティページのダイアログテンプレートリソースを作成する場合は、[ダイアログのプロパティ] プロパティシートで次のスタイルを指定する必要があります。

   - **[全般**] ページの [**キャプション**] 編集ボックスに、このページのタブに表示されるテキストを設定します。

   - [**スタイル**] ページの [**スタイル**] ボックスを [**子**] に設定します。

   - [**スタイル**] ページの [**罫線**] ボックスを [**細**] に設定します。

   - [**スタイル**] ページの [**タイトルバー** ] チェックボックスがオンになっていることを確認します。

   - [その **他のスタイル**] ページで [**無効**] チェックボックスがオンになっていることを確認します。

1. 各プロパティページダイアログテンプレートに対応する [CPropertyPage](../mfc/reference/cpropertypage-class.md)派生クラスを作成します。 「 [クラスの追加」を](../ide/adding-a-class-visual-cpp.md)参照してください。 `CPropertyPage`基本クラスとしてを選択します。

1. このプロパティページの値を保持するメンバー変数を作成します。 プロパティページは特化されたダイアログボックスであるため、プロパティページにメンバー変数を追加するプロセスは、ダイアログボックスにメンバー変数を追加する場合とまったく同じです。 詳細については、「 [ダイアログコントロールのメンバー変数の定義](../windows/adding-editing-or-deleting-controls.md)」を参照してください。

1. ソースコードで [CPropertySheet](../mfc/reference/cpropertysheet-class.md) オブジェクトを構築します。 通常、 `CPropertySheet` プロパティシートを表示するコマンドのハンドラーにオブジェクトを構築します。 このオブジェクトは、プロパティシート全体を表します。 [DoModal](../mfc/reference/cpropertysheet-class.md#domodal)関数を使用してモーダルプロパティシートを作成する場合、フレームワークには既定で [OK]、[キャンセル]、および [適用] の3つのコマンドボタンが用意されています。 フレームワークは、 [Create](../mfc/reference/cpropertysheet-class.md#create) 関数で作成されたモードレスプロパティシートに対してコマンドボタンを作成しません。 `CPropertySheet`他のコントロール (プレビューウィンドウなど) を追加するか、モードレスプロパティシートを表示する場合を除き、からクラスを派生させる必要はありません。 この手順は、プロパティシートを閉じるために使用できる既定のコントロールが含まれていないため、モードレスプロパティシートに対して必要です。

1. プロパティシートに追加するページごとに、次の操作を行います。

   - `CPropertyPage`このプロセスで前に作成した派生クラスごとに1つのオブジェクトを構築します。

   - 各ページに対して [CPropertySheet:: AddPage](../mfc/reference/cpropertysheet-class.md#addpage) を呼び出します。

   通常、を作成するオブジェクトは、 `CPropertySheet` `CPropertyPage` この手順でもオブジェクトを作成します。 ただし、派生クラスを実装する場合は、オブジェクトを `CPropertySheet` `CPropertyPage` オブジェクトに埋め込み、 `CPropertySheet` から派生した `AddPage` クラスコンストラクターから各ページに対してを呼び出すことができ `CPropertySheet` ます。 `AddPage``CPropertyPage`プロパティシートのページの一覧にオブジェクトを追加しますが、実際にはそのページのウィンドウを作成しません。 そのため、プロパティシートのコンストラクターからを呼び出すことができるように、プロパティシートウィンドウが作成されるまで待つ必要はありません。 `AddPage` `AddPage`

   既定では、プロパティシートに表示されるタブの数がプロパティシートの1行に収まりきらない場合、タブは複数の行にスタックされます。 スタックを無効にするには、パラメーターを **FALSE** に設定して [CPropertySheet:: EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs)を呼び出します。 プロパティシートを作成するときに、を呼び出す必要があり `EnableStackedTabs` ます。

1. [CPropertySheet::D oModal](../mfc/reference/cpropertysheet-class.md#domodal)または[Create](../mfc/reference/cpropertysheet-class.md#create)を呼び出して、プロパティシートを表示します。 `DoModal`を呼び出して、モーダルダイアログボックスとしてプロパティシートを作成します。 [ **作成** ] を呼び出して、モードレスダイアログボックスとしてプロパティシートを作成します。

1. プロパティページとプロパティシートの所有者の間でデータを交換します。 これについては、「 [データの交換](../mfc/exchanging-data.md)」をご覧ください。

プロパティシートの使用方法の例については、MFC の一般的なサンプル [PROPDLG](../overview/visual-cpp-samples.md)を参照してください。

## <a name="see-also"></a>関連項目

[プロパティシート](../mfc/property-sheets-mfc.md)
