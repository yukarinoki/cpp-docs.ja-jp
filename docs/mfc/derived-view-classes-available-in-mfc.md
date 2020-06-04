---
title: MFC で使用できる派生ビュー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 12b31074e4fcc2ed6a83e3669e1044f5b9caedab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373503"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC で使用できる派生ビュー クラス

次の表は、MFC のビュー クラスと、それらの相互関係を示しています。 ビュー クラスの機能は、派生元の MFC ビュー クラスによって異なります。

### <a name="view-classes"></a>クラスを表示する

|クラス|説明|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|すべてのビューの基本クラス。|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|`CTreeView`、 、 `CListView`、`CEditView`および`CRichEditView`の基本クラス。 これらのクラスを使用すると、示された Windows コモン コントロールでドキュメント/ビュー アーキテクチャを使用できます。|
|[CEditView](../mfc/reference/ceditview-class.md)|Windows エディット ボックス コントロールに基づく単純なビュー。 テキストの入力と編集が可能で、単純なテキスト エディタ アプリケーションのベースとして使用できます。 `CRichEditView` も参照してください。|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|[オブジェクトを](../mfc/reference/cricheditctrl-class.md)含むビュー。 このクラスは`CEditView`に似ていますが、 `CEditView``CRichEditView`とは異なり、書式設定されたテキストを処理します。|
|[CListView](../mfc/reference/clistview-class.md)|[オブジェクト](../mfc/reference/clistctrl-class.md)を含むビュー。|
|[Cツリービュー](../mfc/reference/ctreeview-class.md)|Visual C++ の [ソリューション エクスプローラ] ウィンドウに似たビューの[場合は、CTreeCtrl](../mfc/reference/ctreectrl-class.md)オブジェクトを含むビュー。|
|[CScrollView](../mfc/reference/cscrollview-class.md)|、 、`CFormView``CRecordView`および`CDaoRecordView`の基本クラス。 ビューの内容をスクロールする実装。|
|[CFormView](../mfc/reference/cformview-class.md)|フォーム ビュー、コントロールを含むビュー。 フォーム ベースのアプリケーションは、このようなフォーム インターフェイスを 1 つ以上提供します。|
|[ビュー](../mfc/reference/chtmlview-class.md)|アプリケーションのユーザーが Www Web 上のサイト、およびローカル ファイル システム内のフォルダ、およびネットワーク上のフォルダを参照できる Web ブラウザ ビュー。 Web ブラウザ ビューは、Active ドキュメント コンテナーとしても機能します。|
|[CRecordView](../mfc/reference/crecordview-class.md)|コントロールに ODBC データベース レコードを表示するフォーム ビュー。 プロジェクトで ODBC サポートを選択した場合、ビューの基本クラスは`CRecordView`です。 ビューはオブジェクトに`CRowset`接続されています。|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|コントロール内の DAO データベース レコードを表示するフォーム ビュー。 プロジェクトで DAO サポートを選択した場合、ビューの基本クラスは`CDaoRecordView`です。 ビューはオブジェクトに`CDaoRecordset`接続されています。|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|OLE DB レコードをコントロールに表示するフォーム ビュー。 プロジェクトで OLE DB サポートを選択した場合、ビューの基本クラス`COleDBRecordView`は です。 ビューはオブジェクトに`CRowset`接続されています。|

> [!NOTE]
> MFC バージョン 4.0`CEditView`の時点では`CCtrlView`、 から派生しています。

これらのクラスをアプリケーションで使用するには、アプリケーションのビュー クラスを派生させます。 関連情報については、「[ビューのスクロールとスケーリング」](../mfc/scrolling-and-scaling-views.md)を参照してください。 データベース クラスの詳細については、「概要[: データベース プログラミング](../data/data-access-programming-mfc-atl.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ビューの使用](../mfc/using-views.md)
