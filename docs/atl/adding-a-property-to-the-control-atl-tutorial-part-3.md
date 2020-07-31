---
title: コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: c5f71880f780e793cd77eb5a7571d31de4a8d01a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219002"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)

`IPolyCtl`は、コントロールのカスタムメソッドとプロパティを含むインターフェイスであり、プロパティを追加します。

### <a name="to-add-the-property-definitions-to-your-project"></a>プロパティ定義をプロジェクトに追加するには

1. **クラスビュー**で、分岐を展開し `Polygon` ます。

1. を右クリック `IPolyCtl` します。

1. ショートカットメニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。 **プロパティの追加**ウィザードが表示されます。

1. `Sides`**プロパティ名**として「」と入力します。

1. **プロパティの種類**のドロップダウンリストで、[] を選択し **`short`** ます。

1. [ **OK** ] をクリックして、プロパティの追加を完了します。

1. **ソリューションエクスプローラー**から、Polygon を開き、インターフェイスの末尾にある次の行を置き換え `IPolyCtl : IDispatch` ます。

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    with

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. **ソリューションエクスプローラー**から polyctl.htm を開き、の定義の後に次の行を追加し `m_clrFillColor` ます。

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

プロパティを設定および取得するためのスケルトン関数が用意されていますが、プロパティを格納する変数を取得するには、それに応じて関数を実装する必要があります。

### <a name="to-update-the-get-and-put-methods"></a>Get メソッドと put メソッドを更新するには

1. の既定値を設定 `m_nSides` します。 Polyctl.htm のコンストラクターに行を追加して、既定の図形を三角形にします。

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. `Get`メソッドとメソッドを実装し `Put` ます。 `get_Sides`および `put_Sides` 関数の宣言が polyctl.htm に追加されました。 次のように、とのコードを `get_Sides` `put_Sides` polyctl.htm に追加します。

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

メソッドは、 `get_Sides` ポインターを介してプロパティの現在の値を返し `Sides` `pVal` ます。 メソッドでは、 `put_Sides` ユーザーが `Sides` プロパティを受け入れ可能な値に設定していることがコードによって保証されます。 最小値は3である必要があります。また、点の配列が各辺に使用されるため、100は最大値に対して妥当な制限となります。

これで、という名前のプロパティが作成されました `Sides` 。 次の手順では、描画コードを使用するように変更します。

手順[2 に戻っ](../atl/adding-a-control-atl-tutorial-part-2.md)[て、手順4に](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)&#124; ます。

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
