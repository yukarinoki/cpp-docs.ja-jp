---
title: イベントの追加 (ATL チュートリアル、パート 5) |Microsoft Docs
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
ms.openlocfilehash: c08bd2ca05b0bb73b85572ab86222c2d1210115c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848634"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>イベントの追加 (ATL チュートリアル、パート 5)
この手順では、追加、`ClickIn`と`ClickOut`ATL コントロールにイベント。 起動は、`ClickIn`多角形および火災内で、ユーザーがクリックした場合、イベント`ClickOut`の外側をクリックした場合。 イベントを追加するタスクは次のとおりです。  
  
-   追加、`ClickIn`と`ClickOut`メソッド  
  
-   タイプ ライブラリを生成します。  
  
-   接続ポイントのインターフェイスを実装します。  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>ClickIn と ClickOut メソッドを追加します。  
 選択した ATL のコントロールを手順 2. で作成したときに、**コネクション ポイント**チェック ボックスをオンします。 作成した、 `_IPolyCtlEvents` Polygon.idl ファイルのインターフェイス。 インターフェイス名がアンダー スコアで始まるに注意してください。 これは、インターフェイスが内部のインターフェイスであることを示す規則です。 したがって、COM オブジェクトを参照するためのプログラムは、ユーザー インターフェイスを表示しないように選択できます。 また**コネクション ポイント**ことを示すために Polygon.idl ファイルで、次の行を追加`_IPolyCtlEvents`は既定のソース インターフェイス。  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 基になる属性では、コントロールは、コンテナーでこのインターフェイスを呼び出すことが、ため、通知のソースをことを示します。  
  
 ここで追加、`ClickIn`と`ClickOut`メソッドを`_IPolyCtlEvents`インターフェイス。  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>ClickIn と ClickOut メソッドを追加するには  
  
1.  クラス ビューでは、オンを表示するには、多角形と PolygonLib を展開します。  
  
2.  オンを右クリックします。 ショートカット メニューの **[追加]**、**[メソッドの追加]** を順にクリックします。  
  
3.  選択、**型を返す**の`void`します。  
  
4.  入力*ClickIn*で、**メソッド名**ボックス。  
  
5.  **パラメーター属性**を選択、**で**ボックス。  
  
6.  選択、**パラメーターの型**の`LONG`します。  
  
7.  型*x*として、**パラメーター名**、 をクリック**追加**します。  
  
8.  手順 5 ~ 7 では、この時間を**パラメーター名**の*y*します。  
  
9. **[次へ]** をクリックします。  
  
10. 型`method ClickIn`として、 **helpstring**します。  
  
11. **[完了]** をクリックします。  
  
12. 定義する上記の手順を繰り返して、`ClickOut`メソッドと同じ`LONG`パラメーター *x*と*y*、同じ**パラメーター属性**と同じ`void`型を返します。  
  
 Polygon.idl ファイルにコードが追加されたことを確認してください、`_IPolyCtlEvents`ディスパッチ インターフェイス。  
  
 `_IPolyCtlEvents` Polygon.idl ファイルのディスパッチ インターフェイス次のようになります。  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 `ClickIn`と`ClickOut`メソッドを x とパラメーターとして、クリックした点の y 座標。  
  
## <a name="generating-the-type-library"></a>タイプ ライブラリを生成します。  
 接続ポイント ウィザードを使用すると接続ポイントのインターフェイスとコントロールの接続ポイント コンテナー インターフェイスを構築する必要がある情報の取得に使用するため、この時点では、タイプ ライブラリを生成します。  
  
#### <a name="to-generate-the-type-library"></a>タイプ ライブラリを生成するには  
  
1.  プロジェクトをリビルドします。  
  
     - または -  
  
2.  ソリューション エクスプ ローラーで Polygon.idl ファイルを右クリックし、をクリックして**コンパイル**ショートカット メニューの します。  
  
 これにより、これは、タイプ ライブラリ Polygon.tlb ファイルが作成されます。 バイナリ ファイルとことはできませんが表示またはに直接編集は、Polygon.tlb ファイルをソリューション エクスプ ローラーで表示されません。  
  
