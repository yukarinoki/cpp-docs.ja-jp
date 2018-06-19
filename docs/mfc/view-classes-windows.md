---
title: クラス (Windows) の表示 |Microsoft ドキュメント
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
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28dbcd246033dd53788861b97a0c678c1be2aa17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384180"
---
# <a name="view-classes-windows"></a>ビュー クラス (Windows)
`CView` その派生クラスは、フレーム ウィンドウのクライアント領域を表す子ウィンドウ。 ビューは、データを表示し、ドキュメントの入力をそのまま使用します。  
  
 ビュー クラスは、ドキュメント クラスおよびドキュメント テンプレート オブジェクトを使用して、フレーム ウィンドウ クラスに関連付けられています。  
  
 [CView](../mfc/reference/cview-class.md)  
 ドキュメントのデータのアプリケーション固有のビューの基底クラス。 ビューは、データを表示し、ユーザー入力を編集またはデータの選択をそのまま使用します。 ビュー クラスまたはクラスから派生`CView`です。  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 スクロール機能を持つビューの基底クラス。 ビュー クラスを派生させる`CScrollView`自動スクロールのためです。  
  
## <a name="form-and-record-views"></a>フォーム ビューとレコード ビュー  
 フォーム ビューもスクロール可能なビューです。 これらは、ダイアログ ボックスのテンプレートに基づきます。  
  
 レコード ビューは、フォーム ビューから取得されます。 ダイアログ ボックスのテンプレートだけでなく、データベースへの接続もあります。  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 レイアウトを持つが、ダイアログ ボックスのテンプレートで定義されているスクロール可能なビューです。 クラスを派生`CFormView` ダイアログ ボックスのテンプレートに基づくユーザー インターフェイスを実装します。  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 フォーム ビューのデータ アクセス オブジェクト (DAO) レコード セット オブジェクトに直接接続します。 すべてのフォーム ビューと同様に、 `CDaoRecordView`  ダイアログ ボックスのテンプレートに基づきます。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 フォーム ビューのオープン データベース コネクティビティ (ODBC) レコード セット オブジェクトに直接接続します。 すべてのフォーム ビューと同様に、 `CRecordView`  ダイアログ ボックスのテンプレートに基づきます。  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 HTML の WebBrowser 編集プラットフォームの機能を提供するフォーム ビュー。  
  
## <a name="control-views"></a>コントロールの表示  
 コントロール ビューは、それぞれのビューとしてコントロールを表示します。  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows のコントロールに関連付けられているすべてのビューの基底クラス。 コントロールに基づくビューは次のとおりです。  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 標準の Windows を含むビューの編集コントロール (を参照してください[CEdit](../mfc/reference/cedit-class.md))。 コントロールのテキスト編集をサポート、検索、置換、およびスクロール機能を編集します。  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 編集コントロールの機能豊富な Windows を含むビュー (を参照してください[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 エディット コントロールの機能、だけでなく豊富なコントロール サポートのフォント、色、段落の書式設定、および OLE の埋め込みオブジェクトを編集します。  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows のリスト コントロールを含むビュー (を参照してください[CListCtrl](../mfc/reference/clistctrl-class.md))。 リスト コントロールには、アイコンとラベルをファイル エクスプ ローラーの右側のウィンドウと同様の方法で構成される各項目のコレクションが表示されます。  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows のツリー コントロールを含むビュー (を参照してください[CTreeCtrl](../mfc/reference/ctreectrl-class.md))。 ツリー コントロールでは、ファイル エクスプ ローラーの左側のウィンドウと同様の方法で配置されたラベルとアイコンの階層リストを表示します。  
  
## <a name="related-classes"></a>関連するクラス  
 `CSplitterWnd` 1 つのフレーム ウィンドウ内で複数のビューであることができます。 `CPrintDialog` および`CPrintInfo`ビューの印刷と印刷プレビュー機能をサポートします。 `CRichEditDoc` および`CRichEditCntrItem`で使用される`CRichEditView`OLE コンテナーの機能を実装します。  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 ユーザーが複数のペインに分割できるウィンドウです。 これらのウィンドウのユーザーまたは固定サイズでサイズ変更できることができます。  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 ファイルを印刷するためには、標準のダイアログ ボックスを提供します。  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 印刷または印刷プレビュー ジョブに関する情報を含む構造体。 によって使用される`CView`のアーキテクチャを印刷します。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 含まれる OLE クライアント アイテムの一覧を保持する`CRichEditView`です。  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 項目に格納されている ole クライアント側のアクセスを提供する`CRichEditView`です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

