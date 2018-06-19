---
title: プロパティ ページ (ATL チュートリアル、パート 6) の追加 |Microsoft ドキュメント
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf7f0383697fbc1e23e179936a2616d1d236b5f2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361591"
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>プロパティ ページの追加 (ATL チュートリアル、パート 6)
プロパティ ページは、必要な場合を共有できるように個別の COM オブジェクトとして実装されます。 このステップでは、コントロールにプロパティ ページを追加するタスクを次の操作を行います。  
  
-   プロパティ ページ リソースの作成  
  
-   コードの作成し、管理、プロパティ ページを追加します。  
  
-   コントロールに、プロパティ ページを追加します。  
  
## <a name="creating-the-property-page-resource"></a>プロパティ ページ リソースの作成  
 コントロールにプロパティ ページを追加するには、クラスの追加ウィザードを使用します。  
  
#### <a name="to-add-a-property-page"></a>プロパティ ページを追加するには  
  
1.  ソリューション エクスプ ローラーで、多角形を右クリックします。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**クラスの追加**です。  
  
3.  テンプレートの一覧から選択**ATL プロパティ ページ** をクリック**追加**です。  
  
4.  ATL プロパティ ページ ウィザードが表示されたら、入力`PolyProp`として、**短い**名。  
  
5.  をクリックして**文字列**を開くには、**文字列**ページし、入力 **& 多角形**として、**タイトル**です。  
  
     **タイトル**プロパティのページは、そのページのタブに表示される文字列。 **ドキュメント文字列**プロパティ フレームを使用してステータス行またはツール ヒントに表示される説明を示します。 標準的なプロパティ フレーム現在は使用されないこの文字列では、既定の内容のままにすることができますので注意してください。 生成されません、**ヘルプ ファイルを**現時点では、そのテキスト ボックス内のエントリをので削除します。  
  
6.  をクリックして**完了**、プロパティ ページのオブジェクトが作成されます。  
  
 次の 3 つのファイルが作成されます。  
  
|ファイル|説明|  
|----------|-----------------|  
|PolyProp.h|C++ クラスを含む`CPolyProp`、プロパティ ページを実装します。|  
|PolyProp.cpp|PolyProp.h ファイルが含まれます。|  
|Polyprop.rgs という|プロパティ ページ オブジェクトを登録するレジストリ スクリプトです。|  
  
 次のコードの変更も行われます。  
  
-   新しいプロパティ ページは、Polygon.cpp のオブジェクト エントリ マップに追加されます。  
  
-   `PolyProp`クラスが Polygon.idl ファイルに追加します。  
  
-   新しい polyprop.rgs というレジストリ スクリプト ファイルは、プロジェクトのリソースに追加されます。  
  
-   ダイアログ ボックスのテンプレートは、プロパティ ページのプロジェクトのリソースに追加されます。  
  
-   指定したプロパティの文字列は、リソース文字列テーブルに追加されます。  
  
 プロパティ ページに表示するフィールドを追加します。  
  
#### <a name="to-add-fields-to-the-property-page"></a>プロパティ ページにフィールドを追加するには  
  
1.  ソリューション エクスプ ローラーで、Polygon.rc リソース ファイルをダブルクリックします。 リソース ビューが表示されます。  
  
2.  リソース ビューでダイアログ ノードを展開し、IDD_POLYPROP をダブルクリックします。 表示されるダイアログ ボックスがコントロールをここに挿入するよう指示する、ラベルを除く空であることに注意してください。  
  
3.  そのラベルを選択し、変更を読み取る`Sides:`変更することにより、**キャプション**内のテキスト、**プロパティ**ウィンドウです。  
  
4.  [ラベル] ボックスのサイズを変更して、テキストのサイズが収まるようにします。  
  
5.  エディット コントロールをツールボックスから、ラベルの右側にドラッグします。  
  
6.  最後に、変更、 **ID**するエディット コントロールの`IDC_SIDES`プロパティ ウィンドウを使用します。  
  
 これは、プロパティ ページのリソースを作成するプロセスを完了します。  
  
## <a name="adding-code-to-create-and-manage-the-property-page"></a>コードの作成し、管理、プロパティ ページを追加します。  
 プロパティ ページのリソースを作成して、実装コードを記述する必要があります。  
  
 最初に、有効にする、`CPolyProp`クラス オブジェクトの辺の数を設定するときに、**適用**ボタンが押されました。  
  
#### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>辺の数を設定する適用関数を変更するには  
  
