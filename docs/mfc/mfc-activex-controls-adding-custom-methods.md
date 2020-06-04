---
title: 'MFC ActiveX コントロール : カスタム メソッドの追加'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: 88d486248eab5d980463764db34bf40b05b830dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364710"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX コントロール : カスタム メソッドの追加

カスタム メソッドは、stock メソッドとは異なり、 で`COleControl`実装されていません。 コントロールに追加するカスタム メソッドごとに実装を指定する必要があります。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールのユーザーは、コントロール固有のアクションを実行するために、いつでもカスタム メソッドを呼び出すことができます。 カスタム メソッドのディスパッチ マップ エントリは、DISP_FUNCTION形式です。

## <a name="adding-a-custom-method-with-the-add-method-wizard"></a><a name="_core_adding_a_custom_method_with_classwizard"></a>メソッドの追加ウィザードを使用したカスタム メソッドの追加

次の手順では、カスタム メソッド PtInCircle を ActiveX コントロールのスケルトン コードに追加する方法を示します。 PtInCircle は、コントロールに渡される座標が円の内側か外側かを決定します。 この同じ手順を使用して、他のカスタム メソッドを追加することもできます。 カスタム メソッド名とそのパラメーターを、PtInCircle メソッド名とパラメーターに置き換えます。

> [!NOTE]
> この例では、`InCircle`記事「イベント」の関数を使用します。 この関数の詳細については[、「MFC ActiveX コントロール : ActiveX コントロールへのカスタム イベントの追加](../mfc/mfc-activex-controls-adding-custom-events.md)」を参照してください。

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>メソッドの追加ウィザードを使用して PtInCircle カスタム メソッドを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**メソッドの追加**] をクリックします。

   メソッドの追加ウィザードが開きます。

1. [**メソッド名**] ボックス*に「PtInCircle」* と入力します。

1. [**内部名]** ボックスに、メソッドの内部関数の名前を入力するか、既定値 (この場合は*PtInCircle)* を使用します。

1. [**戻り値の型]** ボックスで、メソッドの戻り値の型に対して **[VARIANT_BOOL]** をクリックします。

1. **[パラメーターの型]** コントロールと **[パラメーター名]** コントロールを使用して *、xCoord*という名前のパラメーターを*追加します*(OLE_XPOS_PIXELS と入力します)。

1. **[パラメーターの種類]** コントロールと **[パラメーター名]** コントロールを使用して *、yCoord*という名前のパラメーターを*追加します*(OLE_YPOS_PIXELS と入力します)。

1. **[完了]** をクリックします。

## <a name="add-method-wizard-changes-for-custom-methods"></a><a name="_core_classwizard_changes_for_custom_methods"></a>カスタム メソッドのメソッド ウィザードの変更の追加

カスタム メソッドを追加すると、メソッドの追加ウィザードによってコントロール クラス ヘッダー (.H) および実装 (.CPP) ファイル。 次の行がコントロール クラス ヘッダーのディスパッチ マップ宣言に追加されます (.H) ファイル:

[!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

このコードは、 というディスパッチ`PtInCircle`メソッド ハンドラーを宣言します。 この関数は、外部名`PtInCircle`を使用してコントロール ユーザーが呼び出すことができます。

次の行がコントロールの に追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

この行は、メソッド`PtInCircle`に特定の ID 番号を割り当て、メソッドの追加ウィザードのメソッドとプロパティの一覧でのメソッドの位置を割り当てます。 メソッドの追加ウィザードを使用してカスタム メソッドを追加したため、そのエントリはプロジェクトの .IDL ファイル。

さらに、実装内に配置される以下の行(.コントロール クラスの CPP) ファイルがコントロールのディスパッチ マップに追加されます。

[!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

DISP_FUNCTION`PtInCircle`マクロは、メソッドをコントロールのハンドラー関数にマップし、`PtInCircle`戻り値の型を**VARIANT_BOOL**宣言し **、VTS_XPOS_PIXELS**型の 2 つのパラメーターを宣言し **、VTS_YPOSPIXELS**に`PtInCircle`渡す。

最後に、メソッドの追加ウィザードは、スタブ`CSampleCtrl::PtInCircle`関数をコントロールの実装の一番下に追加します (.CPP) ファイル。 前述`PtInCircle`のように機能するには、次のように変更する必要があります。

[!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[クラス ビューとオブジェクト ブラウザのアイコン](/visualstudio/ide/class-view-and-object-browser-icons)