## <a name="implementing-the-connection-point-interfaces"></a>接続ポイントのインターフェイスを実装します。  
 接続ポイントのインターフェイスとコントロールの接続ポイント コンテナー インターフェイスを実装します。 COM では、イベントは、コネクション ポイントのメカニズムを通じて実装されます。 COM オブジェクトからイベントを受信するには、コンテナーは、COM オブジェクトを実装する接続ポイントにアドバイザリ コネクションを確立します。 COM オブジェクトが複数の接続ポイントを持てないため、COM オブジェクトは、接続ポイント コンテナー インターフェイスも実装します。 このインターフェイスを使用する接続ポイントがサポートされているコンテナーを確認できます。  
  
 接続ポイントを実装するインターフェイスと呼びます`IConnectionPoint`、接続ポイント コンテナーを実装するインターフェイスを呼び出すと`IConnectionPointContainer`します。  
  
 実装に役立つ`IConnectionPoint`、接続ポイントの実装ウィザードを使用します。 このウィザードで生成、`IConnectionPoint`タイプ ライブラリを読み取って、起動できるイベントごとに関数を実装するインターフェイス。  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>接続ポイントの実装ウィザードを使用するには  
  
1.  クラス ビューでコントロールの実装クラスを右クリック`CPolyCtl`します。  
  
2.  ショートカット メニューで、**追加**、 をクリックし、**接続ポイントの追加**します。  
  
3.  選択`_IPolyCtlEvents`から、**ソース インターフェイス**を一覧表示し、ダブルクリックに追加して、**コネクション ポイントを実装**列。 **[完了]** をクリックします。 コネクション ポイントのプロキシ クラスが生成されます、ここでは、`CProxy_IPolyCtlEvents`します。  
  
 ソリューション エクスプ ローラーで生成された _IPolyCtlEvents_CP.h ファイルを見ると、わかりますというクラスを使用している`CProxy_IPolyCtlEvents`から派生した`IConnectionPointImpl`します。 _IPolyCtlEvents_CP.h は 2 つのメソッドも定義`Fire_ClickIn`と`Fire_ClickOut`、座標の 2 つのパラメーターを取ることができます。 コントロールからイベントを発生する場合に、これらのメソッドを呼び出します。  
  
 ウィザードの追加も`CProxy_PolyEvents`と`IConnectionPointContainerImpl`コントロールの複数の継承リストにします。 公開されているウィザード`IConnectionPointContainer`COM マップに適切なエントリを追加できます。  
  
 イベントをサポートするコードの実装が完了したら。 適切な時点で、イベントを発生させるコードを追加します。 起動することに注意してください、`ClickIn`または`ClickOut`イベント、ユーザーがコントロールでマウスの左ボタンをクリックするとします。 ユーザーがボタンをクリックしたときに確認をするのハンドラーを追加、`WM_LBUTTONDOWN`メッセージ。  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN メッセージ ハンドラーを追加するには  
  
1.  クラス ビューで CPolyCtl クラスを右クリックし、をクリックして**プロパティ**ショートカット メニューの します。  
  
2.  **プロパティ**ウィンドウで、をクリックして、**メッセージ**アイコンをクリック`WM_LBUTTONDOWN`、左側の一覧から。  
  
3.  表示されるドロップダウン リストから、クリックして**\<追加 > OnLButtonDown**します。 `OnLButtonDown` PolyCtl.h、するハンドラーの宣言が追加され、ハンドラーの実装は PolyCtl.cpp に追加されます。  
  
 次に、ハンドラーを変更します。  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown メソッドを変更するには  
  
1.  構成するコードを変更、`OnLButtonDown`メソッド PolyCtl.cpp (ウィザードで配置された任意のコードを削除する) で次のように見えるように。  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 ポイントの使用が計算されたこのコードにより、`OnDraw`関数の呼び出しで、ユーザーのマウスのクリックを検出する領域を作成する`PtInRegion`します。  
  
 *UMsg*パラメーターは、処理されている Windows メッセージの ID。 これにより、さまざまなメッセージを処理する 1 つの関数が存在することができます。 *WParam*と*lParam*パラメーターは、処理されるメッセージの標準の値。 パラメーター bHandled かどうか、関数が、メッセージを処理するかどうかを指定することができます。 既定では、値を FALSE に設定することができますが、関数は、メッセージを処理を示すために TRUE に設定します。 ATL にメッセージを送信するメッセージ ハンドラー関数が別の検索を続行するのには、なります。  
  
## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト  
 イベントを試すようになりました。 コントロールをビルドし、ActiveX コントロール テスト コンテナーをもう一度開始します。 今回では、イベント ログ ウィンドウを表示します。 出力ウィンドウにイベントをルーティングする をクリックして**ログ**から、**オプション**メニュー選択し、**出力ウィンドウにログ**します。 インポート コントロールの挿入 ウィンドウでクリックして操作をやり直してください。 注意`ClickIn`、多角形内をクリックした場合に発生し、`ClickOut`外部をクリックしたときに発生します。  
  
 次に、プロパティ ページを追加します。  
  
 [手順 4 に戻る](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [手順 6 に進む](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

