---
title: プロパティの追加 (ATL チュートリアル、パート 3) のコントロールに |Microsoft ドキュメント
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
ms.openlocfilehash: fda9359da6ddc48248874227d58f0c184af45c54
ms.sourcegitcommit: 9b442b44ee912822d06cabec826aac4a8d82ec75
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)
`IPolyCtl` コントロールのカスタム プロパティとメソッドを格納しているインターフェイスは、プロパティを追加します。  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してプロパティを追加するには  
  
1.  クラス ビューでは、多角形のブランチを展開します。  
  
2.  IPolyCtl を右クリックします。  
  
3.  ショートカット メニューをクリックして**追加**、クリックして**プロパティの追加**です。  
  
     プロパティの追加ウィザードが表示されます。  
  
4.  プロパティの種類のドロップダウン リストで選択`SHORT`です。  
  
5.  型`Sides`として、**プロパティ名。**  
  
6.  をクリックして**完了**プロパティの追加を完了します。  
  
 MIDL (.idl ファイルをコンパイルするプログラム) を定義、インターフェイスにプロパティを追加すると、`Get`をその値を取得するメソッドと`Put`新しい値を設定するためのメソッドです。 付加することによって、メソッドの名前として`put_`と`get_`プロパティ名にします。  
  
 プロパティの追加ウィザードでは、.idl ファイルに必要な行を追加します。 さらに、`Get`と`Put`関数のプロトタイプ PolyCtl.h でクラスの定義にし、PolyCtl.cpp に空の実装を追加します。 これをチェックするには PolyCtl.cpp を開き、関数を探して`get_Sides`と`put_Sides`です。  
  
 今すぐ設定して、プロパティを取得するスケルトンの関数がある場合、格納する場所が必要があります。 プロパティを格納および関数を適宜更新する変数を作成します。  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>Get メソッドと、put を更新プロパティを格納する変数を作成するには  
  
1.  ソリューション エクスプ ローラーから PolyCtl.h を開きの定義の後に、次の行を追加`m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  既定値を設定`m_nSides`です。 PolyCtl.h でコンス トラクターに 1 行を追加することにより図形の三角形の既定にします。  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  実装、`Get`と`Put`メソッドです。 `get_Sides`と`put_Sides`PolyCtl.h に関数宣言が追加されました。 コードの PolyCtl.cpp で置き換え`get_Sides`と`put_Sides`を次のコード。  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides`の現在の値を返します、`Sides`プロパティを介して、`pVal`ポインター。 `put_Sides`メソッド、コードにより、ユーザーが設定、`Sides`プロパティに許容される値。 最小値は 3 である必要があり、100 は、最大値の妥当な制限は、点の配列のそれぞれの側を使用することがあるためです。  
  
 今すぐというプロパティがある`Sides`です。 次の手順では、それを使用する描画コードを変更します。  
  
 [手順 2 に戻る](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [手順 4 に進む](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

