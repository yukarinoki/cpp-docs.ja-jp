---
title: MFC で使用できる派生ビュー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: dc0f0b10ea291db32c576a7d36b7fc19728fa6ce
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616980"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC で使用できる派生ビュー クラス

次の表は、MFC のビュークラスと、それらのクラス間のリレーションシップを示しています。 ビュークラスの機能は、その派生元である MFC ビュークラスに依存します。

### <a name="view-classes"></a>ビュークラス

|クラス|説明|
|-----------|-----------------|
|[CView](reference/cview-class.md)|すべてのビューの基本クラスです。|
|[CCtrlView](reference/cctrlview-class.md)|`CTreeView`、、 `CListView` `CEditView` 、およびの基本クラス `CRichEditView` 。 これらのクラスを使用すると、Windows コモンコントロールでドキュメント/ビューアーキテクチャを使用できます。|
|[CEditView](reference/ceditview-class.md)|Windows のエディットボックスコントロールに基づく単純なビュー。 テキストの入力と編集が可能で、単純なテキストエディターアプリケーションの基礎として使用できます。 `CRichEditView` も参照してください。|
|[CRichEditView](reference/cricheditview-class.md)|[CRichEditCtrl](reference/cricheditctrl-class.md)オブジェクトを含むビューです。 このクラスはに似てい `CEditView` ますが、とは異なり `CEditView` 、 `CRichEditView` 書式設定されたテキストを処理します。|
|[CListView](reference/clistview-class.md)|[CListCtrl](reference/clistctrl-class.md)オブジェクトを含むビューです。|
|[CTreeView](reference/ctreeview-class.md)|Visual C++ のソリューションエクスプローラーウィンドウに似たビューの、 [CTreeCtrl](reference/ctreectrl-class.md)オブジェクトを含むビュー。|
|[CScrollView](reference/cscrollview-class.md)|`CFormView`、 `CRecordView` 、およびの基本クラス `CDaoRecordView` 。 ビューの内容のスクロールを実装します。|
|[CFormView](reference/cformview-class.md)|フォームビュー。コントロールを含むビューです。 フォームベースのアプリケーションは、1つまたは複数のフォームインターフェイスを提供します。|
|[CHtmlView](reference/chtmlview-class.md)|アプリケーションのユーザーが、World Wide Web 上のサイト、およびローカルファイルシステムおよびネットワーク上のフォルダーを参照できる Web ブラウザービュー。 Web ブラウザービューは、アクティブなドキュメントコンテナーとして機能することもできます。|
|[CRecordView](reference/crecordview-class.md)|コントロールに ODBC データベースレコードを表示するフォームビュー。 プロジェクトで ODBC サポートを選択した場合、ビューの基本クラスは `CRecordView` です。 ビューがオブジェクトに接続されてい `CRowset` ます。|
|[CDaoRecordView](reference/cdaorecordview-class.md)|コントロールに DAO データベースレコードを表示するフォームビュー。 プロジェクトで [DAO サポート] を選択した場合、ビューの基本クラスはに `CDaoRecordView` なります。 ビューがオブジェクトに接続されてい `CDaoRecordset` ます。|
|[COleDBRecordView](reference/coledbrecordview-class.md)|コントロールに OLE DB レコードを表示するフォームビュー。 プロジェクトで OLE DB サポートを選択した場合、ビューの基本クラスは `COleDBRecordView` です。 ビューがオブジェクトに接続されてい `CRowset` ます。|

> [!NOTE]
> MFC バージョン4.0 以降、 `CEditView` はから派生 `CCtrlView` します。

これらのクラスをアプリケーションで使用するには、アプリケーションのビュークラスを派生させます。 関連情報については、「[ビューのスクロールとスケーリング](scrolling-and-scaling-views.md)」を参照してください。 データベースクラスの詳細については、「[概要: データベースプログラミング](../data/data-access-programming-mfc-atl.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ビューの使用](using-views.md)
