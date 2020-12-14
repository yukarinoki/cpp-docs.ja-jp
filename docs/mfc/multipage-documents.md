---
description: '詳細情報: マルチページドキュメント'
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
ms.openlocfilehash: a7824097e0d8de6dd91c3bbd73a1eea08efb6912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251051"
---
# <a name="multipage-documents"></a>マルチページ ドキュメント

この記事では、Windows 印刷プロトコルについて説明し、複数のページを含むドキュメントを印刷する方法について説明します。 この記事では、次のトピックについて説明します。

- [印刷プロトコル](#_core_the_printing_protocol)

- [オーバーライド (ビュークラス関数を)](#_core_overriding_view_class_functions)

- [改ページ位置の自動修正](#_core_pagination)

- [プリンターページとドキュメントページ](#_core_printer_pages_vs.._document_pages)

- [印刷時のページ割り当て](#_core_print.2d.time_pagination)

## <a name="the-printing-protocol"></a><a name="_core_the_printing_protocol"></a> 印刷プロトコル

複数ページのドキュメントを印刷するために、フレームワークとビューは次のように対話します。 最初に、フレームワークによって [**印刷**] ダイアログボックスが表示され、プリンターのデバイスコンテキストが作成されて、 [CDC](reference/cdc-class.md)オブジェクトの [StartDoc](reference/cdc-class.md#startdoc)メンバー関数が呼び出されます。 次に、ドキュメントのページごとに、フレームワークがオブジェクトの [StartPage](reference/cdc-class.md#startpage) メンバー関数を呼び出し `CDC` 、ページを印刷するように view オブジェクトに指示し、 [EndPage](reference/cdc-class.md#endpage) メンバー関数を呼び出します。 特定のページを開始する前にプリンターモードを変更する必要がある場合、ビューは [Resetdc](reference/cdc-class.md#resetdc)を呼び出します。これにより、新しいプリンターモード情報を含む [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 構造体が更新されます。 ドキュメント全体が印刷されると、フレームワークは [EndDoc](reference/cdc-class.md#enddoc) メンバー関数を呼び出します。

## <a name="overriding-view-class-functions"></a><a name="_core_overriding_view_class_functions"></a> オーバーライド (ビュークラス関数を)

[CView](reference/cview-class.md)クラスは、印刷時にフレームワークによって呼び出されるいくつかのメンバー関数を定義します。 ビュークラスでこれらの関数をオーバーライドすることによって、フレームワークの印刷ロジックとビュークラスの印刷ロジック間の接続を提供します。 これらのメンバー関数の一覧を次の表に示します。

### <a name="cviews-overridable-functions-for-printing"></a>CView のオーバーライド可能な印刷用関数

|名前|オーバーライドの理由|
|----------|---------------------------|
|[OnPreparePrinting](reference/cview-class.md#onprepareprinting)|[印刷] ダイアログボックスに値を挿入する場合は (特にドキュメントの長さ)|
|[OnBeginPrinting](reference/cview-class.md#onbeginprinting)|フォントまたはその他の GDI リソースを割り当てるには|
|[OnPrepareDC](reference/cview-class.md#onpreparedc)|特定のページのデバイスコンテキストの属性を調整するには、または印刷時の改ページ位置の自動修正を行うには|
|[OnPrint](reference/cview-class.md#onprint)|特定のページを印刷するには|
|[OnEndPrinting](reference/cview-class.md#onendprinting)|GDI リソースの割り当てを解除するには|

印刷関連の処理も他の関数でも実行できますが、これらの関数は印刷プロセスを駆動しています。

次の図は、印刷プロセスに必要な手順を示しています。また、の各 `CView` 印刷メンバー関数が呼び出される場所を示しています。 この記事の残りの部分では、これらの手順の大部分について詳しく説明します。 印刷プロセスの追加部分については、「 [GDI リソースの割り当て](allocating-gdi-resources.md)」で説明されています。

![印刷ループ処理](../mfc/media/vc37c71.gif "印刷ループ処理") <br/>
印刷ループ

## <a name="pagination"></a><a name="_core_pagination"></a> ページ割り付け

フレームワークは、印刷ジョブに関する情報の多くを [CPrintInfo](reference/cprintinfo-structure.md) 構造体に格納します。 の値のいくつかは、 `CPrintInfo` 次の表に示すように、改ページ位置の自動修正に関連しています。

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo に格納されているページ番号情報

|メンバー変数または<br /><br /> 関数名|参照されたページ番号|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|ドキュメントの最初のページ|
|`GetMaxPage`/`SetMaxPage`|ドキュメントの最後のページ|
|`GetFromPage`|印刷される最初のページ|
|`GetToPage`|最後に印刷されるページ|
|`m_nCurPage`|現在印刷中のページ|

ページ番号は1から始まります。つまり、最初のページの番号は0ではなく1になります。 これらのメンバーと [CPrintInfo](reference/cprintinfo-structure.md)の他のメンバーの詳細については、「 *MFC リファレンス*」を参照してください。

印刷プロセスの開始時に、フレームワークは、構造体へのポインターを渡して、ビューの [OnPreparePrinting](reference/cview-class.md#onprepareprinting) メンバー関数を呼び出し `CPrintInfo` ます。 アプリケーションウィザードでは、の `OnPreparePrinting` 別のメンバー関数 [DoPreparePrinting](reference/cview-class.md#doprepareprinting)を呼び出すの実装が用意されて `CView` います。 `DoPreparePrinting` は、[印刷] ダイアログボックスを表示し、プリンターデバイスコンテキストを作成する関数です。

この時点で、アプリケーションはドキュメント内のページ数を認識していません。 ドキュメントの最初と最後のページの番号には、既定値の1と0xFFFF が使用されます。 ドキュメントに含まれるページ数がわかっている場合は、 `OnPreparePrinting` に送信する前に、構造体の [SetMaxPage]--brokenlink--(reference/cprintinfo # SetMaxPage) をオーバーライドして呼び出し `CPrintInfo` `DoPreparePrinting` ます。 これにより、ドキュメントの長さを指定できます。

`DoPreparePrinting` 次に、[印刷] ダイアログボックスが表示されます。 が返された場合、 `CPrintInfo` 構造体にはユーザーによって指定された値が含まれます。 ユーザーが選択した範囲のページだけを印刷する場合は、[印刷] ダイアログボックスで開始ページ番号と終了ページ番号を指定できます。 フレームワークは、 `GetFromPage` `GetToPage` [CPrintInfo](reference/cprintinfo-structure.md)の関数と関数を使用してこれらの値を取得します。 ユーザーがページ範囲を指定しない場合、フレームワークはとを呼び出し、 `GetMinPage` `GetMaxPage` 返された値を使用してドキュメント全体を印刷します。

フレームワークは、印刷するドキュメントのページごとに、2つのメンバー関数をビュークラス [OnPrepareDC](reference/cview-class.md#onpreparedc) と [OnPrint](reference/cview-class.md#onprint)に呼び出し、各関数に2つのパラメーター ( [CDC](reference/cdc-class.md) オブジェクトへのポインターと `CPrintInfo` 構造体へのポインター) を渡します。 フレームワークがおよびを呼び出すたび `OnPrepareDC` `OnPrint` に、構造体の *m_nCurPage* メンバーに異なる値が渡さ `CPrintInfo` れます。 このようにして、フレームワークは印刷するページを表示するように指示します。

[OnPrepareDC](reference/cview-class.md#onpreparedc)メンバー関数は、画面の表示にも使用されます。 描画が実行される前に、デバイスコンテキストの調整が行われます。 `OnPrepareDC` 印刷でも同様の役割を果たしますが、2つの違いがあります。まず、 `CDC` オブジェクトが画面デバイスコンテキストではなくプリンターデバイスコンテキストを表し、2番目の `CPrintInfo` パラメーターとしてオブジェクトが渡されます。 (画面表示のためにが呼び出されると、このパラメーターは **NULL** に `OnPrepareDC` なります)。 `OnPrepareDC` 印刷されるページに基づいてデバイスコンテキストを調整するには、をオーバーライドします。 たとえば、ビューポートの原点とクリッピング領域を移動して、ドキュメントの適切な部分が印刷されるようにすることができます。

[OnPrint](reference/cview-class.md#onprint)メンバー関数は、ページの実際の印刷を実行します。 この記事では、 [既定の印刷方法につい](how-default-printing-is-done.md) て、フレームワークがプリンターデバイスコンテキストで [OnDraw](reference/cview-class.md#ondraw) を呼び出して印刷を実行する方法を示します。 より正確には、フレームワークは `OnPrint` `CPrintInfo` 構造とデバイスコンテキストを使用してを呼び出し、 `OnPrint` デバイスコンテキストをに渡し `OnDraw` ます。 をオーバーライドして、 `OnPrint` 印刷中にのみ実行し、画面の表示には実行しないようにする必要があるレンダリングを実行します。 たとえば、ヘッダーまたはフッターを印刷する場合は (詳細については、「 [ヘッダーとフッター](headers-and-footers.md) 」を参照してください)。 次 `OnDraw` に、のオーバーライドからを呼び出して、 `OnPrint` 画面の表示と印刷の両方に共通のレンダリングを実行します。

`OnDraw`画面の表示と印刷の両方に対してレンダリングを実行するという事実は、アプリケーションが WYSIWYG であることを意味しています。 ただし、WYSIWYG アプリケーションを記述していないとします。 たとえば、印刷用に太字のフォントを使用し、画面に太字のテキストを示すコントロールコードを表示するテキストエディターを考えてみます。 このような状況では、 `OnDraw` 画面の表示には厳密にを使用します。 をオーバーライドする場合は `OnPrint` 、の呼び出しを `OnDraw` 別の描画関数の呼び出しに置き換えます。 この関数は、画面に表示されていない属性を使用して、文書を紙に表示する方法を描画します。

## <a name="printer-pages-vs-document-pages"></a><a name="_core_printer_pages_vs.._document_pages"></a> プリンターページとドキュメントページ

ページ番号を参照するときは、プリンターのページの概念とページのドキュメントの概念を区別する必要がある場合があります。 プリンターの観点から見ると、1ページは1枚の用紙です。 ただし、1枚の用紙は、必ずしも文書の1ページと同じではありません。 たとえば、シートを折りたたむニュースレターを印刷する場合、1枚の用紙にドキュメントの最初のページと最後のページの両方が横に並んで表示されることがあります。 同様に、スプレッドシートを印刷する場合、ドキュメントはまったくページで構成されていません。 代わりに、1枚の用紙に 1 ~ 20 の行が含まれている可能性があります。 6 ~ 10 です。

[CPrintInfo](reference/cprintinfo-structure.md)構造体のすべてのページ番号は、プリンターページを参照します。 フレームワークは、 `OnPrepareDC` プリンターを通過 `OnPrint` する用紙のシートごとにとを1回呼び出します。 ドキュメントの長さを指定するために [OnPreparePrinting](reference/cview-class.md#onprepareprinting) 関数をオーバーライドする場合は、プリンターページを使用する必要があります。 1対1の対応がある場合 (つまり、1つのプリンターページが1つのドキュメントページに等しい場合)、これは簡単です。 一方、ドキュメントページとプリンターページが直接対応していない場合は、それらの間で変換を行う必要があります。 たとえば、スプレッドシートを印刷することを検討してください。 をオーバーライドする場合は `OnPreparePrinting` 、スプレッドシート全体を印刷するために必要な用紙のシート数を計算し、のメンバー関数を呼び出すときにその値を使用する必要があり `SetMaxPage` `CPrintInfo` ます。 同様に、をオーバーライドする場合は、 `OnPrepareDC` *m_nCurPage* を特定のシートに表示される行と列の範囲に変換し、それに応じてビューポートの原点を調整する必要があります。

## <a name="print-time-pagination"></a><a name="_core_print.2d.time_pagination"></a> 改ページ位置の Print-Time

場合によっては、実際に印刷されるまで、ビュークラスがドキュメントの長さを事前に把握していないことがあります。 たとえば、アプリケーションが WYSIWYG ではない場合、画面上のドキュメントの長さが印刷時の長さに対応していないとします。

これにより、ビュークラスの [OnPreparePrinting](reference/cview-class.md#onprepareprinting) をオーバーライドするときに問題が発生します。 `SetMaxPage` ドキュメントの長さがわからないため、 [CPrintInfo](reference/cprintinfo-structure.md) 構造体の関数に値を渡すことはできません。 ユーザーが [印刷] ダイアログボックスを使用して停止するページ番号を指定していない場合、フレームワークは、印刷ループをいつ停止するかを認識しません。 印刷ループをいつ停止するかを決定する唯一の方法は、ドキュメントを印刷し、いつ終了するかを確認することです。 ビュークラスは、ドキュメントの印刷中にドキュメントの末尾を確認し、終了に達したことをフレームワークに通知する必要があります。

フレームワークは、ビュークラスの [OnPrepareDC](reference/cview-class.md#onpreparedc) 関数に依存して、停止するタイミングを通知します。 を呼び出すたびに、 `OnPrepareDC` フレームワークは `CPrintInfo` *m_bContinuePrinting* と呼ばれる構造体のメンバーをチェックします。 既定値は **TRUE です。** このままであれば、フレームワークは print ループを続行します。 **FALSE** に設定されている場合、フレームワークは停止します。 印刷時の改ページ位置の自動修正を実行するには、をオーバーライドして、 `OnPrepareDC` ドキュメントの末尾に到達したかどうかを確認し、がある場合は *M_bContinuePrinting* を **FALSE** に設定します。

現在のページが1より大きい場合は、の既定の実装では `OnPrepareDC` *m_bContinuePrinting* **FALSE** に設定されます。 つまり、ドキュメントの長さが指定されていない場合、フレームワークはドキュメントが1ページであることを前提としています。 この1つの結果として、の基本クラスバージョンを呼び出す場合は注意が必要です `OnPrepareDC` 。 基底クラスのバージョンを呼び出した後、 *m_bContinuePrinting* が **TRUE** であると想定しないでください。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ヘッダーとフッター](headers-and-footers.md)

- [GDI リソースの割り当て](allocating-gdi-resources.md)

## <a name="see-also"></a>関連項目

[印刷](printing.md)<br/>
[CView クラス](reference/cview-class.md)<br/>
[CDC クラス](reference/cdc-class.md)
