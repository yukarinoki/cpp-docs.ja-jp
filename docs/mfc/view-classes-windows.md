---
description: '詳細情報: ビュークラス (Windows)'
title: ビュー クラス (Windows)
ms.date: 09/17/2019
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: f7ad1fb97952468fd2f2bde9560b1a4c18252332
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143105"
---
# <a name="view-classes-windows"></a>ビュー クラス (Windows)

`CView` およびその派生クラスは、フレームウィンドウのクライアント領域を表す子ウィンドウです。 ビューには、データが表示され、ドキュメントの入力が受け入れられます。

ビュークラスは、ドキュメントクラスと、ドキュメントテンプレートオブジェクトを使用するフレームウィンドウクラスに関連付けられています。

[CView](../mfc/reference/cview-class.md)<br/>
ドキュメントのデータのアプリケーション固有のビューの基本クラス。 ビューデータを表示し、ユーザーの入力を受け入れてデータを編集または選択します。 ビュークラスまたはクラスをから派生させ `CView` ます。

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
スクロール機能を持つビューの基本クラスです。 自動スクロールを行うために、からビュークラスを派生させ `CScrollView` ます。

## <a name="form-and-record-views"></a>フォームビューとレコードビュー

フォームビューはスクロールビューでもあります。 これらは、ダイアログボックステンプレートに基づいています。

レコードビューはフォームビューから派生します。 ダイアログボックステンプレートに加えて、データベースへの接続もあります。

[CFormView](../mfc/reference/cformview-class.md)<br/>
ダイアログボックステンプレートでレイアウトが定義されているスクロールビュー。 からクラスを派生させ、 `CFormView` ダイアログボックステンプレートに基づいてユーザーインターフェイスを実装します。

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
データアクセスオブジェクト (DAO) レコードセットオブジェクトに直接接続されたフォームビューを提供します。 すべてのフォームビューと同様に、は `CDaoRecordView` ダイアログボックステンプレートに基づいています。 DAO は Access データベースで使用され、Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Open Database Connectivity (ODBC) レコードセットオブジェクトに直接接続されたフォームビューを提供します。 すべてのフォームビューと同様に、は `CRecordView` ダイアログボックステンプレートに基づいています。

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
WebBrowser HTML 編集プラットフォームの機能を提供するフォームビュー。

## <a name="control-views"></a>コントロールビュー

コントロールビューでは、コントロールがビューとして表示されます。

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows コントロールに関連付けられているすべてのビューの基本クラス。 以下では、コントロールに基づくビューについて説明します。

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Windows 標準編集コントロールを含むビュー (「 [CEdit](../mfc/reference/cedit-class.md)」を参照)。 エディットコントロールは、テキストの編集、検索、置換、およびスクロール機能をサポートします。

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Windows リッチエディットコントロールを含むビュー (「 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)」を参照)。 リッチエディットコントロールでは、エディットコントロールの機能に加えて、フォント、色、段落書式、および埋め込み OLE オブジェクトがサポートされています。

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows リストコントロールを含むビュー ( [CListCtrl](../mfc/reference/clistctrl-class.md)を参照)。 リストコントロールは、ファイルエクスプローラーの右ペインと同様の方法で、項目のコレクションを表示します。各項目はアイコンとラベルで構成されます。

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Windows ツリーコントロールを含むビュー (「 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)」を参照)。 ツリーコントロールには、ファイルエクスプローラーの左ペインと同様の方法で配置されたアイコンとラベルの階層リストが表示されます。

## <a name="related-classes"></a>関連クラス

`CSplitterWnd` 1つのフレームウィンドウ内に複数のビューを含めることができます。 `CPrintDialog` およびで `CPrintInfo` は、ビューの印刷と印刷のプレビュー機能がサポートされています。 `CRichEditDoc` と `CRichEditCntrItem` は、 `CRichEditView` OLE コンテナー機能を実装するためにと共に使用されます。

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
ユーザーが複数のペインに分割できるウィンドウ。 これらのペインは、ユーザーまたは固定サイズによってサイズ変更できます。

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
には、ファイルを印刷するための標準のダイアログボックスが用意されています。

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
印刷または印刷プレビュージョブに関する情報を格納している構造体。 の印刷アーキテクチャで使用され `CView` ます。

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
に含まれる OLE クライアントアイテムの一覧を保持し `CRichEditView` ます。

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
に格納されている OLE 項目へのクライアント側アクセスを提供 `CRichEditView` します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
