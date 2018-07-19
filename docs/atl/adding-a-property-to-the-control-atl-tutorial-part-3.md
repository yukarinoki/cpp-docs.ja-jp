---
title: コントロール (ATL チュートリアル、パート 3) にプロパティの追加 |Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cbfb0b22579aceb5cbee196e3c5eda3079c9304
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848718"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)
`IPolyCtl` コントロールのカスタム メソッドとプロパティを格納しているインターフェイスは、プロパティを追加します。  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してプロパティを追加するには  
  
1.  クラス ビューでは、多角形のブランチを展開します。  
  
2.  IPolyCtl を右クリックします。  
  
3.  ショートカット メニューで、**追加**、 をクリックし、**プロパティの追加**します。  
  
     プロパティの追加ウィザードが表示されます。  
  
4.  プロパティの型のドロップダウン リストで選択`SHORT`します。  
  
5.  型*辺*として、**プロパティ名。**  
  
6.  クリックして**完了**プロパティの追加を完了します。  
  
 MIDL (.idl ファイルにコンパイルされるプログラム) を定義、インターフェイスにプロパティを追加すると、`Get`その値を取得するためのメソッドと`Put`メソッドの新しい値を設定します。 メソッドが付けた`put_`と`get_`プロパティ名にします。  
  
 プロパティの追加ウィザードでは、.idl ファイルに必要な行を追加します。 また、`Get`と`Put`関数のプロトタイプ PolyCtl.h でクラス定義にし、PolyCtl.cpp に空の実装を追加します。 これを確認するには PolyCtl.cpp を開き、関数を探して`get_Sides`と`put_Sides`します。  
  
 スケルトンの関数を設定し、プロパティを取得するようになりましたが、格納される場所が必要です。 プロパティの格納および関数を適宜更新する変数を作成します。  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>プロパティを格納、更新、put と get メソッドに変数を作成するには  
  
1.  ソリューション エクスプ ローラーから PolyCtl.h を開きの定義の後に、次の行を追加`m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  既定値を設定`m_nSides`します。 PolyCtl.h でコンス トラクターに 1 行を追加することで、三角形を図形の既定を行います。  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  実装、`Get`と`Put`メソッド。 `get_Sides`と`put_Sides`PolyCtl.h に関数の宣言が追加されました。 コードの PolyCtl.cpp に置き換えます`get_Sides`と`put_Sides`を次のコード。  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides`メソッドの現在の値を返します、`Sides`プロパティを介して、`pVal`ポインター。 `put_Sides`メソッド、コードにより、ユーザーの設定、`Sides`プロパティに許容される値。 最小値は 3 である必要があり、100 は最大値として妥当な制限でそれぞれの側のポイントの配列を使用するためです。  
  
 という名前のプロパティがあるようになりました`Sides`します。 次の手順では、それを使用する描画コードを変更します。  
  
 [手順 2 に戻る](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [手順 4 に](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

