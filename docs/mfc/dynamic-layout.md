---
title: 動的レイアウト
ms.date: 09/09/2019
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
ms.openlocfilehash: 3108e7bae0be216dfb877d03c87fdc17ef7d69f2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624760"
---
# <a name="dynamic-layout"></a>動的レイアウト

Visual Studio 2015 の MFC では、ユーザーがサイズ変更できるダイアログを作成できます。また、レイアウトがサイズの変更に合わせてどのように調整されるかを制御できます。 たとえば、ボタンをダイアログの下の端に付けて、常にダイアログ ボックスの下部に配置されるようにすることができます。 ユーザーがダイアログを展開するときに、リスト ボックス、エディット ボックス、テキスト フィールドなどの特定のコントロールを展開するように設定することもできます。

## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>MFC ダイアログ ボックスのレイアウトの動的な設定を指定する

ユーザーがダイアログ ボックスをサイズ変更するときに、ダイアログのコントロールのサイズを変更したり、X と Y の方向に移動したりできます。 ユーザーがダイアログ ボックスのサイズを変更するときのコントロールのサイズや位置の変更は、動的レイアウトと呼ばれます。 たとえば、次に示すのはサイズを変更する前のダイアログです。

![サイズ変更する前のダイアログ。](../mfc/media/mfcdynamiclayout4.png "サイズ変更する前のダイアログ。")

サイズを変更した後で、リスト ボックス領域がより多くの項目を表示するよう増え、ボタンは右下隅に沿って移動します。

![サイズ変更した後のダイアログ。](../mfc/media/mfcdynamiclayout5.png "サイズ変更した後のダイアログ。")

IDE のリソースエディターで各コントロールの詳細を指定することによって動的レイアウトを制御できます。また、特定のコントロールのオブジェクトにアクセスしてプロパティを設定することによって、プログラムによってレイアウトを制御することもできます `CMFCDynamicLayout` 。

### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>リソース エディターで動的レイアウト プロパティを設定する

リソース エディターを使用すると、コードを記述しなくても、ダイアログ ボックス動的のレイアウトの動作を設定できます。

#### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>動的レイアウトのプロパティをリソース エディターで設定するには

1. MFC プロジェクトを開いた状態にして、ダイアログ エディターで作業するダイアログ ボックスを開きます。

   ![リソース エディターのダイアログを開きます。](../mfc/media/mfcdynamiclayout3.png "リソース エディターのダイアログを開きます。")

1. コントロールを選択し、[**プロパティ**] ウィンドウ (**クラスビュー**) で、動的レイアウトプロパティを設定します。 [**プロパティ**] ウィンドウの [**動的レイアウト**] セクションには、[**移動の種類**]、[サイズ変更の**種類**]、および [プロパティ] で選択した値に応じて、サイズを移動または変更するコントロールの量を定義する特定のプロパティが表示されます。 **移動型**は、ダイアログのサイズが変更されたときにコントロールを移動する方法を決定します。サイズ変更の**種類**によって、ダイアログのサイズが変更されたときにコントロールのサイズがどのように変更されるかが決まります。 動的に変更するディメンションに応じ**て、** 移動の**種類**と**サイズ変更の種類****は、** **水平方向**、**垂直方向**、またはいずれかになります。 [水平] は X 方向、[垂直] はY 方向です。

1. ボタンなどのコントロールを固定サイズにして、右下に配置しておく必要がある場合は ( **[OK]** または **[キャンセル**] ボタンに共通)、 **[サイズ変更の種類**] を **[なし**] に設定し、[**移動の種類**] を [**両方**] に設定します。 [**移動の種類**] で**X**を移動して Y 値を**移動**する場合は、[100%] を設定して、コントロールが右下隅から固定された距離になるようにします。

   ![動的レイアウト](../mfc/media/mfcdynamiclayout1.png "動的レイアウト")

1. ダイアログ ボックスの拡張と共に拡張させたいコントロールがあるとします。 通常、複数行の編集ボックスを拡張して、テキスト領域のサイズを増やすために、ダイアログを拡張するか、より多くのデータを表示するために、リスト コントロールを拡張します。 この場合は、[**サイズ変更の種類**] を [両方] に設定し、[**移動の種類**] を [なし] に設定します。 次に、**サイズ変更 X**と**サイズ変更の Y**値を100に設定します。

   ![動的レイアウト設定](../mfc/media/mfcdynamiclayout2.png "動的レイアウト設定")

1. コントロールにとって意味がある可能性のあるその他の値をテストします。 たとえば、1行のテキストボックスがあるダイアログでは、**サイズ変更の種類**が [**水平方向**のみ] に設定されている場合があります。

### <a name="setting-dynamic-layout-properties-programmatically"></a>プログラムによる動的レイアウト プロパティの設定

前の手順は、デザイン時にダイアログの動的レイアウト プロパティを指定するには便利ですが、動的レイアウト プロパティを実行時に制御したい場合は、動的レイアウト プロパティをプログラムで設定できます。

#### <a name="to-set-dynamic-layout-properties-programmatically"></a>動的レイアウト プロパティをプログラムによって設定するには

1. ダイアログの動的レイアウトを指定する、ダイアログ クラスの実装コードの場所を検索または作成します。 たとえば、ダイアログに `AdjustLayout` などのメソッドを追加して、レイアウトを変更する必要がある場所から呼び出すことができます。 最初にこれをコンストラクターから呼び出すか、ダイアログに変更を加えた後で呼び出すことができます。

