---
title: クラス (アーキテクチャ) を参照 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.view
dev_langs:
- C++
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11bb3d9e551089a156d255f7b27fb55cbe87bdbe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="view-classes-architecture"></a>ビュー クラス (アーキテクチャ)
`CView` その派生クラスは、フレーム ウィンドウのクライアント領域を表す子ウィンドウ。 ビューは、データを表示し、ドキュメントの入力をそのまま使用します。  
  
 ビュー クラスは、ドキュメント クラスおよびドキュメント テンプレート オブジェクトを使用して、フレーム ウィンドウ クラスに関連付けられています。  
  
 [CView](../mfc/reference/cview-class.md)  
 ドキュメントのデータのアプリケーション固有のビューの基底クラス。 ビューは、データを表示し、ユーザー入力を編集またはデータの選択をそのまま使用します。 独自のビュー クラスを派生させる`CView`です。  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 スクロール機能を持つビューの基底クラス。 ビュー クラスを派生させる`CScrollView`自動スクロールのためです。  
  
## <a name="form-and-record-views"></a>フォーム ビューとレコード ビュー  
 フォーム ビューもスクロール可能なビューです。 これらは、ダイアログ ボックスのテンプレートに基づきます。  
  
 レコード ビューは、フォーム ビューから取得されます。 ダイアログ ボックスのテンプレートだけでなく、データベースへの接続もあります。  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 レイアウトを持つが、ダイアログ ボックスのテンプレートで定義されているスクロール可能なビューです。 クラスを派生`CFormView` ダイアログ ボックスのテンプレートに基づくユーザー インターフェイスを実装します。  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 フォーム ビューのデータ アクセス オブジェクト (DAO) レコード セット オブジェクトに直接接続します。 すべてのフォーム ビューと同様に、 `CDaoRecordView`  ダイアログ ボックスのテンプレートに基づきます。  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 アプリケーション内で Web を参照するためのコントロールをサポートしています。 コントロールには、MFC での動的 HTML がサポートされています。  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 フォーム ビューの MFC OLE DB のサポートを提供します。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 フォーム ビューのオープン データベース コネクティビティ (ODBC) レコード セット オブジェクトに直接接続します。 すべてのフォーム ビューと同様に、 `CRecordView`  ダイアログ ボックスのテンプレートに基づきます。  
  
## <a name="control-views"></a>コントロールの表示  
 コントロール ビューは、それぞれのビューとしてコントロールを表示します。  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows のコントロールに関連付けられているすべてのビューの基底クラス。 コントロールに基づくビューは次のとおりです。  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 標準の Windows を含むビューの編集コントロール (を参照してください[CEdit](../mfc/reference/cedit-class.md))。 コントロールのテキスト編集をサポート、検索、置換、およびスクロール機能を編集します。  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 編集コントロールの機能豊富な Windows を含むビュー (を参照してください[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 エディット コントロールの機能、だけでなく豊富なコントロール サポートのフォント、色、段落の書式設定、および OLE の埋め込みオブジェクトを編集します。  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows のリスト コントロールを含むビュー (を参照してください[CListCtrl](../mfc/reference/clistctrl-class.md))。 リスト コントロールは、ファイル エクスプ ローラーの右側のペインに同様の方法で、アイコンと文字列を表示します。  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows のツリー コントロールを含むビュー (を参照してください[CTreeCtrl](../mfc/reference/ctreectrl-class.md))。 ツリー コントロールには、このアイコンと、ファイル エクスプ ローラーの左側のウィンドウと同様の方法で階層内に配置する文字列が表示されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

