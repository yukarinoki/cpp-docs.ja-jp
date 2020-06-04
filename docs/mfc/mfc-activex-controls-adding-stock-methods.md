---
title: 'MFC ActiveX コントロール : ストック メソッドの追加'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: ec59ccc0cbd48fc3114eb2dc0833dd3dd65691de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364668"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX コントロール : ストック メソッドの追加

ストック メソッドは、既にクラス[COleControl](../mfc/reference/colecontrol-class.md)によって実装されているカスタム メソッドとは異なります。 たとえば、`COleControl`コントロールの Refresh メソッドをサポートする定義済みのメンバー関数が含まれています。 このストックメソッドのディスパッチマップエントリはDISP_STOCKFUNC_REFRESH。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

`COleControl`は、DoClick と更新の 2 つのストック方法をサポートしています。 更新は、コントロールのユーザーによって呼び出され、コントロールの外観をすぐに更新します。DoClick が呼び出され、コントロールの Click イベントが発生します。

|Method|ディスパッチ マップ エントリ|解説|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK( )**|Click イベントを発生させます。|
|`Refresh`|**DISP_STOCKPROP_REFRESH( )**|コントロールの外観を直ちに更新します。|

## <a name="adding-a-stock-method-using-the-add-method-wizard"></a><a name="_core_adding_a_stock_method_using_classwizard"></a>メソッドの追加ウィザードを使用したストック メソッドの追加

ストック メソッドの追加は、[メソッドの追加ウィザード](../ide/add-method-wizard.md)を使用して簡単に行えます。 次の手順では、MFC ActiveX コントロール ウィザードを使用して作成したコントロールに Refresh メソッドを追加する方法を示します。

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>メソッドの追加ウィザードを使用してストック Refresh メソッドを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**メソッドの追加**] をクリックします。

   メソッドの追加ウィザードが開きます。

1. [**メソッド名**] ボックスの一覧の [**最新の情報に更新**] をクリックします。

1. **[完了]** をクリックします。

## <a name="add-method-wizard-changes-for-stock-methods"></a><a name="_core_classwizard_changes_for_stock_methods"></a>ストック メソッドのメソッド ウィザードの変更の追加

ストック Refresh メソッドはコントロールの基本クラスでサポートされているため、**メソッドの追加ウィザード**では、コントロールのクラス宣言は変更されません。 メソッドのエントリをコントロールのディスパッチ マップとに追加します。IDL ファイル。 次の行は、コントロールの実装内にあるディスパッチ マップに追加されます (.CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

これにより、Refresh メソッドをコントロールのユーザーが使用できるようになります。

次の行がコントロールの に追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

この行は、Refresh メソッドに特定の ID 番号を割り当てます。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
