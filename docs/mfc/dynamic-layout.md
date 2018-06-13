---
title: 動的レイアウト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7518e2fdd07254b8b1991fae8a41f26058920858
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350850"
---
# <a name="dynamic-layout"></a>動的レイアウト
Visual Studio 2015 で MFC をユーザーがダイアログを作成してサイズの変更に合わせてレイアウトを調整する方法を制御することができます。 たとえば、ボタンをダイアログの下の端に付けて、常にダイアログ ボックスの下部に配置されるようにすることができます。 ユーザーがダイアログを展開するときに、リスト ボックス、エディット ボックス、テキスト フィールドなどの特定のコントロールを展開するように設定することもできます。  
  
## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>MFC ダイアログ ボックスのレイアウトの動的な設定を指定する  
 ユーザーがダイアログ ボックスをサイズ変更するときに、ダイアログのコントロールのサイズを変更したり、X と Y の方向に移動したりできます。 ユーザーがダイアログ ボックスのサイズを変更するときのコントロールのサイズや位置の変更は、動的レイアウトと呼ばれます。 たとえば、次に示すのはサイズを変更する前のダイアログです。  
  
 ![サイズ変更される前にダイアログ ボックス。] (../mfc/media/mfcdynamiclayout4.png "mfcdynamiclayout4")  
  
 サイズを変更した後で、リスト ボックス領域がより多くの項目を表示するよう増え、ボタンは右下隅に沿って移動します。  
  
 ![サイズを変更した後のダイアログ。] (../mfc/media/mfcdynamiclayout5.png "mfcdynamiclayout5")  
  
 IDE のリソース エディターの各コントロールの詳細を指定して、動的レイアウトを制御することも、特定のコントロールの CMFCDynamicLayout オブジェクトにアクセスしてプロパティを設定し、プログラムで制御することもできます。  
  
### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>リソース エディターで動的レイアウト プロパティを設定する  
 リソース エディターを使用すると、コードを記述しなくても、ダイアログ ボックス動的のレイアウトの動作を設定できます。  
  
##### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>動的レイアウトのプロパティをリソース エディターで設定するには  
  
1.  MFC プロジェクトを開いた状態にして、ダイアログ エディターで作業するダイアログ ボックスを開きます。  
  
     ![リソース エディターでダイアログを開きます。] (../mfc/media/mfcdynamiclayout3.png "mfcdynamiclayout3")  
  
2.  コントロールを選択し、[プロパティ] ウィンドウで、その動的レイアウト プロパティを設定します。 **動的レイアウト**プロパティ ウィンドウでセクションには、プロパティが含まれています**移動の種類**、**サイズ変更の種類**、し、それらのプロパティを、選択した値に応じて。コントロールが移動またはサイズを変更する量を定義する特定のプロパティです。 **型の移動**コントロールを移動するかを判断、ダイアログのサイズが変更される; と**サイズ変更の種類**コントロールを変更する方法を決定する、ダイアログのサイズが変更されるとします。 **型の移動**と**サイズ変更の種類**可能性があります**水平**、**垂直**、**両方**、または**None**に応じて動的に変化するディメンションです。 [水平] は X 方向、[垂直] はY 方向です。  
  
3.  固定サイズであるし、右下の場所に維持するためのボタンなどのコントロールを実行する場合に、同様が一般的、 **OK**または**キャンセル**ボタン、設定、**サイズ変更の種類**に**None**、設定と、**移動の種類**に**両方**です。 **X の移動**と**Y の移動**下にある値**移動の種類**100% まま下部から一定の距離の右下隅にコントロールを設定します。  
  
     ![動的レイアウト](../mfc/media/mfcdynamiclayout1.png "mfcdynamiclayout1")  
  
4.  ダイアログ ボックスの拡張と共に拡張させたいコントロールがあるとします。 通常、複数行の編集ボックスを拡張して、テキスト領域のサイズを増やすために、ダイアログを拡張するか、より多くのデータを表示するために、リスト コントロールを拡張します。 この場合、次のように設定します。、**サイズ変更の種類**、両方に設定し、**移動の種類**[なし] にします。 次に、設定、 **X のサイズ変更**と**Y のサイズ変更**100 の値。  
  
     ![動的レイアウト設定](../mfc/media/mfcdynamiclayout2.png "mfcdynamiclayout2")  
  
5.  コントロールにとって意味がある可能性のあるその他の値をテストします。 1 行のテキスト ボックスとダイアログ ボックスがあります、**サイズ変更の種類**'éý'**水平**例についてのみ、します。  
  
### <a name="setting-dynamic-layout-properties-programmatically"></a>プログラムによる動的レイアウト プロパティの設定  
 前の手順は、デザイン時にダイアログの動的レイアウト プロパティを指定するには便利ですが、動的レイアウト プロパティを実行時に制御したい場合は、動的レイアウト プロパティをプログラムで設定できます。  
  
