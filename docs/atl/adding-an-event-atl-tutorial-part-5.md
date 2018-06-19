---
title: イベント (ATL チュートリアル、パート 5) の追加 |Microsoft ドキュメント
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a118cf29546ac8dae2e882d5658b07e3b5e085f6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361266"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>イベントの追加 (ATL チュートリアル、パート 5)
この手順では、追加、`ClickIn`と`ClickOut`ATL コントロールにイベント。 起動、`ClickIn`多角形および火災内でクリックすると、ユーザー イベント`ClickOut`の外側をクリックした場合。 イベントを追加するタスクは次のとおりです。  
  
-   追加する、`ClickIn`と`ClickOut`メソッド  
  
-   タイプ ライブラリを生成します。  
  
-   接続ポイントのインターフェイスを実装します。  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>ClickIn と ClickOut メソッドを追加します。  
 手順 2 で、ATL コントロールを作成する際に選択、**コネクション ポイント**チェック ボックスをオンします。 作成した、 `_IPolyCtlEvents` Polygon.idl ファイル内のインターフェイスです。 インターフェイス名がアンダー スコアで始まることに注意してください。 これは、インターフェイスが内部のインターフェイスであることを示す規則です。 したがって、COM オブジェクトを参照できるプログラムは、ユーザー インターフェイスを表示しないように選択できます。 また**コネクション ポイント**ことを示すために Polygon.idl ファイルで、次の行を追加した`_IPolyCtlEvents`は、既定のソース インターフェイス。  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 基になる属性では、コントロールは、コンテナーでこのインターフェイスが呼び出されますため、ソース、通知のことを示します。  
  
 ここで追加、`ClickIn`と`ClickOut`メソッドを`_IPolyCtlEvents`インターフェイスです。  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>ClickIn と ClickOut メソッドを追加するには  
  
1.  クラス ビュー でオンを表示するには、多角形と PolygonLib を展開します。  
  
2.  オンを右クリックします。 ショートカット メニューをクリックして**追加**、クリックして**メソッドの追加**です。  
  
3.  選択、**型を返す**の`void`します。  
  
4.  入力`ClickIn`で、**メソッド名**ボックス。  
  
5.  **パラメーター属性**、select、**で**ボックス。  
  
6.  選択、**パラメーターの型**の`LONG`します。  
  
7.  型`x`として、**パラメーター名**、 をクリック**追加**です。  
  
8.  手順 5. ~ 7.、この時間を**パラメーター名**の`y`します。  
  
9. **[次へ]** をクリックします。  
  
10. 型`method ClickIn`として、 **helpstring**です。  
  
11. **[完了]** をクリックします。  
  
12. 定義するのには上記の手順を繰り返して、`ClickOut`を同じメソッド`LONG`パラメーター`x`と`y`、同じ**パラメーター属性**と同じ`void`型を返します。  
  
 Polygon.idl を表示するファイルにコードが追加されたことを確認して、`_IPolyCtlEvents`ディスパッチ インターフェイスです。  
  
 `_IPolyCtlEvents` Polygon.idl ファイルのディスパッチ インターフェイスは次のようになります。  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 `ClickIn`と`ClickOut`メソッドを x とパラメーターとして、クリックしたポイントの y 座標。  
  
## <a name="generating-the-type-library"></a>タイプ ライブラリを生成します。  
 接続ポイントが使用されますが、接続ポイントのインターフェイスとコントロール用の接続ポイント コンテナー インターフェイスを構築するために必要な情報を取得するためこの時点では、タイプ ライブラリを生成します。  
  
#### <a name="to-generate-the-type-library"></a>タイプ ライブラリを生成するには  
  
1.  プロジェクトをリビルドします。  
  
     - または -  
  
2.  ソリューション エクスプ ローラーで Polygon.idl ファイルを右クリックし、をクリックして**コンパイル**ショートカット メニューの します。  
  
 これにより、これは、タイプ ライブラリ Polygon.tlb ファイルが作成されます。 Polygon.tlb ファイルではありませんソリューション エクスプ ローラーで表示される、バイナリ ファイルは、表示またはできませんを直接編集します。  
  
