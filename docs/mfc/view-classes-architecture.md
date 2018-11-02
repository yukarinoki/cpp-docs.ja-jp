---
title: ビュー クラス (アーキテクチャ)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
ms.openlocfilehash: 7855f152e340b488d64f01dbf290034e1bdbc9b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647300"
---
# <a name="view-classes-architecture"></a>ビュー クラス (アーキテクチャ)

`CView` その派生クラスは、フレーム ウィンドウのクライアント領域を表す子ウィンドウ。 ビューは、データを表示し、ドキュメントの入力をそのまま使用します。

ビュー クラスは、ドキュメント クラスとドキュメント テンプレート オブジェクトを使用して、フレーム ウィンドウ クラスに関連付けられます。

[CView](../mfc/reference/cview-class.md)<br/>
ドキュメントのデータのアプリケーション固有のビューの基本クラスです。 ビューは、データを表示し、ユーザー入力を編集したり、データの選択をそのまま使用します。 独自のビュー クラスを派生`CView`します。

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
スクロール機能を持つビューの基本クラスです。 ビューからクラスを派生`CScrollView`自動スクロールします。

## <a name="form-and-record-views"></a>フォーム ビューとレコード ビュー

フォーム ビューは、スクロール可能なビューでも。 ダイアログ ボックスのテンプレートが基づきます。

レコード ビューは、フォーム ビューから派生します。 ダイアログ ボックス テンプレートだけでなくもデータベースへの接続があります。

[CFormView](../mfc/reference/cformview-class.md)<br/>
レイアウトを持つが、ダイアログ ボックスのテンプレートで定義されているスクロール可能なビュー。 クラスを派生`CFormView` ダイアログ ボックスのテンプレートに基づくユーザー インターフェイスを実装します。

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
フォーム ビューのデータ アクセス オブジェクト (DAO) のレコード セット オブジェクトに直接接続します。 などのすべてのフォーム ビュー、 `CDaoRecordView`  ダイアログ ボックスのテンプレートに基づきます。

[CHtmlView](../mfc/reference/chtmlview-class.md)<br/>
Web のブラウズ、アプリケーション内のコントロールをサポートしています。 コントロールには、MFC で動的 HTML がサポートされています。

[COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)<br/>
フォーム ビューの MFC OLE DB のサポートを提供します。

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
フォーム ビューの Open Database Connectivity (ODBC) レコード セット オブジェクトに直接接続されています。 などのすべてのフォーム ビュー、 `CRecordView`  ダイアログ ボックスのテンプレートに基づきます。

## <a name="control-views"></a>コントロールの表示

コントロールのビューでは、そのビューとしてコントロールが表示されます。

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows のコントロールに関連付けられているすべてのビューの基本クラスです。 コントロールに基づくビューを以下に示します。

[CEditView](../mfc/reference/ceditview-class.md)<br/>
標準の Windows を含むビューの編集コントロール (を参照してください[CEdit](../mfc/reference/cedit-class.md))。 コントロールのサポートのテキストの編集、検索、置換、およびスクロール機能を編集します。

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
豊富な Windows を含むビューの編集コントロール (を参照してください[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 エディット コントロールの機能だけでなく豊富なコントロールのサポートのフォント、色、段落の書式設定、および OLE 埋め込みオブジェクトを編集します。

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows のリスト コントロールを含むビュー (を参照してください[CListCtrl](../mfc/reference/clistctrl-class.md))。 リスト コントロールでは、ファイル エクスプ ローラーの右側のウィンドウと同様の方法で、アイコンと文字列が表示されます。

[Ctreeview の比較](../mfc/reference/ctreeview-class.md)<br/>
Windows のツリー コントロールを含むビュー (を参照してください[CTreeCtrl](../mfc/reference/ctreectrl-class.md))。 ツリー コントロールでは、アイコンとファイル エクスプ ローラーの左側のウィンドウと同様の方法で階層として配置文字列が表示されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