##### <a name="to-set-dynamic-layout-properties-programmatically"></a>動的レイアウト プロパティをプログラムによって設定するには  
  
1.  ダイアログの動的レイアウトを指定する、ダイアログ クラスの実装コードの場所を検索または作成します。 たとえば、ダイアログに `AdjustLayout` などのメソッドを追加して、レイアウトを変更する必要がある場所から呼び出すことができます。 最初にこれをコンストラクターから呼び出すか、ダイアログに変更を加えた後で呼び出すことができます。  
  
2.  ダイアログで、呼び出す[GetDynamicLayout](../mfc/reference/cwnd-class.md#getdynamiclayout)、CWnd クラスのメソッドです。 GetDynamicLayout は、CMFCDynamicLayout オブジェクトへのポインターを返します。  
  
 ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();

 ```  
  
3.  動的な動作を追加する最初のコントロールの静的メソッドのクラスを使用、動的レイアウトを作成、 [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure)コントロールを調整する方法をエンコードする構造体。 最初に適切な静的メソッドを選択してこれを行う: [CMFCDynamicLayout::MoveHorizontal](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal)、 [CMFCDynamicLayout::MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical)、 [CMFCDynamicLayout::MoveNone](../mfc/reference/cmfcdynamiclayout-class.md#movenone)、または[CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical)です。 移動の水平/垂直方向のアスペクト比率を渡します。 これらすべての静的メソッドは、コントロールの移動の動作を指定する時に使用できる、新しく作成された MoveSettings オブジェクトを返します。  
  
     100 にするとダイアログのサイズ変更とまったく同じサイズの移動を行い、これによりコントロールのエッジが新しい境界からの固定距離を維持します。  
  
 ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);

 ```  
  
4.  サイズなどの動作を使用して同じ操作を行う、 [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure)型です。 たとえば、ダイアログ ボックスのサイズを変更するときにコントロールがサイズを変更しないよう指定するには、次のコードを使用します。  
  
 ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();

 ```  
  
5.  コントロールを使用して、動的レイアウト マネージャーを追加、 [cmfcdynamiclayout::additem](../mfc/reference/cmfcdynamiclayout-class.md#additem)メソッドです。 目的のコントロールを指定するさまざまな方法に対して、2 つのオーバーロードがあります。 1 つはコントロールのウィンドウ ハンドル (HWND) を取得し、もう 1 つは、コントロールの ID を取得します。  
  
 ```  
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);

 ```  
  
6.  移動またはサイズを変更する必要がある各コントロールに対して繰り返します。  
  
7.  必要に応じて、使用する場合、 [cmfcdynamiclayout::hasitem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem)コントロールが動的レイアウトの変更対象となるコントロールの一覧に既にかどうかを判断するメソッド、または[cmfcdynamiclayout::isempty](../mfc/reference/cmfcdynamiclayout-class.md#isempty)変更される可能性がありますが、コントロールがあるかを確認するメソッドです。  
  
8.  ダイアログのレイアウトを有効にするを呼び出して、 [cwnd::enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout)メソッドです。  
  
 ```  
    pDialog->EnableDynamicLayout(TRUE);

 ```  
  
9. 次回ユーザーが、ダイアログ ボックスをサイズ変更、 [cmfcdynamiclayout::adjust](../mfc/reference/cmfcdynamiclayout-class.md#adjust)実際には、設定を適用するメソッドが呼び出されます。  
  
10. 動的レイアウトを無効にする場合は、呼び出す[cwnd::enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout)で`FALSE`の場合と同様、`bEnabled`パラメーター。  
  
 ```  
    pDialog->EnableDynamicLayout(FALSE);

 ```  
  
##### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>リソース ファイルから動的レイアウトをプログラムで設定するには  
  
1.  使用して、 [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical)メソッドを次の例のように、動的レイアウト情報を指定する、関連するリソース スクリプト ファイル (.rc ファイル) でリソース名を指定します。  
  
 ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");

 ```  
  
     名前付きのリソースは、次の例のように、リソース ファイル内の AFX_DIALOG_LAYOUT エントリの形式のレイアウト情報が含まれているダイアログを参照する必要があります。  
  
 '' *///*//*//AFX_DIALOG_LAYOUT *//  
 
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    0X0000、0X6400、0X0028、0X643C、0X0028 を開始します。  
    End 
 
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    0X0000 0X6464、0X0000、0X6464、0X0000、0X0000、0X6464、0X0000 0X0000 を開始します。  
 
    End 
 ```  
  
## See Also  
 [CMFCDynamicLayout Class](../mfc/reference/cmfcdynamiclayout-class.md)   
 [Control Classes](../mfc/control-classes.md)   
 [Dialog Box Classes](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../windows/dialog-editor.md)

