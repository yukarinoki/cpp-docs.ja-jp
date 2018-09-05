---
title: Web ページ (ATL チュートリアル、パート 7) 上のコントロールの配置 |Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edc45522aaff12077de6115105b344ecf41e187e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762825"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Web ページへのコントロールの配置 (ATL チュートリアル、パート 7)

これで、コントロールが完成しました。 コントロールの動作を実際の環境で確認するには、Web ページに配置します。 コントロールを含む HTML ファイルは、コントロールを定義したときに作成されています。 PolyCtl.htm ファイルを開く**ソリューション エクスプ ローラー**、Web ページ上にコントロールを確認できます。

このステップでは、イベントに応答できるように Web ページのスクリプティングを行います。 また、コントロールのスクリプトが安全であることを Internet Explorer に通知できるように、コントロールを変更します。

## <a name="scripting-the-web-page"></a>Web ページのスクリプティング

コントロールではまだ何も実行されないので、送られたイベントに応答できるように、Web ページを変更します。

#### <a name="to-script-the-web-page"></a>Web ページをスクリプティングするには

1. PolyCtl.htm を開き、HTML ビューを選択します。 次のコードを HTML コードに追加します。 追加する場所は `</OBJECT>` の後、`</BODY>` の前です。

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            PolyCtl.Sides = PolyCtl.Sides + 1
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            PolyCtl.Sides = PolyCtl.Sides - 1
        End Sub
    -->
    </SCRIPT>
    ```

2. HTM ファイルを保存します。

追加した VBScript コードでは、コントロールの内側がクリックされるとコントロールから Sides プロパティを取得して辺の数を 1 ずつ増やします。 コントロールの外側がクリックされた場合は、辺の数を 1 ずつ減らします。

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>コントロールのスクリプトが安全であることを示す

コントロールが含まれた Web ページは、Internet Explorer で表示できます。Visual C++ に組み込まれている Web ブラウザー ビューを使用すると、さらに便利です。 Web ブラウザー ビューでコントロールを表示するには、PolyCtl.htm を右クリックし、クリックして**ブラウザーで表示**します。

Internet Explorer の現在のセキュリティ設定によっては、コントロールのスクリプトが安全ではなく、損害を被る危険性があることを示す [セキュリティの警告] ダイアログ ボックスが表示されることがあります。 たとえば、ファイルを表示するコントロールに、ファイルを削除する `Delete` メソッドも含まれている場合、このコントロールは、ページを表示するだけの場合は安全です。 ただし、`Delete` メソッドが呼び出される可能性もあるため、このコントロールのスクリプトは安全ではありません。

> [!IMPORTANT]
> このチュートリアルでは、安全としてマークされていない ActiveX コントロールを実行できるように、Internet Explorer のセキュリティ設定を変更できます。 コントロール パネルで、次のようにクリックします。**インターネット プロパティ** をクリック**セキュリティ**適切な設定を変更します。 チュートリアルを完了したら、セキュリティ設定を元の状態に戻してください。

このコントロールに関しては [セキュリティの警告] ダイアログ ボックスを表示する必要がないことを、Internet Explorer にプログラムで通知することもできます。 これを行うことができます、`IObjectSafety`インターフェイス、および ATL クラスは、このインターフェイスの実装を提供します。 [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)します。 このインターフェイスをコントロールに追加するには、継承するクラスのリストに `IObjectSafetyImpl` を追加し、対応するエントリを COM マップに追加します。

#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>コントロールに IObjectSafetyImpl を追加するには

1. PolyCtl.h で、継承するクラスのリストの末尾に次の行を追加し、直前の行にコンマを追加します。

[!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

2. PolyCtl.h の COM マップに次の行を追加します。

[!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト

コントロールをビルドします。 ビルドが完了したら、PolyCtl.htm をブラウザー ビューで再度開きます。 今回は、[セキュリティの警告] ダイアログ ボックスが表示されず、Web ページが直接表示されます。 多角形の内側をクリックすると、辺の数が 1 つ増えます。 多角形の外側をクリックすると、辺の数が減ります。 辺の数を 3 未満に減らそうとすると、設定したエラー メッセージが表示されます。

[手順 6 に戻る](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>次の手順

これで ATL チュートリアルは終わりです。 ATL に関する詳細情報へのリンクを参照してください、 [ATL のスタート ページ](../atl/active-template-library-atl-concepts.md)します。

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
