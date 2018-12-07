---
title: マルチページ ドキュメント
ms.date: 11/19/2018
helpviewer_keywords:
- pagination [MFC]
- overriding [MFC], View class functions for printing
- OnPrepareDC method [MFC]
- CPrintInfo structure [MFC], multipage documents
- OnEndPrinting method [MFC]
- protocols [MFC], printing protocol
- document pages vs. printer pages [MFC]
- printer mode [MFC]
- printing [MFC], multipage documents
- printers [MFC], printer mode
- documents [MFC], printing
- OnPreparePrinting method [MFC]
- OnPrint method [MFC]
- DoPreparePrinting method and pagination [MFC]
- OnDraw method [MFC], printing
- pagination [MFC], printing multipage documents
- printing [MFC], protocol
- pages [MFC], printing
- OnBeginPrinting method [MFC]
- multipage documents [MFC]
- printing [MFC], pagination
- documents [MFC], paginating
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
ms.openlocfilehash: b4ec9f456443b9cd180f1558946829281bc10a36
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176381"
---
# <a name="multipage-documents"></a>マルチページ ドキュメント

この記事では、Windows 印刷プロトコルについて説明し、複数のページが含まれているドキュメントを印刷する方法について説明します。 この記事では、次のトピックについて説明します。

- [印刷のプロトコル](#_core_the_printing_protocol)

- [ビュー クラスの関数をオーバーライドします。](#_core_overriding_view_class_functions)

- [改ページ](#_core_pagination)

- [プリンターのページとドキュメント ページ](#_core_printer_pages_vs.._document_pages)

- [印刷時の改ページ](#_core_print.2d.time_pagination)

##  <a name="_core_the_printing_protocol"></a> 印刷のプロトコル

マルチページ ドキュメントを印刷するにはフレームワークとビューは次のように操作します。 最初に、フレームワークが表示されます、**印刷**ダイアログ ボックスで、プリンター、および呼び出しのデバイス コンテキストを作成、 [StartDoc](../mfc/reference/cdc-class.md#startdoc)のメンバー関数、 [CDC](../mfc/reference/cdc-class.md)オブジェクト。 次に、ドキュメントの各ページでは、フレームワーク、 [StartPage](../mfc/reference/cdc-class.md#startpage)のメンバー関数、`CDC`オブジェクト、ページ、および呼び出しを印刷するビュー オブジェクトに指示、 [EndPage](../mfc/reference/cdc-class.md#endpage)メンバー関数。 ビューを呼び出す場合は、特定のページを開始する前に、プリンター モードを変更する必要があります、[印刷](../mfc/reference/cdc-class.md#resetdc)、更新プログラム、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)新しいプリンター モードの情報を含む構造体。 ドキュメント全体が印刷されたときに、フレームワーク、 [EndDoc](../mfc/reference/cdc-class.md#enddoc)メンバー関数。

##  <a name="_core_overriding_view_class_functions"></a> ビュー クラスの関数をオーバーライドします。

[CView](../mfc/reference/cview-class.md)クラスは、印刷時にフレームワークによって呼び出されるいくつかのメンバー関数を定義します。 ビュー クラスでこれらの関数をオーバーライドして、フレームワークの印刷ロジックと印刷ロジックをビュー クラスの間の接続を提供します。 次の表には、これらのメンバー関数が一覧表示します。

### <a name="cviews-overridable-functions-for-printing"></a>印刷用 CView のオーバーライド可能な関数

|名前|オーバーライドする理由|
|----------|---------------------------|
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|[印刷] ダイアログ ボックスで、ドキュメントの長さなどの値を挿入するには|
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|フォントまたはその他の GDI リソースを割り当てる|
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|特定のページのデバイス コンテキストの属性を調整するには、または印刷時の改ページ調整を行う|
|[OnPrint](../mfc/reference/cview-class.md#onprint)|特定のページを印刷するには|
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI リソースの割り当てを解除するには|

同様に、他の関数での印刷関連の処理を行うことができますが、これらの関数は、印刷プロセスを促進します。

印刷プロセスの手順を示しています、場所を示しています。 次の図の各`CView`印刷メンバー関数が呼び出されます。 この記事の残りの部分では、これらの手順の詳細のほとんどについて説明します。 印刷プロセスの追加部分については、記事[GDI リソースの割り当て](../mfc/allocating-gdi-resources.md)します。

![印刷ループ プロセス](../mfc/media/vc37c71.gif "印刷ループ処理") <br/>
印刷ループ

##  <a name="_core_pagination"></a> 改ページ

フレームワークはで印刷ジョブに関する情報の多くは、格納、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体。 いくつかの値の`CPrintInfo`改ページ調整に関連は、これらの値にアクセスできるは、次の表に示すようにします。

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo に格納されているページ数情報

|メンバー変数または<br /><br /> 関数名|参照されているページ数|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|ドキュメントの最初のページ|
|`GetMaxPage`/`SetMaxPage`|ドキュメントの最後のページ|
|`GetFromPage`|最初のページを印刷するには|
|`GetToPage`|印刷する最後のページ|
|`m_nCurPage`|現在印刷中のページ|

1、ページ番号の開始は、最初のページ番号が 1、0 ではありません。 これらや他のメンバーの詳細については[CPrintInfo](../mfc/reference/cprintinfo-structure.md)を参照してください、 *MFC リファレンス*します。

印刷プロセスの先頭には、フレームワークによって、ビューの[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)メンバー関数へのポインターを渡して、`CPrintInfo`構造体。 アプリケーション ウィザードの実装を提供する`OnPreparePrinting`を呼び出す[DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting)、別のメンバー関数の`CView`します。 `DoPreparePrinting` 印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成する関数です。

この時点で、アプリケーションでは、数ページには、ドキュメントを認識しません。 ドキュメントの最初と最後のページ数の既定値 1 と 0 xffff を使用します。 ドキュメントのページの数がわかっている場合は、オーバーライド`OnPreparePrinting`を呼び出すと [の SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage)、`CPrintInfo`に送信する前に構造体`DoPreparePrinting`します。 これにより、ドキュメントの長さを指定できます。

`DoPreparePrinting` [印刷] ダイアログ ボックスが表示されます。 それが返されるときに、`CPrintInfo`構造体には、ユーザーによって指定された値が含まれています。 ページの選択範囲のみを印刷する場合は、そのユーザーを指定できます、最初と最後の印刷 ダイアログ ボックスのページ番号。 フレームワークを使用してこれらの値を取得する、`GetFromPage`と`GetToPage`関数の[CPrintInfo](../mfc/reference/cprintinfo-structure.md)します。 ユーザーがページの範囲を指定していない場合、フレームワーク`GetMinPage`と`GetMaxPage`文書全体を印刷に返される値を使用しています。

印刷するドキュメントの各ページでは、フレームワークは、ビュー クラスで 2 つのメンバー関数を呼び出す[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)と[OnPrint](../mfc/reference/cview-class.md#onprint)、し、各関数の 2 つのパラメーターを渡しますへのポインター、 [ 。CDC](../mfc/reference/cdc-class.md)オブジェクトとへのポインター、`CPrintInfo`構造体。 たびに、フレームワークによって`OnPrepareDC`と`OnPrint`で別の値を渡す、 *m_nCurPage*のメンバー、`CPrintInfo`構造体。 この方法では、フレームワークは、ビューに対し、どのページを印刷するかを指示します。

[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)メンバー関数は、画面の表示にも使用します。 描画が行われる前に、デバイス コンテキストの調整になります。 `OnPrepareDC` 印刷では、同様の役割の機能の相違点のいくつかありますが、: 最初、`CDC`オブジェクトは画面のデバイス コンテキスト、および秒ではなくプリンター デバイス コンテキストを表します、`CPrintInfo`オブジェクトが 2 番目のパラメーターとして渡されます。 (このパラメーターは**NULL**とき`OnPrepareDC`は画面表示のために呼び出されます)。オーバーライド`OnPrepareDC`印刷するページに基づき、デバイス コンテキストを調整します。 たとえば、ビューポートの原点と文書の適切な部分を印刷を取得することを確認するクリッピング領域を移動できます。

[OnPrint](../mfc/reference/cview-class.md#onprint)メンバー関数は、ページの印刷を実行します。 記事[既定の印刷を行う方法](../mfc/how-default-printing-is-done.md)フレームワークを呼び出す方法を示しています。 [OnDraw](../mfc/reference/cview-class.md#ondraw)印刷を実行するプリンター デバイス コンテキストを使用します。 フレームワークによって正確には、`OnPrint`で、`CPrintInfo`構造と、デバイス コンテキストと`OnPrint`デバイス コンテキストを渡します`OnDraw`。 オーバーライド`OnPrint`印刷時にのみ、および画面表示ではなく行う必要があるすべてのレンダリングを実行します。 たとえば、ヘッダーまたはフッターを印刷する (記事をご覧ください[ヘッダーとフッター](../mfc/headers-and-footers.md)詳細については)。 呼び出して`OnDraw`のオーバーライドから`OnPrint`画面表示の両方に共通の表示と印刷を行う。

事実を`OnDraw`レンダリングでは、両方の画面表示と印刷の場合、アプリケーションが WYSIWYG であることを意味は:"どのような you see is what you get"。 ただし、WYSIWYG アプリケーションを作成するいないとします。 たとえば、テキスト エディターを印刷の太字のフォントを使用しますが、画面上の太字のテキストを示す制御コードが表示されますを検討します。 このような状況でを使用して`OnDraw`画面に対して厳密にします。 オーバーライドする場合`OnPrint`への呼び出しを置き換える`OnDraw`描画の個別の関数の呼び出しで。 その関数は、画面に表示しない属性を使用する用紙に表示される方法をドキュメントに描画します。

##  <a name="_core_printer_pages_vs.._document_pages"></a> プリンターのページとドキュメント ページ

ページ番号を参照する場合、ページのプリンターの概念と、ページのドキュメントの概念を区別するために必要な場合があります。 プリンターのポイントのビューからは、ページは、1 枚の用紙が。 ただし、1 枚の用紙は、ドキュメントの 1 つのページを必ずしも等しくないです。 たとえば、ニュースレター、場所、シートは折りたためませんには、印刷する場合 1 枚用紙にはにサイド バイ サイドのドキュメントの最初と最後のページが含まれます。 同様に、スプレッドシートを印刷する場合、ドキュメントがで構成されているページのすべての。 代わりに、1 枚用紙にはには、1 ~ 20 個、6 ~ 10 の列の行が含まれます。

すべてのページ番号、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体は、プリンターのページを参照してください。 Framework 呼び出し`OnPrepareDC`と`OnPrint`とに 1 回 1 枚の用紙をプリンターにパススルーされます。 オーバーライドする場合、 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)ドキュメントの長さを指定する関数をプリンターのページを使用する必要があります。 一対一の対応関係がある場合 (つまり、1 つのプリンター ページ等しい 1 つのドキュメント ページ)、これは簡単です。 その一方で、ドキュメントのページとプリンター ページ直接対応しない場合は、それらの間に変換する必要があります。 たとえば、スプレッドシートを印刷します。 オーバーライドするときに`OnPreparePrinting`、数枚の紙は、スプレッドシート全体を印刷し、呼び出すときにその値を使用する必要がありますを計算する必要があります、`SetMaxPage`のメンバー関数`CPrintInfo`します。 同様に、オーバーライドするときに`OnPrepareDC`、変換する必要があります*m_nCurPage*がその特定のシートに表示され、ビューポートの原点を適宜調整する行と列の範囲にします。

##  <a name="_core_print.2d.time_pagination"></a> 印刷時の改ページ

場合によっては、ビュー クラスご存じない事前にどれくらいの時間、ドキュメントが実際に印刷されるまでです。 たとえば、WYSIWYG アプリケーションではないとしますので、画面上のドキュメントの長さは印刷時に、その長さと一致しません。

これをオーバーライドするときに問題が発生[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)ビュー クラス: の値を渡すことはできません、`SetMaxPage`の関数、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体の長さがわからないため、ドキュメントです。 [印刷] ダイアログ ボックスを使用して停止するページ番号を指定しない場合、framework は印刷ループを停止するタイミングを認識しません。 印刷ループを停止するかを判断する唯一の方法では、ドキュメントを印刷し、終了時に参照してください。 ビュー クラスは、終わりに達したときに、フレームワークに通知し、印刷するときに、ドキュメントの最後のチェックが必要があります。

ビュー クラスの依存フレームワーク[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)を指示する関数をいつ中止します。 各呼び出しの後`OnPrepareDC`、フレームワークのメンバーを確認します、`CPrintInfo`と呼ばれる構造*m_bContinuePrinting*します。 既定値は**TRUE です。** その状態が、限りフレームワークは印刷ループを続行します。 設定されている場合**FALSE**フレームワークが停止します。 印刷時の改ページ調整を実行するのには、オーバーライド`OnPrepareDC`ドキュメントの末尾に達すると、および設定するかどうかを確認する*m_bContinuePrinting*に**FALSE**必要があるとき。

既定の実装`OnPrepareDC`設定*m_bContinuePrinting*に**FALSE**現在のページが 1 より大きい場合。 これは、ドキュメントの長さが指定されていない場合、フレームワークを想定しているドキュメントが 1 つのページが時間の長いことを意味します。 この 1 つの結果は、の基底クラスのバージョンを呼び出す場合は、注意する必要があります`OnPrepareDC`します。 あるいない*m_bContinuePrinting*なります**TRUE**基底クラスのバージョンを呼び出した後。

### <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ヘッダーとフッター](../mfc/headers-and-footers.md)

- [GDI リソースの割り当てください。](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>関連項目

[印刷](../mfc/printing.md)<br/>
[CView クラス](../mfc/reference/cview-class.md)<br/>
[CDC クラス](../mfc/reference/cdc-class.md)