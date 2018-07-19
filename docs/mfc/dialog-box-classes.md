---
title: ダイアログ ボックス クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.dialog
dev_langs:
- C++
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d33289d8025d7cdcaf4f6f69062230730b958c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351690"
---
# <a name="dialog-box-classes"></a>ダイアログ ボックス クラス
クラス`CDialog`し、その派生クラスがダイアログ ボックスの機能をカプセル化します。 ダイアログ ボックスはウィンドウの特殊なので`CDialog`から派生した`CWnd`です。 ダイアログ クラスを派生`CDialog`またはいずれかの標準のダイアログ ボックスで、開くファイルを保存したり、印刷、フォントや色を選択するなどのコモン ダイアログ クラスの検索と置換操作を開始するを実行するさまざまな OLE に関連します。操作です。  
  
 [CDialog](../mfc/reference/cdialog-class.md)  
 すべてのダイアログ ボックスをモーダルとモードレスの両方の基本クラス。  
  
 [CDataExchange](../mfc/reference/cdataexchange-class.md)  
 ダイアログ ボックスのデータ交換と検証情報を提供します。  
  
## <a name="common-dialogs"></a>コモン ダイアログ  
 これらのダイアログ ボックス クラスは、Windows のコモン ダイアログ ボックスをカプセル化します。 複雑なダイアログ ボックスの使いやすい実装を提供します。  
  
 [CCommonDialog](../mfc/reference/ccommondialog-class.md)  
 すべてのコモン ダイアログ ボックスの基本クラス。  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 開く、またはファイルを保存するためには、標準のダイアログ ボックスを提供します。  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 色を選択するためには、標準のダイアログ ボックスを提供します。  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 フォントを選択するためには、標準のダイアログ ボックスを提供します。  
  
 [CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)  
 検索と置換の操作の標準のダイアログ ボックスを提供します。  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 ファイルを印刷するためには、標準のダイアログ ボックスを提供します。  
  
 [CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)  
 Windows の 印刷のプロパティ シートを提供します。  
  
 [CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)  
 設定と印刷の余白を変更の追加サポートと共に Windows に共通の [ページ設定] ダイアログ ボックスにより提供されるサービスをカプセル化します。  
  
## <a name="ole-common-dialogs"></a>OLE コモン ダイアログ  
 OLE は、Windows に共通のいくつかのダイアログ ボックスを追加します。 これらのクラスは、OLE コモン ダイアログ ボックスをカプセル化します。  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 OLE ダイアログ ボックスをすべての一般的な実装を含むため、フレームワークで使用します。 ユーザー インターフェイスのカテゴリ内のすべてのダイアログ ボックス クラスは、この基本クラスから派生します。 `COleDialog` 直接使用することはできません。  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 リンクまたは埋め込みアイテムの新しい OLE を挿入するは、オブジェクトの挿入 ダイアログ ボックスで、標準のユーザー インターフェイスを表示します。  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 貼り付け ダイアログ ボックス、編集貼り付け コマンドを実装するための標準のユーザー インターフェイスを表示します。  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 リンクの編集 ダイアログ ボックスで、リンクされた項目に関する情報を変更するための標準のユーザー インターフェイスを表示します。  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 アイコンの変更 ダイアログ ボックスで、OLE に関連付けられているアイコンの埋め込みを変更、またはリンクされた項目のための標準のユーザー インターフェイスを表示します。  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 OLE 項目を別の 1 つの型に変換する標準のユーザー インターフェイスである [変換] ダイアログ ボックスが表示されます。  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Windows コモン OLE プロジェクト プロパティ ダイアログ ボックスをカプセル化します。 共通の OLE プロパティ ダイアログ ボックスでは、表示し、Windows の標準に準拠した形式での OLE ドキュメント項目のプロパティを変更する簡単な方法を提供します。  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 更新プログラム ダイアログ ボックスで、ドキュメント内のすべてのリンクを更新するための標準のユーザー インターフェイスを表示します。 ダイアログ ボックスには、完了するまで更新手順は、どの程度近いかを示すために、進行状況インジケーターが含まれています。  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 ソースの変更 ダイアログ ボックスで、移行先やリンクのソースを変更する標準のユーザー インターフェイスを表示します。  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 サーバーがビジー状態、サーバーが応答していないダイアログ ボックス、ビジー状態のアプリケーションへの呼び出しを処理するための標準のユーザー インターフェイスを表示します。 通常、によって自動的に表示されます、[関数](../mfc/reference/colemessagefilter-class.md)実装します。  
  
## <a name="property-sheet-classes"></a>プロパティ シート クラス  
 プロパティ シート クラスには、プロパティ シートとも呼ばれるタブ付きダイアログ ボックスを使用するアプリケーションができるようにします。 プロパティ シートは、多数の 1 つのダイアログ ボックスのコントロールを整理する効率的な方法です。  
  
 [CPropertyPage](../mfc/reference/cpropertypage-class.md)  
 プロパティ シート内の各ページを提供します。 クラスを派生`CPropertyPage`プロパティ シートに追加するには、各ページ。  
  
 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)  
 複数のプロパティ ページのフレームを提供します。 プロパティ シートのクラスを派生`CPropertySheet`のプロパティ シートを迅速に実装します。  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 ダイアログ ボックスのようなグラフィカル インターフェイスで制御する OLE のプロパティを表示します。  
  
## <a name="html-based-dialog-classes"></a>HTML ベースのダイアログ クラス  
 [CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)  
 ダイアログではなく、HTML リソースによるユーザー インターフェイスを実装するダイアログ ボックスを作成するために使用します。  
  
 [CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)  
 複数の HTML ページを順番に表示し、各ページのイベントを処理します。  
  
## <a name="related-classes"></a>関連するクラス  
 これらのクラスのダイアログ ボックス本質的にはないダイアログ ボックスのテンプレートを使用してダイアログ ボックスの動作の多くがあります。  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 ダイアログ ボックスのテンプレートに基づいているコントロール バーです。  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 レイアウトを持つが、ダイアログ ボックスのテンプレートで定義されているスクロール可能なビューです。 クラスを派生`CFormView` ダイアログ ボックスのテンプレートに基づくユーザー インターフェイスを実装します。  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 フォーム ビューのデータ アクセス オブジェクト (DAO) レコード セット オブジェクトに直接接続します。 すべてのフォーム ビューと同様に、 `CDaoRecordView`  ダイアログ ボックスのテンプレートに基づきます。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 フォーム ビューのオープン データベース コネクティビティ (ODBC) レコード セット オブジェクトに直接接続します。 すべてのフォーム ビューと同様に、 `CRecordView`  ダイアログ ボックスのテンプレートに基づきます。  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 印刷または印刷プレビュー ジョブに関する情報を含む構造体。 印刷のアーキテクチャで使用される[CView](../mfc/reference/cview-class.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