1. ダイアログの場合は、クラスのメソッドである[Getdynamiclayout](reference/cwnd-class.md#getdynamiclayout)を呼び出し `CWnd` ます。 `GetDynamicLayout` は `CMFCDynamicLayout` オブジェクトへのポインターを返します。

    ```cpp
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();
    ```

1. 動的な動作を追加する最初のコントロールについては、動的レイアウトクラスの静的メソッドを使用して、コントロールの調整方法をエンコードする[Movesettings](reference/cmfcdynamiclayout-class.md#movesettings_structure)構造体を作成します。 これを行うには、まず、適切な静的メソッドである[Cmfcdynamiclayout:: MoveHorizontal](reference/cmfcdynamiclayout-class.md#movehorizontal)、 [cmfcdynamiclayout:: movehorizontal](reference/cmfcdynamiclayout-class.md#movevertical)、 [Cmfcdynamiclayout:: mo/One](reference/cmfcdynamiclayout-class.md#movenone)、または[Cmfcdynamiclayout:: movehorizontal andvertical](reference/cmfcdynamiclayout-class.md#movehorizontalandvertical)を選択します。 移動の水平/垂直方向のアスペクト比率を渡します。 これらすべての静的メソッドは、コントロールの移動の動作を指定する時に使用できる、新しく作成された MoveSettings オブジェクトを返します。

   100 にするとダイアログのサイズ変更とまったく同じサイズの移動を行い、これによりコントロールのエッジが新しい境界からの固定距離を維持します。

    ```cpp
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);
    ```

1. サイズの動作についても、 [Sizesettings](reference/cmfcdynamiclayout-class.md#sizesettings_structure)型を使用して同じ処理を行います。 たとえば、ダイアログ ボックスのサイズを変更するときにコントロールがサイズを変更しないよう指定するには、次のコードを使用します。

    ```cpp
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();
    ```

1. [Cmfcdynamiclayout:: AddItem](reference/cmfcdynamiclayout-class.md#additem)メソッドを使用して、コントロールを動的レイアウトマネージャーに追加します。 目的のコントロールを指定するさまざまな方法に対して、2 つのオーバーロードがあります。 1 つはコントロールのウィンドウ ハンドル (HWND) を取得し、もう 1 つは、コントロールの ID を取得します。

    ```cpp
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);
    ```

1. 移動またはサイズを変更する必要がある各コントロールに対して繰り返します。

1. 必要に応じて、は、 [Cmfcdynamiclayout:: HasItem](reference/cmfcdynamiclayout-class.md#hasitem)メソッドを使用して、コントロールが動的レイアウトの変更に依存するコントロールのリストに既に存在するかどうかを判断したり、 [Cmfcdynamiclayout:: IsEmpty](reference/cmfcdynamiclayout-class.md#isempty)メソッドを使用して変更の対象となるコントロールがあるかどうかを判断したりできます。

1. ダイアログのレイアウトを有効にするには、 [CWnd:: EnableDynamicLayout](reference/cwnd-class.md#enabledynamiclayout)メソッドを呼び出します。

    ```cpp
    pDialog->EnableDynamicLayout(TRUE);
    ```

1. 次にユーザーがダイアログのサイズを変更したときに、 [Cmfcdynamiclayout:: アジャスト](reference/cmfcdynamiclayout-class.md#adjust)メソッドが呼び出され、実際に設定が適用されます。

1. 動的レイアウトを無効にする場合は、 *Benabled*パラメーターに**FALSE**を指定して[CWnd:: enabledynamiclayout](reference/cwnd-class.md#enabledynamiclayout)を呼び出します。

    ```cpp
    pDialog->EnableDynamicLayout(FALSE);
    ```

#### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>リソース ファイルから動的レイアウトをプログラムで設定するには

1. 次の例に示すように、 [Cmfcdynamiclayout:: Move横軸 Andvertical](reference/cmfcdynamiclayout-class.md#movehorizontalandvertical)メソッドを使用して、関連するリソーススクリプトファイル (.rc ファイル) で動的レイアウト情報を指定するリソース名を指定します。

    ```cpp
    dynamicLayout->LoadResource("IDD_DIALOG1");
    ```

   名前付きリソースは、次の例のように、リソースファイルの**AFX_DIALOG_LAYOUT**エントリの形式でレイアウト情報を含むダイアログを参照する必要があります。

    ```RC
    /////////////////////////////////////////////////////////////////////////////
    //
    // AFX_DIALOG_LAYOUT
    //

    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT
    BEGIN
    0x0000,
    0x6400,
    0x0028,
    0x643c,
    0x0028
    END

    IDD_DIALOG1 AFX_DIALOG_LAYOUT
    BEGIN
    0x0000,
    0x6464,
    0x0000,
    0x6464,
    0x0000,
    0x0000,
    0x6464,
    0x0000,
    0x0000

    END
    ```

## <a name="see-also"></a>関連項目

[CMFCDynamicLayout クラス](reference/cmfcdynamiclayout-class.md)<br/>
[コントロール クラス](control-classes.md)<br/>
[ダイアログ ボックス クラス](dialog-box-classes.md)<br/>
[ダイアログエディター](../windows/dialog-editor.md)<br/>
[Visual C++ 2015 の MFC の動的ダイアログレイアウト](https://mariusbancila.ro/blog/2015/07/27/dynamic-dialog-layout-for-mfc-in-visual-c-2015/)
