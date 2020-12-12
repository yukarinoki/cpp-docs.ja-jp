---
description: '詳細については、「MFC ActiveX コントロール: ストックメソッドの追加」を参照してください。'
title: 'MFC ActiveX コントロール : ストック メソッドの追加'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: 1bd176c81a3c97ad5530a9b1971656e5204fe407
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202874"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX コントロール : ストック メソッドの追加

ストックメソッドは、クラスによって既に実装 [されて](reference/colecontrol-class.md)いるので、カスタムメソッドとは異なります。 たとえば、には、 `COleControl` コントロールの Refresh メソッドをサポートする定義済みのメンバー関数が含まれています。 このストックメソッドのディスパッチマップエントリは DISP_STOCKFUNC_REFRESH です。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

`COleControl` では、DoClick と Refresh の2つのストックメソッドがサポートされています。 コントロールのユーザーが更新を呼び出して、コントロールの外観を直ちに更新します。DoClick を呼び出して、コントロールの Click イベントを発生させます。

|Method|ディスパッチマップエントリ|コメント|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK ()**|Click イベントを発生します。|
|`Refresh`|**DISP_STOCKPROP_REFRESH ()**|コントロールの外観を直ちに更新します。|

## <a name="adding-a-stock-method-using-the-add-method-wizard"></a><a name="_core_adding_a_stock_method_using_classwizard"></a> メソッドの追加ウィザードを使用したストックメソッドの追加

ストックメソッドの追加は、メソッドの [追加ウィザード](../ide/adding-a-method-visual-cpp.md#add-method-wizard)を使用して簡単に行うことができます。 次の手順は、MFC ActiveX コントロールウィザードを使用して作成されたコントロールに Refresh メソッドを追加する方法を示しています。

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>メソッドの追加ウィザードを使用して stock Refresh メソッドを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **メソッドの追加**] をクリックします。

   メソッドの追加ウィザードが開きます。

1. [ **メソッド名** ] ボックスで、[最新の状態に **更新**] をクリックします。

1. **[完了]** をクリックします。

## <a name="add-method-wizard-changes-for-stock-methods"></a><a name="_core_classwizard_changes_for_stock_methods"></a> ストックメソッドのメソッドの追加ウィザードの変更

Stock Refresh メソッドはコントロールの基本クラスでサポートされているため、 **メソッドの追加ウィザード** では、コントロールのクラス宣言がどのようにも変更されません。 このメソッドは、コントロールのディスパッチマップとそのにメソッドのエントリを追加します。IDL ファイル。 実装 () にあるコントロールのディスパッチマップに、次の行が追加されます。CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#16](codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

これにより、コントロールのユーザーが Refresh メソッドを使用できるようになります。

次の行がコントロールのに追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#17](codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

この行によって、更新メソッドに特定の ID 番号が割り当てられます。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
