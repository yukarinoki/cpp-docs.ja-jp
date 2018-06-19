---
title: 'MFC ActiveX コントロール: ストック プロパティの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c51a2efba3c89b4e216fec96459b14c3d0c637d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357560"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX コントロール : ストック プロパティの追加
ストック プロパティは、クラスによって既に実装されている点で、カスタム プロパティとは異なります。`COleControl`です。 `COleControl` コントロールの共通プロパティをサポートする定義済みのメンバー関数が含まれています。 一部の共通プロパティには、コントロールのキャプションと、前景色と背景色が含まれます。 その他のストック プロパティについては、次を参照してください。[プロパティの追加ウィザードでサポートするストック プロパティ](#_core_stock_properties_supported_by_classwizard)この記事で後述します。 ストック プロパティのディスパッチ マップ エントリが常に付けた**DISP_STOCKPROP**です。  
  
 この記事では、(ここで、キャプション) ストック プロパティのプロパティの追加ウィザードを使用して ActiveX コントロールを追加する方法について説明し、結果として得られるコードの変更について説明します。 ここでは、次の内容について説明します。  
  
-   [ストック プロパティを追加するプロパティの追加ウィザードを使用します。](#_core_using_classwizard_to_add_a_stock_property)  
  
-   [ストック プロパティのプロパティ ウィザードによる変更を追加します。](#_core_classwizard_changes_for_stock_properties)  
  
-   [プロパティの追加ウィザードでサポートされるストック プロパティ](#_core_stock_properties_supported_by_classwizard)  
  
-   [ストック プロパティと通知](#_core_stock_properties_and_notification)  
  
-   [色のプロパティ](#_core_color_properties)  
  
    > [!NOTE]
    >  Visual Basic のカスタム コントロールには、通常、Top、Left、幅、高さ、配置、タグ、名、TabIndex、TabStop、および親などプロパティがあります。 ActiveX コントロール コンテナーがこれらのコントロール プロパティの実装を担当し、したがって ActiveX コントロールではこれらのプロパティをサポートしません。  
  
##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> 使用して、プロパティの追加ウィザードのストック プロパティを追加するには  
 ストック プロパティを追加するために、カスタム プロパティを追加するよりも少ないコードが必要です、プロパティがによって自動的に処理のサポートを`COleControl`です。 次の手順を使用して、ActiveX コントロール フレームワークへのストック キャプション プロパティの追加を示します、他のストック プロパティを追加するも使用できます。 キャプションのストック プロパティが選択されている名前に置き換えます。  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用して在庫のキャプション プロパティを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューから **[追加]** をクリックし、**プロパティの追加**です。  
  
     開き、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)です。  
  
5.  **プロパティ名**ボックスで、クリックして**キャプション**です。  
  
6.  **[完了]** をクリックします。  
  
##  <a name="_core_classwizard_changes_for_stock_properties"></a> ストック プロパティのプロパティ ウィザードによる変更を追加します。  
 `COleControl`サポートするストック プロパティ、プロパティの追加ウィザードには、任意の方法で、クラス宣言は変わりません。 ディスパッチ マップにプロパティを追加します。 プロパティの追加ウィザードでは、実装にあるコントロールのディスパッチ マップに次の行を追加 (です。Cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]  
  
 コントロールのインターフェイスの説明を次の行が追加されます (です。IDL) ファイル。  
  
 [!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]  
  
 特定の ID の Caption プロパティに割り当てます。 この行 プロパティはバインド可能であり、値を変更する前に、データベースからアクセス許可を要求に注意してください。  
  
 利用 Caption プロパティをコントロールのユーザーにします。 ストック プロパティの値を使用して、メンバー変数またはのメンバー関数にアクセス、`COleControl`基本クラスです。 これらのメンバー変数とメンバー関数の詳細については、プロパティの追加ウィザードでサポートするストック プロパティの次のセクションを参照してください。  
  
##  <a name="_core_stock_properties_supported_by_classwizard"></a> ストック プロパティでサポートされている、プロパティの追加ウィザード  
 `COleControl`クラスには、9 つのストック プロパティが用意されています。 プロパティの追加ウィザードを使用して必要なプロパティを追加することができます。  
  
|プロパティ|ディスパッチ マップ エントリ|値にアクセスする方法|  
|--------------|------------------------|-------------------------|  
|**外観**|**DISP_STOCKPROP_APPEARANCE に関するページ)**|値としてアクセスできる**m_sAppearance**です。|  
|`BackColor`|**DISP_STOCKPROP_BACKCOLOR に関するページ)**|呼び出すことによってアクセス可能な値`GetBackColor`です。|  
|`BorderStyle`|**DISP_STOCKPROP_BORDERSTYLE に関するページ)**|値としてアクセスできる**m_sBorderStyle**です。|  
|**[キャプション]**|**DISP_STOCKPROP_CAPTION に関するページ)**|呼び出すことによってアクセス可能な値`InternalGetText`です。|  
|**有効**|**DISP_STOCKPROP_ENABLED に関するページ)**|値としてアクセスできる**m_bEnabled**です。|  
|**フォント**|**DISP_STOCKPROP_FONT に関するページ)**|記事を参照して[MFC ActiveX コントロール: フォントの使用](../mfc/mfc-activex-controls-using-fonts.md)使用法をします。|  
|`ForeColor`|**DISP_STOCKPROP_FORECOLOR に関するページ)**|呼び出すことによってアクセス可能な値`GetForeColor`です。|  
|**hWnd**|**DISP_STOCKPROP_HWND に関するページ)**|値としてアクセスできる`m_hWnd`です。|  
|**[テキスト]**|**DISP_STOCKPROP_TEXT に関するページ)**|呼び出すことによってアクセス可能な値`InternalGetText`です。 このプロパティは、同じ**キャプション**プロパティ名を除く。|  
|**ReadyState**|**DISP_STOCKPROP_READYSTATE()**|M_lReadyState としてアクセス可能な値または `GetReadyState`|  
  
