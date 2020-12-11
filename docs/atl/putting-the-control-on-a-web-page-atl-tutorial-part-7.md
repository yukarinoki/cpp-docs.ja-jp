---
description: 詳細については、「Web ページにコントロールを配置する (ATL チュートリアル、パート 7)」を参照してください。
title: Web ページへのコントロールの配置 (ATL チュートリアル、パート 7)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: 738d847a6436a2afab2e336502ec3255d1a1e589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159180"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Web ページへのコントロールの配置 (ATL チュートリアル、パート 7)

これで、コントロールが完成しました。 コントロールの動作を実際の環境で確認するには、Web ページに配置します。 コントロールを含む HTML ファイルは、コントロールを定義したときに作成されています。 **ソリューションエクスプローラー** から PolyCtl.htm ファイルを開くと、Web ページにコントロールが表示されます。

このステップでは、コントロールに機能を追加し、イベントに応答するように Web ページをスクリプト化します。 また、コントロールを変更して、Internet Explorer がスクリプトに対して安全であることを知らせます。

## <a name="adding-new-functionality"></a>新機能の追加

### <a name="to-add-control-features"></a>コントロール機能を追加するには

1. Polyctl.htm を開き、次のコードを置き換えます。

    ```cpp
    if (PtInRegion(hRgn, xPos, yPos))
        Fire_ClickIn(xPos, yPos);
    else
        Fire_ClickOut(xPos, yPos);
    ```

    with

    ```cpp
    short temp = m_nSides;
    if (PtInRegion(hRgn, xPos, yPos))
    {
        Fire_ClickIn(xPos, yPos);
        put_Sides(++temp);
    }
    else
    {
        Fire_ClickOut(xPos, yPos);
        put_Sides(--temp);
    }
    ```

これで、クリックした場所に応じて図形の辺が追加または削除されるようになります。

## <a name="scripting-the-web-page"></a>Web ページのスクリプティング

コントロールはまだ何も実行しないので、送信したイベントに応答するように Web ページを変更します。

### <a name="to-script-the-web-page"></a>Web ページをスクリプティングするには

1. PolyCtl.htm を開き、HTML ビューを選択します。 次のコードを HTML コードに追加します。 追加する場所は `</OBJECT>` の後、`</BODY>` の前です。

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - adding side")
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - removing side")
        End Sub
    -->
    </SCRIPT>
    ```

1. HTM ファイルを保存します。

コントロールから側のプロパティを取得する VBScript コードを追加しました。 コントロール内をクリックすると、辺の数が1ずつ増加します。 コントロールの外側がクリックされた場合は、辺の数を 1 ずつ減らします。

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>コントロールのスクリプトが安全であることを示す

Internet Explorer でのみ、コントロールを使用して Web ページを表示できます。 他のブラウザーでは、セキュリティの脆弱性により、ActiveX コントロールをサポートしなくなりました。

> [!NOTE]
> コントロールが表示されていない場合は、一部のブラウザーで ActiveX コントロールを実行するための設定の調整が必要であることを確認します。 ActiveX コントロールを有効にする方法については、ブラウザーのドキュメントを参照してください。

現在の Internet Explorer のセキュリティ設定に基づき、[セキュリティの警告] ダイアログボックスが表示される場合があります。 これは、コントロールがスクリプトに対して安全ではなく、損害を及ぼす可能性があることを示しています。 たとえば、ファイルを表示するコントロールに、ファイルを削除する `Delete` メソッドも含まれている場合、このコントロールは、ページを表示するだけの場合は安全です。 ただし、`Delete` メソッドが呼び出される可能性もあるため、このコントロールのスクリプトは安全ではありません。

> [!IMPORTANT]
> このチュートリアルでは、安全としてマークされていない ActiveX コントロールを実行できるように、Internet Explorer のセキュリティ設定を変更できます。 [コントロールパネル] の [ **インターネットのプロパティ** ] をクリックし、[ **セキュリティ** ] をクリックして適切な設定を変更します。 チュートリアルを完了したら、セキュリティ設定を元の状態に戻してください。

この特定のコントロールの [セキュリティの警告] ダイアログボックスを表示する必要がないことを、プログラムによって Internet Explorer に通知できます。 これは、インターフェイスを使用して行うことができ `IObjectSafety` ます。 ATL では、 [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)クラスにこのインターフェイスの実装が用意されています。 インターフェイスをコントロールに追加するには、 `IObjectSafetyImpl` 継承されたクラスのリストにを追加し、そのエントリを COM マップに追加します。

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>コントロールに IObjectSafetyImpl を追加するには

1. PolyCtl.h で、継承するクラスのリストの末尾に次の行を追加し、直前の行にコンマを追加します。

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. PolyCtl.h の COM マップに次の行を追加します。

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト

コントロールをビルドします。 ビルドが完了したら、PolyCtl.htm をブラウザー ビューで再度開きます。 今度は、[ **安全性の警告** ] ダイアログボックスを表示せずに、Web ページを直接表示する必要があります。 多角形の内側をクリックすると、辺の数が1ずつ増えます。 多角形の外側をクリックすると、辺の数が減ります。

[ステップ 6 に戻る](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>次の手順

この手順では、ATL チュートリアルを終了します。 ATL の詳細情報へのリンクについては、 [atl のスタートページ](../atl/active-template-library-atl-concepts.md)を参照してください。

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
