---
title: マルチページ ドキュメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24ad3e99399e4d5db45606accfd58512f3950f26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355273"
---
# <a name="multipage-documents"></a>マルチページ ドキュメント
この記事では、Windows 印刷プロトコルについて説明し、複数のページを含むドキュメントを印刷する方法について説明します。 アーティクルでは、次のトピックについて説明します。  
  
-   [印刷のプロトコル](#_core_the_printing_protocol)  
  
-   [ビュー クラスの関数をオーバーライドします。](#_core_overriding_view_class_functions)  
  
-   [改ページ](#_core_pagination)  
  
-   [プリンターのページとドキュメント ページ](#_core_printer_pages_vs.._document_pages)  
  
-   [印刷時の改ページ](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a> 印刷のプロトコル  
 マルチページ ドキュメントを印刷するには、フレームワークとビューの次のように対話します。 最初に、フレームワークを表示、**印刷**ダイアログ ボックスで、プリンター、および呼び出し用のデバイス コンテキストを作成、 [StartDoc](../mfc/reference/cdc-class.md#startdoc)のメンバー関数、 [CDC](../mfc/reference/cdc-class.md)オブジェクト。 次に、ドキュメントの各ページでは、フレームワーク、 [StartPage](../mfc/reference/cdc-class.md#startpage)のメンバー関数、`CDC`オブジェクト、ページ、および呼び出しを印刷するビュー オブジェクトに指示、 [EndPage](../mfc/reference/cdc-class.md#endpage)メンバー関数。 ビューを呼び出す場合は、特定のページを開始する前に、プリンター モードを変更する必要があります、[印刷](../mfc/reference/cdc-class.md#resetdc)、更新プログラム、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)新しいプリンター モードの情報を含む構造体。 ドキュメント全体が印刷されたときに、フレームワーク、 [EndDoc](../mfc/reference/cdc-class.md#enddoc)メンバー関数。  
  
##  <a name="_core_overriding_view_class_functions"></a> ビュー クラスの関数をオーバーライドします。  
 [CView](../mfc/reference/cview-class.md)クラスは印刷中に、フレームワークによって呼び出されるいくつかのメンバー関数を定義します。 ビュー クラスでこれらの関数をオーバーライドするでは、フレームワークの印刷ロジックとビュー クラスの印刷ロジックの間の接続を提供します。 次の表には、これらのメンバー関数が一覧表示します。  
  
### <a name="cviews-overridable-functions-for-printing"></a>印刷用 CView のオーバーライド可能な関数  
  
|名前|オーバーライドする理由|  
|----------|---------------------------|  
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|[印刷] ダイアログ ボックスで、ドキュメントの長さなどの値を挿入するには|  
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|フォントまたはその他の GDI リソースを割り当てる|  
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|特定のページにデバイス コンテキストの属性を調整するには、かを印刷時の改ページ調整を行うには|  
|[OnPrint](../mfc/reference/cview-class.md#onprint)|特定のページを印刷するには|  
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI リソースの割り当てを解除するには|  
  
 同様に、他の関数での印刷関連の処理を行うことができますが、これらの関数は、印刷プロセスを促進します。  
  
 印刷プロセスに必要な手順を示しています、場所を示しています。 次の図の各`CView`関数が呼び出されるメンバーの印刷します。 この記事の残りの部分では、さらに詳しくは、この手順のほとんどについて説明します。 印刷プロセスの追加部分については、記事[GDI リソースの割り当て](../mfc/allocating-gdi-resources.md)です。  
  
 ![印刷ループ プロセス](../mfc/media/vc37c71.gif "vc37c71")  
印刷ループ  
  
##  <a name="_core_pagination"></a> 改ページ  
 フレームワークは、多くの印刷ジョブに関する情報の格納、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体。 いくつかの値の`CPrintInfo`改ページに関係するもの以外の場合はこれらの値は次の表に示すようにアクセスします。  
  
### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo に格納されているページ数情報  
  
|メンバー変数または<br /><br /> 関数名|参照されているページ数|  
|-----------------------------------------------|----------------------------|  
|`GetMinPage`/`SetMinPage`|ドキュメントの最初のページ|  
|`GetMaxPage`/`SetMaxPage`|ドキュメントの最後のページ|  
|`GetFromPage`|最初のページを印刷します。|  
|`GetToPage`|最後のページを印刷します。|  
|`m_nCurPage`|現在印刷中 ページします。|  
  
 1、ページ番号の開始は、最初のページ番号が 1、0 ではありません。 これらおよび他のメンバーの詳細については[CPrintInfo](../mfc/reference/cprintinfo-structure.md)を参照してください、 *『 MFC リファレンス*です。  
  
 印刷プロセスの先頭には、フレームワークによって、ビューの[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)へのポインターを引数としてメンバー関数を`CPrintInfo`構造体。 アプリケーションのウィザードの実装を提供する`OnPreparePrinting`を呼び出す[DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting)、別のメンバー関数の`CView`します。 `DoPreparePrinting` [印刷] ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成する関数です。  
  
 この時点でアプリケーションは、ページ数が、ドキュメントでは認識しません。 ドキュメントの最初と最後のページ数の既定値 1 と 0 xffff を使用します。 ドキュメントがページの数がわかっている場合は、オーバーライド`OnPreparePrinting`を呼び出すと [の SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage)、`CPrintInfo`に送信する前に構造体`DoPreparePrinting`です。 これにより、ドキュメントの長さを指定できます。  
  
 `DoPreparePrinting` [印刷] ダイアログ ボックスが表示されます。 返されたときに、`CPrintInfo`構造には、ユーザーによって指定された値が含まれています。 ページの選択範囲のみを印刷する場合は、そのユーザーを指定できます開始と終了値、[印刷] ダイアログ ボックスのページ番号。 フレームワークを使用してこれらの値を取得する、`GetFromPage`と`GetToPage`関数の[CPrintInfo](../mfc/reference/cprintinfo-structure.md)です。 ユーザーがページの範囲を指定していない場合、フレームワークによって呼び出されます`GetMinPage`と`GetMaxPage`文書全体を印刷に返される値を使用しています。  
  
 印刷するドキュメントの各ページでは、フレームワークを呼び出し、2 つのメンバー関数、ビュー クラスで[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)と[OnPrint](../mfc/reference/cview-class.md#onprint)、し、各関数の 2 つのパラメーターを渡します: へのポインター、 [CDC](../mfc/reference/cdc-class.md)オブジェクトとへのポインター、`CPrintInfo`構造体。 たびに、フレームワークによって`OnPrepareDC`と`OnPrint`で別の値を渡す、`m_nCurPage`のメンバー、`CPrintInfo`構造体。 この方法では、フレームワークは、ビューに対し、どのページを印刷するかを示します。  
  
 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)メンバー関数は、画面の表示にも使用します。 やすくなる図面行われる前に、デバイス コンテキストの調整。 `OnPrepareDC` 印刷での同様の役割の機能がいくつかの相違点がある場合: 最初に、`CDC`オブジェクト画面デバイス コンテキスト、および秒ではなくプリンター デバイス コンテキストを表します、`CPrintInfo`オブジェクトが 2 番目のパラメーターとして渡されます。 (このパラメーターは**NULL**とき`OnPrepareDC`画面に対して呼び出されます)。オーバーライド`OnPrepareDC`ページの印刷に基づき、デバイス コンテキストを調整します。 たとえば、ビューポートの原点と、ドキュメントの適切な部分を取得印刷されるようにクリッピング領域を移動することができます。  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint)メンバー関数は、ページの印刷を実行します。 アーティクル[既定の印刷方法](../mfc/how-default-printing-is-done.md)フレームワークを呼び出す方法を示しています。 [OnDraw](../mfc/reference/cview-class.md#ondraw)印刷を実行するプリンター デバイス コンテキストを使用します。 フレームワークでは具体的には、`OnPrint`で、`CPrintInfo`構造と、デバイス コンテキストおよび`OnPrint`デバイス コンテキストを渡します`OnDraw`です。 オーバーライド`OnPrint`レンダリング印刷時にだけ、および画面表示ではなく行う必要がありますを実行します。 たとえば、ヘッダーまたはフッターを印刷する (記事を参照して[ヘッダーとフッター](../mfc/headers-and-footers.md)詳細については)。 呼び出す`OnDraw`のオーバーライドから`OnPrint`画面表示の両方に共通の表示と印刷を行う。  
  
 ファクトを`OnDraw`レンダリングでは両方の画面表示と印刷の場合、アプリケーションが WYSIWYG であることを意味するは:"What you see is what you get"。 ただし、WYSIWYG アプリケーションを作成するいないとします。 たとえば、印刷の太字のフォントを使用しますが、画面上の太字のテキストを示すためにコントロールのコードを表示するエディターのテキストを検討します。 使用するこのような状況で、`OnDraw`画面表示の厳密にします。 オーバーライドする場合`OnPrint`への呼び出しに置き換える`OnDraw`描画の個別の関数を呼び出しています。 その関数は、画面に表示しない属性を使用する用紙に表示される方法、ドキュメントを描画します。  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a> プリンターのページとします。ドキュメントのページ  
 ページ番号を参照するとき、ページのプリンターの概念と、ページのドキュメントの概念を区別する必要があります。 観点から、プリンターのページは、1 枚の用紙します。 ただし、1 枚の用紙必ずしも、ドキュメントの 1 つのページが一致しません。 たとえば、ニュースレター、場所、シートは折りたたむには、印刷する場合 1 枚用紙にはに、ドキュメントでは、サイド バイ サイドの最初と最後のページが含まれます。 同様に、ワークシートを印刷する場合、ドキュメントしないで構成されているページのすべてのです。 代わりに、1 枚用紙にはには、1 ~ 20、6 ~ 10 の列の行が含まれます。  
  
 すべてのページ番号、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体は、プリンターのページを参照してください。 フレームワークによって`OnPrepareDC`と`OnPrint`1 枚の用紙がプリンターに送信されるに対して 1 回です。 オーバーライドする場合、 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)関数のドキュメントの長さを指定する、プリンターのページを使用する必要があります。 一対一の対応関係がある場合 (つまり、1 つのプリンターのページと等しくなります 1 つのドキュメント ページ)、これは簡単です。 その一方で、ドキュメントのページと印刷ページ直接対応しない場合は、それらの間に変換する必要があります。 たとえば、スプレッドシートの印刷を検討してください。 オーバーライドする場合`OnPreparePrinting`、数枚の用紙がワークシート全体を印刷して呼び出すときにその値を使用、する必要がありますを計算する必要があります、`SetMaxPage`のメンバー関数`CPrintInfo`です。 同様に、オーバーライドする場合`OnPrepareDC`、変換する必要があります`m_nCurPage`をその特定のシートに表示され、必要に応じて、ビューポートの原点を調整する行と列の範囲にします。  
  
##  <a name="_core_print.2d.time_pagination"></a> 印刷時の改ページ  
 場合によっては、ビュー クラス可能性がありますいないを前もって知って実際に印刷されるまで、どのくらいの時間のドキュメントには。 たとえば、アプリケーションには、WYSIWYG がない場合と仮定しますので、画面上のドキュメントの長さは印刷時の長さと一致しません。  
  
 これをオーバーライドする際に問題が原因[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)ビュー クラス: の値を渡すことはできません、`SetMaxPage`の関数、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体の長さがわからないため、ドキュメントです。 [印刷] ダイアログ ボックスを使用して停止するページ番号を指定しない場合、印刷ループを停止するタイミングをフレームワークに知りません。 印刷ループを停止するタイミングを決定する唯一の方法では、ドキュメントを印刷し、終わりを確認します。 ビュー クラスが印刷される末尾に達したときに、フレームワークを通知中に、ドキュメントの最後のチェックが必要です。  
  
 ビュー クラスの依存フレームワーク[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)を指示する関数をいつ中止します。 呼び出すたび`OnPrepareDC`、フレームワークのメンバーのチェック、`CPrintInfo`と呼ばれる構造`m_bContinuePrinting`です。 既定値は**TRUE です。** 既定値のまま、限りフレームワークは印刷ループを続行します。 設定されている場合**FALSE**フレームワークが停止します。 印刷時の改ページを実行するのには、オーバーライド`OnPrepareDC`ドキュメントの末尾に達すると、および設定するかどうかをチェック`m_bContinuePrinting`に**FALSE**を得た場合。  
  
 既定の実装`OnPrepareDC`設定`m_bContinuePrinting`に**FALSE**現在のページが 1 より大きい場合。 これは、ドキュメントの長さが指定されていない場合、フレームワークを想定している 1 つのページの長さは、ドキュメントを意味します。 この結果は、の基本クラスのバージョンを呼び出す場合は、注意する必要があります`OnPrepareDC`です。 だない`m_bContinuePrinting`なります**TRUE**基底クラスのバージョンの呼び出し後にします。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ヘッダーとフッター](../mfc/headers-and-footers.md)  
  
-   [GDI リソースの割り当てください。](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>関連項目  
 [印刷](../mfc/printing.md)   
 [CView クラス](../mfc/reference/cview-class.md)   
 [CDC クラス](../mfc/reference/cdc-class.md)