1.  置換、 `Apply` PolyProp.h で関数を次のコード。  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 プロパティ ページに接続して、一度に 1 つ以上のクライアントを持つことができますので、`Apply`関数でループ処理し、呼び出し`put_Sides`値では、各クライアントでは、エディット ボックスから取得します。 使用している、 [CComQIPtr](../atl/reference/ccomqiptr-class.md)を実行するには、クラス、`QueryInterface`を取得するには、各オブジェクトに対して、`IPolyCtl`からインターフェイス、 **IUnknown**インターフェイス (に格納されている、`m_ppUnk`配列)。  
  
 コードは、その設定を今すぐチェック、`Sides`プロパティが実際に動作します。 コードがエラーの詳細を表示するメッセージ ボックスを表示して、失敗した場合は、 **IErrorInfo**インターフェイスです。 コンテナーでのオブジェクトを要求する通常、 **ISupportErrorInfo**インターフェイスと呼び出し`InterfaceSupportsErrorInfo`最初は、オブジェクトがエラー情報の設定をサポートするかどうかを判別します。 このタスクをスキップすることができます。  
  
 [CComPtr](../atl/reference/ccomptr-class.md)を呼び出す必要はありませんので、参照カウントを自動的に処理することで役立つ`Release`インターフェイスです。 `CComBSTR` 役立つ`BSTR`を処理するため、最終的なを実行する必要はありません`SysFreeString`呼び出します。 使用することも、さまざまな文字列変換クラスのいずれかの変換できるように、`BSTR`必要な場合 (その理由は、`USES_CONVERSION`マクロと関数の開始時に)。  
  
 示すために、プロパティ ページのダーティ フラグを設定する必要があります、**適用**ボタンが有効にする必要があります。 これは、ユーザーに値を変更する場合に発生、**辺**編集ボックス。  
  
#### <a name="to-handle-the-apply-button"></a>[適用] ボタンを処理するには  
  
1.  クラス ビュー で CPolyProp を右クリックし、をクリックして**プロパティ**ショートカット メニューの します。  
  
2.  [プロパティ] ウィンドウ、**イベント**アイコン。  
  
3.  展開して、`IDC_SIDES`ノードは、イベントの一覧表示します。  
  
4.  選択`EN_CHANGE`、右側にドロップ ダウン メニューからをクリックして**\<追加 > OnEnChangeSides**です。 `OnEnChangeSides`ハンドラーの宣言は Polyprop.h、および Polyprop.cpp にハンドラーの実装に追加されます。  
  
 次に、ハンドラーを変更します。  
  
#### <a name="to-modify-the-onenchangesides-method"></a>OnEnChangeSides メソッドを変更するには  
  
1.  Polyprop.cpp で次のコードを追加、`OnEnChangeSides`メソッド (ウィザードがそこに配置するすべてのコードを削除する)。  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides` 呼び出されるときに、 **WM_COMMAND**でメッセージが送信された、 **EN_CHANGE**の通知、`IDC_SIDES`コントロール。 `OnEnChangeSides` 呼び出して`SetDirty`渡します`TRUE`プロパティを示すためにページがダーティ今すぐおよび**適用**ボタンが有効にする必要があります。  
  
## <a name="adding-the-property-page-to-the-control"></a>コントロールに、プロパティ ページを追加します。  
 クラスの追加ウィザードと ATL プロパティ ページ ウィザードに対する追加しないでプロパティ ページをコントロールする自動的に、プロジェクトで複数のコントロールになる可能性があります。 コントロールのプロパティ マップにエントリを追加する必要があります。  
  
#### <a name="to-add-the-property-page"></a>プロパティ ページを追加するには  
  
1.  PolyCtl.h を開き、プロパティ マップに次の行を追加します。  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 コントロールのプロパティ マップは、次のようになります。  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 追加することも、`PROP_PAGE`マクロを使用する場合は、プロパティ ページの CLSID を持つ、`PROP_ENTRY`ように、マクロ、`Sides`プロパティの値は、コントロールの保存時にも保存します。  
  
 マクロに 3 つのパラメーターは、プロパティの説明、プロパティの DISPID とプロパティを含むプロパティ ページの CLSID です。 これにより場合、たとえば、Visual Basic にコントロールを読み込むし、デザイン時に辺の数を設定できます。 辺の数が保存されているため、Visual Basic プロジェクトを再読み込みするときに、辺の数が復元されます。  
  
## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト  
 コントロールをビルドし、ActiveX コントロール テスト コンテナーに挿入するようになりました。 テスト コンテナーで、上、**編集** メニューのをクリックして**PolyCtl クラス オブジェクト**です。 プロパティ ページが表示されます。クリックして、**多角形**タブです。  
  
 **適用**ボタンが最初に無効になります。 値の入力を開始、**辺**ボックスおよび**適用**ボタンが有効になります。 値の入力が完了したら、をクリックして、**適用**ボタンをクリックします。 コントロールの表示が変わり、および**適用**ボタンが再び無効になります。 無効な値を入力してください。 設定するエラーの説明を含むメッセージ ボックスが表示されます、`put_Sides`関数。  
  
 次に、Web ページにコントロールを格納します。  
  
 [手順 5 に戻る](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [手順 7 に](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

