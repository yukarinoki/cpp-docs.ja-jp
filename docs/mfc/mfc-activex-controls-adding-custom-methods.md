---
title: 'MFC ActiveX コントロール: カスタム メソッドの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cdf264bd0c2aa44bdeecc58b4bc8eb89c70fb91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350034"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX コントロール : カスタム メソッドの追加
カスタム メソッドとは異なりストック メソッドによって実装されていない`COleControl`です。 コントロールを追加する各カスタム メソッドの実装を指定する必要があります。  
  
 ActiveX コントロールのユーザーは、コントロールに固有のアクションを実行するには、いつでもカスタム メソッドを呼び出すことができます。 形式は、カスタム メソッドのディスパッチ マップ エントリ`DISP_FUNCTION`です。  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a> カスタム メソッドを追加する、メソッドの追加ウィザード  
 次の手順では、ActiveX コントロールのスケルトン コードを PtInCircle カスタム メソッドを追加することを示します。 PtInCircle は、コントロールに渡される座標が内側または外側円かどうかを判断します。 これと同じ手順は、その他のカスタム メソッドを追加しても使用できます。 PtInCircle メソッドの名前およびパラメーターについては、そのパラメーターのカスタム メソッド名に置き換えます。  
  
> [!NOTE]
>  この例では、`InCircle`記事イベントからの関数。 この関数の詳細については、記事を参照してください。 [MFC ActiveX コントロール: ActiveX コントロールのカスタム イベントの追加](../mfc/mfc-activex-controls-adding-custom-events.md)です。  
  
#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>メソッド追加ウィザードを使用して、PtInCircle カスタム メソッドを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューから **[追加]** をクリックし、**メソッドの追加**です。  
  
     メソッド追加ウィザードが開きます。  
  
5.  **メソッド名**ボックスに、入力`PtInCircle`です。  
  
6.  **内部名**ボックスで、メソッドの内部関数の名前を入力するか、既定値を使用して (この場合、 `PtInCircle`)。  
  
7.  **戻り値の型**ボックスで、クリックして**VARIANT_BOOL**メソッドの戻り値の型。  
  
8.  使用して、**パラメーターの型**と**パラメーター名**コントロール、という名前のパラメーターを追加する`xCoord`(型**OLE_XPOS_PIXELS**)。  
  
9. 使用して、**パラメーターの型**と**パラメーター名**コントロール、という名前のパラメーターを追加する`yCoord`(型**OLE_YPOS_PIXELS**)。  
  
10. **[完了]** をクリックします。  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a> カスタム メソッドのメソッド ウィザードの変更を追加します。  
 メソッド追加ウィザードにはコントロール クラスのヘッダーをいくつかの変更がカスタム メソッドを追加すると (です。H) と実装 (です。CPP) ファイル。 ディスパッチ マップ宣言では、コントロール クラスのヘッダーに、次の行が追加されます (です。H) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]  
  
 このコードと呼ばれるディスパッチ メソッド ハンドラー`PtInCircle`です。 PtInCircle 外部名を使用してコントロールのユーザーによるこの関数を呼び出すことができます。  
  
 コントロールの次の行が追加されます。IDL ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]  
  
 この行は、特定の ID 番号、メソッド追加ウィザードのメソッドとプロパティのリスト内のメソッドの位置を PtInCircle メソッドに割り当てます。 メソッド追加ウィザードを使用、カスタム メソッドを追加するため、プロジェクトにエントリが自動的に追加されました。IDL ファイルです。  
  
 さらに、次の行はクラスの実装 (です。コントロールのクラス、CPP) ファイルは、コントロールのディスパッチ マップに追加されます。  
  
 [!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]  
  
 `DISP_FUNCTION`マクロ メソッド PtInCircle をコントロールのハンドラー関数にマップする`PtInCircle`、するのには、戻り値の型を宣言して**VARIANT_BOOL**、型の 2 つのパラメーターを宣言および**VTS_XPOS_PIXELS**と**VTS_YPOSPIXELS**に渡される`PtInCircle`です。  
  
 メソッド追加ウィザードが最後に、スタブ関数を追加`CSampleCtrl::PtInCircle`コントロールの実装の最下位に (です。CPP) ファイルです。 `PtInCircle`前述したように機能するために変更する必要が次のようにします。  
  
 [!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [[クラス ビュー] ウィンドウとオブジェクト ブラウザーのアイコン](/visualstudio/ide/class-view-and-object-browser-icons)