## <a name="implementing-the-connection-point-interfaces"></a>接続ポイントのインターフェイスを実装します。  
 コネクション ポイント インターフェイスとコントロールの接続ポイント コンテナー インターフェイスを実装します。 COM では、イベントは、接続ポイントのメカニズムを通じて実装されます。 COM オブジェクトからイベントを受信するには、コンテナーは、COM オブジェクトを実装する接続ポイントにアドバイザリ コネクションを確立します。 COM オブジェクトは複数の接続ポイントを持てないため、COM オブジェクトも接続ポイント コンテナー インターフェイスを実装します。 このインターフェイスを使用する接続ポイントがサポートされているコンテナーを判断できます。  
  
 接続ポイントを実装するインターフェイスと呼びます`IConnectionPoint`との接続ポイント コンテナーを実装するインターフェイスと呼びます`IConnectionPointContainer`です。  
  
 実装に役立つ`IConnectionPoint`、接続ポイントの実装ウィザードが使用されます。 このウィザードで生成、`IConnectionPoint`記事、タイプ ライブラリを起動できる各イベントに対して関数を実装するインターフェイスです。  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>接続ポイントの実装ウィザードを使用するには  
  
1.  クラス ビュー で、コントロールの実装のクラスを右クリックして`CPolyCtl`です。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**接続ポイントの追加**です。  
  
3.  選択`_IPolyCtlEvents`から、**ソース インターフェイス**を一覧表示し、ダブルクリックに追加する、**接続ポイントを実装する**列です。 **[完了]** をクリックします。 接続ポイントのプロキシ クラスが生成されます、ここでは、`CProxy_IPolyCtlEvents`です。  
  
 ソリューション エクスプ ローラーで、生成された _IPolyCtlEvents_CP.h ファイルを見ると、わかりますと呼ばれるクラスを使用している`CProxy_IPolyCtlEvents`から派生した`IConnectionPointImpl`です。 _IPolyCtlEvents_CP.h も 2 つのメソッドを定義`Fire_ClickIn`と`Fire_ClickOut`、2 つの座標のパラメーターを取得します。 コントロールからイベントを発生する場合に、これらのメソッドを呼び出します。  
  
 ウィザードも追加`CProxy_PolyEvents`と`IConnectionPointContainerImpl`コントロールの複数の継承リストにします。 公開ウィザード`IConnectionPointContainer`COM マップに適切なエントリを追加することによってです。  
  
 イベントをサポートするためにコードの実装が完了したらです。 ここで、適切な時点でイベントを発生させるコードを追加します。 起動することに注意してください、`ClickIn`または`ClickOut`イベント、ユーザーがコントロールでマウスの左ボタンをクリックします。 参照して、ユーザーがボタンをクリックしたときに、追加のハンドラーを`WM_LBUTTONDOWN`メッセージ。  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN メッセージのハンドラーを追加するには  
  
1.  クラス ビュー] で CPolyCtl クラスを右クリックし、をクリックして**プロパティ**ショートカット メニューの [します。  
  
2.  **プロパティ**ウィンドウで、をクリックして、**メッセージ**アイコンをクリックして`WM_LBUTTONDOWN`左にある一覧からです。  
  
3.  表示されるドロップダウン リストから、クリックして**\<追加 > OnLButtonDown**です。 `OnLButtonDown` PolyCtl.h、するハンドラーの宣言が追加され、ハンドラーの実装は PolyCtl.cpp に追加されます。  
  
 次に、ハンドラーを変更します。  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown メソッドを変更するには  
  
1.  構成するコードを変更、`OnLButtonDown`メソッド (ウィザードで記述されているコードの削除) PolyCtl.cpp で次のように見えるように。  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 ポイントの使用が計算されたこのコードにより、`OnDraw`関数を呼び出したときに、ユーザーのマウスのクリックを検出する領域を作成する`PtInRegion`です。  
  
 `uMsg`パラメーターは、処理されている Windows メッセージの ID。 これにより、さまざまなメッセージを処理する 1 つの関数。 `wParam`と`lParam`パラメーターは、処理されるメッセージの標準的な値です。 パラメーター bHandled では、関数にメッセージが処理されるかどうかどうかを指定することができます。 既定では、値に設定`TRUE`関数には、メッセージが処理されるに設定することを示すこと`FALSE`です。 これにより、メッセージを送信するもう 1 つのメッセージ ハンドラー関数の検索を続行する ATL。  
  
## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト  
 イベントを試すようになりました。 コントロールをビルドし、ActiveX コントロール テスト コンテナーをもう一度開始します。 このときは、イベント ログ ウィンドウを表示します。 イベントを出力ウィンドウにルーティングする をクリックして**ログ**から、**オプション**メニュー**出力ウィンドウにログ**です。 コントロールを挿入して、ウィンドウ内をクリックを再試行してください。 注意してください`ClickIn`塗りつぶされた多角形の中をクリックした場合に発生し、`ClickOut`外部をクリックするときに発生します。  
  
 次に、プロパティ ページを追加します。  
  
 [手順 4 に戻る](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [手順 6 に進む](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

