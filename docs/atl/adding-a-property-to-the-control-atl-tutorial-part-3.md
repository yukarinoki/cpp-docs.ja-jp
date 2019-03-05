---
title: コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: b5f9f9c8fde44dd67a9a05aeae0f91fb7b5f2f4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281019"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)

`IPolyCtl` コントロールのカスタム メソッドとプロパティを格納しているインターフェイスは、プロパティを追加します。

### <a name="to-add-the-property-definitions-to-your-project"></a>プロパティの定義をプロジェクトに追加するには

1. **クラス ビュー**、展開、`Polygon`分岐します。

1. 右クリックして`IPolyCtl`します。

1. ショートカット メニューで、**追加**、 をクリックし、**プロパティの追加**します。 **プロパティの追加**ウィザードが表示されます。

1. 型`Sides`として、**プロパティ名**します。

1. ドロップダウン リストで**プロパティ型**、`short`します。

1. クリックして**OK**プロパティの追加を完了します。

1. **ソリューション エクスプ ローラー**Polygon.idl を開き、次の行の末尾に置き換えます、`IPolyCtl : IDispatch`インターフェイス。

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    with

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. **ソリューション エクスプ ローラー**PolyCtl.h を開いての定義後に、次の行を追加`m_clrFillColor`:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

スケルトンの関数を設定し、プロパティおよびプロパティを格納する変数を取得するようになりましたが、それに応じて関数を実装する必要があります。

### <a name="to-update-the-get-and-put-methods"></a>Get を更新し、put メソッド

1. 既定値を設定`m_nSides`します。 PolyCtl.h でコンス トラクターに 1 行を追加することで、三角形を図形の既定を行います。

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. 実装、`Get`と`Put`メソッド。 `get_Sides`と`put_Sides`PolyCtl.h に関数の宣言が追加されました。 コードを追加`get_Sides`と`put_Sides`PolyCtl.cpp を次に。

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

`get_Sides`メソッドの現在の値を返します、`Sides`プロパティを介して、`pVal`ポインター。 `put_Sides`メソッド、コードにより、ユーザーの設定、`Sides`プロパティに許容される値。 最小値は 3 である必要があり、100 は最大値として妥当な制限でそれぞれの側のポイントの配列を使用するためです。

という名前のプロパティがあるようになりました`Sides`します。 次の手順では、それを使用する描画コードを変更します。

[手順 2 に戻る](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [手順 4 に](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
