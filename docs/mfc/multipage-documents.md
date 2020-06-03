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
ms.openlocfilehash: 87912c06a40740d25530235ee421c6c8bfa11aab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370729"
---
# <a name="multipage-documents"></a>マルチページ ドキュメント

この資料では、Windows 印刷プロトコルについて説明し、複数のページを含むドキュメントを印刷する方法について説明します。 この記事では、次のトピックについて説明します。

- [印刷プロトコル](#_core_the_printing_protocol)

- [ビュー クラス関数のオーバーライド](#_core_overriding_view_class_functions)

- [ページネーション](#_core_pagination)

- [プリンターページとドキュメントページ](#_core_printer_pages_vs.._document_pages)

- [印刷時間のページネーション](#_core_print.2d.time_pagination)

## <a name="the-printing-protocol"></a><a name="_core_the_printing_protocol"></a>印刷プロトコル

複数ページのドキュメントを印刷するには、フレームワークとビューが次のように相互作用します。 まず、フレームワークは **[印刷**]ダイアログ ボックスを表示し、プリンタのデバイス コンテキストを作成し[、CDC](../mfc/reference/cdc-class.md)オブジェクトの[StartDoc](../mfc/reference/cdc-class.md#startdoc)メンバー関数を呼び出します。 次に、フレームワークは、ドキュメントの各ページに対して、オブジェクトの[StartPage](../mfc/reference/cdc-class.md#startpage)メンバー関数を`CDC`呼び出し、ビュー オブジェクトにページを印刷するように指示し[、EndPage](../mfc/reference/cdc-class.md#endpage)メンバー関数を呼び出します。 特定のページを開始する前にプリンター・モードを変更する必要がある場合、ビューは[ResetDC](../mfc/reference/cdc-class.md#resetdc)を呼び出し、新規プリンター・モード情報を含む[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体を更新します。 ドキュメント全体が印刷されると、フレームワークは[EndDoc](../mfc/reference/cdc-class.md#enddoc)メンバー関数を呼び出します。

## <a name="overriding-view-class-functions"></a><a name="_core_overriding_view_class_functions"></a>ビュー クラス関数のオーバーライド

[CView](../mfc/reference/cview-class.md)クラスは、印刷中にフレームワークによって呼び出されるいくつかのメンバー関数を定義します。 ビュー クラスでこれらの関数をオーバーライドすることにより、フレームワークの印刷ロジックとビュー クラスの印刷ロジックとの間の接続を提供します。 次の表に、これらのメンバー関数を示します。

### <a name="cviews-overridable-functions-for-printing"></a>CView の印刷用のオーバーライド可能な関数

|名前|オーバーライドの理由|
|----------|---------------------------|
|[印刷時](../mfc/reference/cview-class.md#onprepareprinting)|[印刷] ダイアログ ボックスに値を挿入するには、特にドキュメントの長さ|
|[オンビギンプリント](../mfc/reference/cview-class.md#onbeginprinting)|フォントまたはその他の GDI リソースを割り当てるには|
|[準備をするDC](../mfc/reference/cview-class.md#onpreparedc)|指定したページのデバイス コンテキストの属性を調整したり、印刷時のページネーションを行ったりするには|
|[Onprint](../mfc/reference/cview-class.md#onprint)|指定したページを印刷するには|
|[オンエンドプリント](../mfc/reference/cview-class.md#onendprinting)|GDI リソースの割り当てを解除するには|

印刷関連の処理は他の機能でも実行できますが、これらの機能は印刷プロセスを推進するものです。

次の図は、印刷プロセスに関連する手順を示し、各`CView`印刷メンバー関数が呼び出される場所を示しています。 この記事の残りの部分では、これらの手順の大部分について詳しく説明します。 印刷プロセスのその他の部分については[、「GDI リソースの割り当て](../mfc/allocating-gdi-resources.md)」を参照してください。

![印刷ループ処理](../mfc/media/vc37c71.gif "印刷ループ処理") <br/>
印刷ループ

## <a name="pagination"></a><a name="_core_pagination"></a> ページ割り付け

フレームワークは、印刷ジョブに関する情報の多くを[CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体に格納します。 の値のいくつかは、ページ`CPrintInfo`ネーションに関連しています。これらの値は、次の表に示すようにアクセスできます。

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo に格納されているページ番号情報

|メンバー変数または<br /><br /> 関数名|参照されているページ番号|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|ドキュメントの最初のページ|
|`GetMaxPage`/`SetMaxPage`|ドキュメントの最後のページ|
|`GetFromPage`|印刷する最初のページ|
|`GetToPage`|印刷する最終ページ|
|`m_nCurPage`|現在印刷中のページ|

ページ番号は 1 から始まり、最初のページは 0 ではなく 1 に番号が付きます。 これらと[CPrintInfo](../mfc/reference/cprintinfo-structure.md)の他のメンバーの詳細については *、MFC リファレンスを参照してください*。

印刷プロセスの開始時に、フレームワークはビューの[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)メンバー関数を呼び出し、構造体へのポインター`CPrintInfo`を渡します。 アプリケーション ウィザードは、その呼`OnPreparePrinting`び出しの実装を提供します[。](../mfc/reference/cview-class.md#doprepareprinting) `CView` `DoPreparePrinting`は、[印刷] ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成する関数です。

この時点では、ドキュメント内のページ数がわかりません。 ドキュメントの最初と最後のページの番号にデフォルト値 1 と 0xFFFF が使用されます。 ドキュメントのページ数がわかっている場合は、ドキュメントを`OnPreparePrinting`に送信する前に、`CPrintInfo`その構造体の [SetMaxPage] --壊れたリンク -- (参照/cprintinfo-class.md#setmaxpage) をオーバーライドして呼び出します`DoPreparePrinting`。 ドキュメントの長さを指定できます。

`DoPreparePrinting`をクリックすると、[印刷] ダイアログ ボックスが表示されます。 戻り値が返`CPrintInfo`されるとき、構造体にはユーザーが指定した値が格納されます。 選択した範囲のページのみを印刷する場合は、[印刷] ダイアログ ボックスで開始ページ番号と終了ページ番号を指定できます。 フレームワークは、 および[CPrintInfo](../mfc/reference/cprintinfo-structure.md)の関数を`GetFromPage``GetToPage`使用してこれらの値を取得します。 ユーザーがページ範囲を指定しない場合、フレームワークは、ドキュメント全体`GetMinPage`を`GetMaxPage`印刷するために返された値を呼び出し、使用します。

ドキュメントの各ページを印刷するには、フレームワークは、ビュー クラスの 2 つのメンバー関数[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)と[OnPrint](../mfc/reference/cview-class.md#onprint)を呼び出し、各関数の 2 つのパラメーターを渡`CPrintInfo`します: [CDC](../mfc/reference/cdc-class.md)オブジェクトへのポインターと構造体へのポインター。 フレームワークは、 と`OnPrepareDC``OnPrint`を呼び出すたびに、構造体の*m_nCurPage*メンバーに`CPrintInfo`異なる値を渡します。 このようにして、フレームワークは、どのページを印刷するかをビューに通知します。

[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)メンバー関数は、画面表示にも使用されます。 描画が行われる前に、デバイス コンテキストを調整します。 `OnPrepareDC`印刷で同様の役割を果たしますが、いくつかの違いがあります:最初に`CDC`、オブジェクトは、画面デバイス コンテキストではなく、プリンターのデバイス コンテキストを表`CPrintInfo`し、次に、オブジェクトは 2 番目のパラメーターとして渡されます。 (画面表示用**NULL**に呼`OnPrepareDC`び出された場合、このパラメーターは NULL です。印刷`OnPrepareDC`するページに基づいてデバイス コンテキストを調整する場合はオーバーライドします。 たとえば、ビューポートの原点とクリッピング領域を移動して、ドキュメントの適切な部分が印刷されるようにすることができます。

[OnPrint](../mfc/reference/cview-class.md#onprint)メンバー関数は、ページの実際の印刷を実行します。 「[既定の印刷の実行方法」の記事では、フレームワークが](../mfc/how-default-printing-is-done.md)印刷を実行するためにプリンターデバイス コンテキストを使用して[OnDraw](../mfc/reference/cview-class.md#ondraw)を呼び出す方法を示します。 より正確には、フレームワークは`OnPrint``CPrintInfo`構造体とデバイス コンテキストを呼び出`OnPrint`し、デバイス コンテキストを`OnDraw`に渡します。 画面`OnPrint`表示ではなく、印刷時にのみ実行するレンダリングを実行する場合は、オーバーライドします。 たとえば、ヘッダーやフッターを印刷するには (詳細については、「[ヘッダーとフッター](../mfc/headers-and-footers.md) 」を参照してください)。 次に`OnDraw`、 の`OnPrint`オーバーライドから呼び出して、画面表示と印刷の両方に共通するレンダリングを行います。

画面表示と`OnDraw`印刷の両方のレンダリングを行うということは、アプリケーションがWYSIWYGであることを意味します:「あなたが見るものはあなたが得るものです。 ただし、WYSIWYG アプリケーションを作成していないとします。 たとえば、印刷に太字フォントを使用し、画面上に太字のテキストを示すコントロール コードを表示するテキスト エディターを考えてみます。 このような場合は、画面表示に`OnDraw`厳密に使用します。 オーバーライド`OnPrint`する場合は、 を別`OnDraw`の描画関数の呼び出しに置き換えます。 この関数は、画面に表示しない属性を使用して、文書を紙に表示する方法で描画します。

## <a name="printer-pages-vs-document-pages"></a><a name="_core_printer_pages_vs.._document_pages"></a>プリンターページとドキュメントページ

ページ番号を参照する場合、プリンタのページの概念とドキュメントのページの概念を区別する必要がある場合があります。 プリンタの観点から見ると、ページは 1 枚の用紙です。 ただし、1 枚の用紙が文書の 1 ページに等しいとは限りません。 たとえば、用紙を折りたたむニュースレターを印刷する場合、1 枚の用紙に文書の最初と最後のページが並べて表示されることがあります。 同様に、スプレッドシートを印刷する場合、文書はページで構成されません。 代わりに、1 枚の用紙に行 1 から 20、6 ~ 10 列が含まれることがあります。

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体のすべてのページ番号は、プリンターのページを参照します。 フレームワークは、`OnPrepareDC`プリンタ`OnPrint`を通過する用紙 1 枚につき 1 回呼び出します。 ドキュメントの長さを指定するために[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)関数をオーバーライドする場合は、プリンター ページを使用する必要があります。 1 対 1 の対応 (つまり、1 つのプリンター ページが 1 つのドキュメント ページに等しい) がある場合、これは簡単です。 一方、ドキュメントページとプリンタページが直接対応していない場合は、ページ間を翻訳する必要があります。 たとえば、スプレッドシートを印刷する場合を考えます。 オーバーライドする`OnPreparePrinting`場合は、スプレッドシート全体を印刷するために必要な用紙の枚数を計算し、その値を使用して`SetMaxPage``CPrintInfo`のメンバー関数を呼び出す必要があります。 同様に`OnPrepareDC`、 をオーバーライドする場合は *、m_nCurPage*を特定のシートに表示される行と列の範囲に変換し、それに応じてビューポートの原点を調整する必要があります。

## <a name="print-time-pagination"></a><a name="_core_print.2d.time_pagination"></a>印刷時のページネーション

状況によっては、実際に印刷されるまでのドキュメントの長さをビュー クラスで事前に把握できないことがあります。 たとえば、アプリケーションが WYSIWYG ではないため、画面上のドキュメントの長さが印刷時の長さに対応していないとします。

これにより、ビュー クラスの[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)をオーバーライドするときに問題が発生します: ドキュメントの長さが`SetMaxPage`わからないので[、CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体の関数に値を渡す方法はありません。 ユーザーが [印刷] ダイアログ ボックスの使用を停止するページ番号を指定しない場合、フレームワークは印刷ループを停止するタイミングを認識しません。 印刷ループを停止するタイミングを決定する唯一の方法は、ドキュメントを印刷して、いつ終了するかを確認することです。 ビュー クラスは、印刷中にドキュメントの末尾をチェックし、終了に達したときにフレームワークに通知する必要があります。

フレームワークは、いつ停止する必要があるかを示すために、ビュー クラスの[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)関数に依存しています。 の`OnPrepareDC`呼び出しが行されるたびに、フレームワークは`CPrintInfo`*m_bContinuePrinting*と呼ばれる構造体のメンバーをチェックします。 既定値は**TRUE です。** そのままの状態であれば、フレームワークは印刷ループを継続します。 **FALSE**に設定されている場合、フレームワークは停止します。 印刷時間のページネーションを実行するには、ドキュメント`OnPrepareDC`の末尾に達したかどうかを確認するためにオーバーライドし、ドキュメントの末尾に達したかどうか*をチェックm_bContinuePrinting* FALSE**に設定**します。

現在の`OnPrepareDC`ページが 1 より大きい場合、set の既定の実装は**FALSE**に*m_bContinuePrinting。* つまり、ドキュメントの長さが指定されていない場合、フレームワークはドキュメントの長さが 1 ページであると見なします。 この結果の 1 つは、基本クラスの バージョンを呼び出す`OnPrepareDC`場合は注意する必要があります。 基本クラスのバージョンを呼び出した後 *、m_bContinuePrinting*が**TRUE**になるとは仮定しないでください。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ヘッダーとフッター](../mfc/headers-and-footers.md)

- [GDI リソースの割り当て](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>関連項目

[印刷](../mfc/printing.md)<br/>
[Cビュークラス](../mfc/reference/cview-class.md)<br/>
[CDCクラス](../mfc/reference/cdc-class.md)
