---
title: 'MFC ActiveX コントロール : カスタム メソッドの追加'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: e32a1c372d89fc4ade414b20a0f77fa162807250
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626157"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX コントロール : カスタム メソッドの追加

カスタムメソッドは、によってまだ実装されていないので、ストックメソッドとは異なり `COleControl` ます。 コントロールに追加する各カスタムメソッドの実装を指定する必要があります。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールユーザーは、コントロール固有のアクションを実行するために、いつでもカスタムメソッドを呼び出すことができます。 カスタムメソッドのディスパッチマップエントリの形式は DISP_FUNCTION です。

## <a name="adding-a-custom-method-with-the-add-method-wizard"></a><a name="_core_adding_a_custom_method_with_classwizard"></a>メソッドの追加ウィザードを使用したカスタムメソッドの追加

次の手順では、ActiveX コントロールのスケルトンコードにカスタムメソッド PtInCircle を追加する方法を示します。 PtInCircle は、コントロールに渡された座標が円の内側と外側のどちらにあるかを判断します。 これと同じ手順を使用して、他のカスタムメソッドを追加することもできます。 PtInCircle メソッドの名前とパラメーターには、カスタムメソッド名とそのパラメーターを置き換えます。

> [!NOTE]
> この例では、アーティクルイベントの関数を使用し `InCircle` ます。 この関数の詳細については、「 [MFC Activex コントロール: Activex コントロールへのカスタムイベントの追加](mfc-activex-controls-adding-custom-events.md)」を参照してください。

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>メソッドの追加ウィザードを使用して PtInCircle カスタムメソッドを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [**追加**] をクリックし、[**メソッドの追加**] をクリックします。

   メソッドの追加ウィザードが開きます。

1. [**メソッド名**] ボックスに「 *PtInCircle*」と入力します。

1. [**内部名**] ボックスに、メソッドの内部関数の名前を入力するか、既定値 (この場合は*PtInCircle*) を使用します。

1. [**戻り値の型**] ボックスで、メソッドの戻り値の型として [ **VARIANT_BOOL** ] をクリックします。

1. パラメーターの**型**と**パラメーター名**のコントロールを使用して、 *xcoord* (型*OLE_XPOS_PIXELS*) という名前のパラメーターを追加します。

1. パラメーターの**型**と**パラメーター名**のコントロールを使用して、 *ycoord* (型*OLE_YPOS_PIXELS*) という名前のパラメーターを追加します。

1. **[完了]** をクリックします。

## <a name="add-method-wizard-changes-for-custom-methods"></a><a name="_core_classwizard_changes_for_custom_methods"></a>カスタムメソッドのメソッドの追加ウィザードの変更

カスタムメソッドを追加すると、メソッドの追加ウィザードによって、コントロールクラスヘッダー () が変更されます。H) と実装 (.CPP) ファイル。 次の行は、コントロールクラスヘッダー () のディスパッチマップ宣言に追加されます。H) ファイル:

[!code-cpp[NVC_MFC_AxUI#18](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

このコードは、というディスパッチメソッドハンドラーを宣言 `PtInCircle` します。 この関数は、コントロールユーザーが外部名を使用して呼び出すことができ `PtInCircle` ます。

次の行がコントロールのに追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#19](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

この行によって、メソッドに特定の ID 番号が割り当てられます。これは、メソッドの `PtInCircle` 追加ウィザードのメソッドとプロパティの一覧です。 メソッドの追加ウィザードを使用してカスタムメソッドを追加したため、そのエントリはプロジェクトのに自動的に追加されました。IDL ファイル。

また、実装 () にある次の行も含まれます。CPP) コントロールクラスのファイルがコントロールのディスパッチマップに追加されます。

[!code-cpp[NVC_MFC_AxUI#20](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

DISP_FUNCTION マクロは、メソッドを `PtInCircle` コントロールのハンドラー関数にマップし、 `PtInCircle` **VARIANT_BOOL**する戻り値の型を宣言し、に渡される**VTS_XPOS_PIXELS**と**VTS_YPOSPIXELS**型の2つのパラメーターを宣言し `PtInCircle` ます。

最後に、メソッドの追加ウィザードによって、スタブ関数が `CSampleCtrl::PtInCircle` コントロールの実装の下部 () に追加されます。CPP) ファイル。 が `PtInCircle` 前述のように機能するには、次のように変更する必要があります。

[!code-cpp[NVC_MFC_AxUI#21](codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[クラスビューとオブジェクトブラウザーアイコン](/visualstudio/ide/class-view-and-object-browser-icons)
