---
title: ビュー クラス (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: 5fc08ec23e0a2b2ba105aa3a633ee862dc452450
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462300"
---
# <a name="view-classes-windows"></a>ビュー クラス (Windows)

`CView` その派生クラスは、フレーム ウィンドウのクライアント領域を表す子ウィンドウ。 ビューは、データを表示し、ドキュメントの入力をそのまま使用します。

ビュー クラスは、ドキュメント クラスとドキュメント テンプレート オブジェクトを使用して、フレーム ウィンドウ クラスに関連付けられます。

[CView](../mfc/reference/cview-class.md)<br/>
ドキュメントのデータのアプリケーション固有のビューの基本クラスです。 ビューは、データを表示し、ユーザー入力を編集したり、データの選択をそのまま使用します。 ビュー クラスまたはクラスから派生`CView`します。

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
スクロール機能を持つビューの基本クラスです。 ビューからクラスを派生`CScrollView`自動スクロールします。

## <a name="form-and-record-views"></a>フォーム ビューとレコード ビュー

フォーム ビューは、スクロール可能なビューでも。 ダイアログ ボックスのテンプレートが基づきます。

レコード ビューは、フォーム ビューから派生します。 ダイアログ ボックス テンプレートだけでなくもデータベースへの接続があります。

[CFormView](../mfc/reference/cformview-class.md)<br/>
レイアウトを持つが、ダイアログ ボックスのテンプレートで定義されているスクロール可能なビュー。 クラスを派生`CFormView` ダイアログ ボックスのテンプレートに基づくユーザー インターフェイスを実装します。

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
フォーム ビューのデータ アクセス オブジェクト (DAO) のレコード セット オブジェクトに直接接続します。 などのすべてのフォーム ビュー、 `CDaoRecordView`  ダイアログ ボックスのテンプレートに基づきます。

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
フォーム ビューの Open Database Connectivity (ODBC) レコード セット オブジェクトに直接接続されています。 などのすべてのフォーム ビュー、 `CRecordView`  ダイアログ ボックスのテンプレートに基づきます。

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
HTML の WebBrowser 編集プラットフォームの機能を提供するフォーム ビュー。

## <a name="control-views"></a>コントロールの表示

コントロールのビューでは、そのビューとしてコントロールが表示されます。

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows のコントロールに関連付けられているすべてのビューの基本クラスです。 コントロールに基づくビューを以下に示します。

[CEditView](../mfc/reference/ceditview-class.md)<br/>
標準の Windows を含むビューの編集コントロール (を参照してください[CEdit](../mfc/reference/cedit-class.md))。 コントロールのサポートのテキストの編集、検索、置換、およびスクロール機能を編集します。

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
豊富な Windows を含むビューの編集コントロール (を参照してください[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 エディット コントロールの機能だけでなく豊富なコントロールのサポートのフォント、色、段落の書式設定、および OLE 埋め込みオブジェクトを編集します。

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows のリスト コントロールを含むビュー (を参照してください[CListCtrl](../mfc/reference/clistctrl-class.md))。 リスト コントロールには、アイコンとラベルをファイル エクスプ ローラーの右側のウィンドウと同様の方法で構成される各項目のコレクションが表示されます。

[Ctreeview の比較](../mfc/reference/ctreeview-class.md)<br/>
Windows のツリー コントロールを含むビュー (を参照してください[CTreeCtrl](../mfc/reference/ctreectrl-class.md))。 ツリー コントロールでは、ファイル エクスプ ローラーの左側のウィンドウと同様の方法で配置されたラベルとアイコンの階層リストを表示します。

## <a name="related-classes"></a>関連するクラス

`CSplitterWnd` 1 つのフレーム ウィンドウ内で複数のビューであることができます。 `CPrintDialog` `CPrintInfo`ビューの印刷と印刷プレビュー機能をサポートします。 `CRichEditDoc` `CRichEditCntrItem`を併用`CRichEditView`OLE コンテナーの機能を実装します。

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
このウィンドウは、ユーザーは、複数のペインに分割できますです。 これらのウィンドウは、サイズ、ユーザーまたは固定サイズを変更できます。

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
ファイルの印刷には、標準のダイアログ ボックスを提供します。

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
印刷または印刷プレビュー ジョブに関する情報を含む構造体。 使用される`CView`アーキテクチャ印刷します。

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
含まれる OLE クライアント アイテムの一覧を保持する`CRichEditView`します。

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
Ole 項目に格納されているクライアント側のアクセスを提供する`CRichEditView`します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

