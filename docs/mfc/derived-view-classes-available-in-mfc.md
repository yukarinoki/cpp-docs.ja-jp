---
title: MFC で使用できるビュー クラスを派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b166e64c57482586e145cecc9e79317eea282b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC で使用できる派生ビュー クラス
次の表は、MFC のビュー クラスと相互の関係を示します。 ビュー クラスの機能は、派生元の MFC ビュー クラスに依存します。  
  
### <a name="view-classes"></a>ビュー クラス  
  
|クラス|説明|  
|-----------|-----------------|  
|[CView](../mfc/reference/cview-class.md)|すべてのビューの基本クラスです。|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|基本クラス`CTreeView`、 `CListView`、 `CEditView`、および`CRichEditView`です。 これらのクラスを使用して、指定された Windows コモン コントロールとドキュメント/ビュー アーキテクチャを使用できます。|  
|[CEditView](../mfc/reference/ceditview-class.md)|Windows ベースの単純なビューでは、ボックス コントロールを編集します。 入力とテキストを編集でき、単純なテキスト エディターのアプリケーションの基礎として使用できます。 「`CRichEditView`」も参照してください。|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|ビューを含む、 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)オブジェクト。 このクラスと似ています`CEditView`とは異なり、 `CEditView`、`CRichEditView`書式付きテキストのハンドル。|  
|[CListView](../mfc/reference/clistview-class.md)|ビューを含む、 [CListCtrl](../mfc/reference/clistctrl-class.md)オブジェクト。|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|ビューを含む、 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Visual C でソリューション エクスプ ローラー ウィンドウのようにビューのオブジェクト。|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|基本クラス`CFormView`、 `CRecordView`、および`CDaoRecordView`です。 ビューの内容をスクロールを実装します。|  
|[CFormView](../mfc/reference/cformview-class.md)|フォーム ビューでは、コントロールを含むビュー。 フォーム ベースのアプリケーションでは、このようなフォーム インターフェイスの 1 つまたは複数を提供します。|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|使用するアプリケーションのユーザー サイトを参照できます、World Wide Web でだけでなくフォルダーで、ネットワークとローカル ファイル システムで Web ブラウザー ビュー。 Web ブラウザー ビューは、Active ドキュメント コンテナーとしても操作できます。|  
|[CRecordView](../mfc/reference/crecordview-class.md)|ODBC データベース レコードをコントロールに表示するフォーム ビュー。 ODBC でサポートを選択するには、プロジェクトで、ビューの基底クラスは`CRecordView`します。 接続されている、ビュー、`CRowset`オブジェクト。|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|DAO データベース レコードをコントロールに表示するフォーム ビュー。 ビューの基底クラスには、プロジェクトの DAO サポートを選択した場合`CDaoRecordView`です。 接続されている、ビュー、`CDaoRecordset`オブジェクト。|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|コントロールの OLE DB レコードを表示するフォーム ビュー。 ビューの基底クラスには、プロジェクトの OLE DB のサポートを選択すると場合、`COleDBRecordView`です。 接続されている、ビュー、`CRowset`オブジェクト。|  
  
> [!NOTE]
>  MFC バージョン 4.0 の時点で`CEditView`から派生した`CCtrlView`です。  
  
 アプリケーションでこれらのクラスを使用するには、そこからアプリケーションのビュー クラスを派生します。 関連情報については、次を参照してください。[のスクロールと拡大/縮小ビュー](../mfc/scrolling-and-scaling-views.md)です。 データベース クラスの詳細については、次を参照してください。[概要: データベース プログラミング](../data/data-access-programming-mfc-atl.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ビューの使い方](../mfc/using-views.md)