##  <a name="_core_stock_properties_and_notification"></a> ストック プロパティと通知  
 ほとんどのストック プロパティでは、オーバーライド可能な通知関数があります。 たとえば、ときに、`BackColor`プロパティを変更すると、`OnBackColorChanged`関数 (コントロールのクラス メンバー関数) が呼び出されます。 既定の実装 (で`COleControl`) 呼び出し`InvalidateControl`です。 このような状況への応答でその他のアクションを実行する場合は、この関数をオーバーライドします。  
  
##  <a name="_core_color_properties"></a> 色のプロパティ  
 素材を使用する`ForeColor`と`BackColor`プロパティ、または、独自のカスタムの色のプロパティ、コントロールを描画するときにします。 色のプロパティを使用するのには、呼び出し、 [COleControl::TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor)メンバー関数。 この関数のパラメーターは、カラー プロパティとオプションのパレット ハンドルの値です。 戻り値は、 **COLORREF** GDI に渡すことができる値などの関数、`SetTextColor`と`CreateSolidBrush`です。  
  
 株式のカラー値`ForeColor`と`BackColor`プロパティにアクセスするかを呼び出すことによって、`GetForeColor`または`GetBackColor`関数は、それぞれします。  
  
 次の例では、コントロールを描画するときにこれら 2 つのカラー プロパティの使用を示します。 一時的な初期化**COLORREF**変数および`CBrush`オブジェクトへの呼び出しを`TranslateColor`: 1 つを使用して、`ForeColor`プロパティおよびその他の使用方法、`BackColor`プロパティです。 一時的な`CBrush`コントロールの四角形を描画するオブジェクトを使用してを使用してテキストの色を設定、`ForeColor`プロパティです。  
  
 [!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
