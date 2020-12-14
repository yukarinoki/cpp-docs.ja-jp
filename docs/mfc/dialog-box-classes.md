---
description: '詳細情報: ダイアログボックスクラス'
title: ダイアログ ボックス クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.dialog
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
ms.openlocfilehash: 5c178bc6895e338bf4b2876be5233c1b80007abc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261555"
---
# <a name="dialog-box-classes"></a>ダイアログ ボックス クラス

クラス `CDialog` とその派生クラスは、ダイアログボックスの機能をカプセル化します。 ダイアログボックスは特別な種類のウィンドウであるため、 `CDialog` はから派生してい `CWnd` ます。 からダイアログクラスを派生させる `CDialog` か、標準的なダイアログボックスのコモンダイアログクラスの1つを使用します。たとえば、ファイルを開いたり保存したり、フォントや色を選択したり、検索と置換の操作を開始したり、OLE 関連のさまざまな操作を実行したりすることができます。

[CDialog](reference/cdialog-class.md)<br/>
モーダルとモードレスの両方のダイアログボックスの基本クラスです。

[CDataExchange](reference/cdataexchange-class.md)<br/>
ダイアログボックスのデータ交換および検証情報を提供します。

## <a name="common-dialogs"></a>コモンダイアログ

これらのダイアログボックスクラスは、Windows のコモンダイアログボックスをカプセル化します。 複雑なダイアログボックスの使いやすい実装が用意されています。

[CCommonDialog](reference/ccommondialog-class.md)<br/>
すべてのコモンダイアログボックスの基本クラスです。

[CFileDialog](reference/cfiledialog-class.md)<br/>
ファイルを開く、または保存するための標準のダイアログボックスを提供します。

[CColorDialog](reference/ccolordialog-class.md)<br/>
色を選択するための標準のダイアログボックスを提供します。

[CFontDialog](reference/cfontdialog-class.md)<br/>
フォントを選択するための標準のダイアログボックスを提供します。

[CFindReplaceDialog](reference/cfindreplacedialog-class.md)<br/>
検索と置換の操作に使用する標準のダイアログボックスを提供します。

[CPrintDialog](reference/cprintdialog-class.md)<br/>
には、ファイルを印刷するための標準のダイアログボックスが用意されています。

[CPrintDialogEx](reference/cprintdialogex-class.md)<br/>
Windows 印刷プロパティシートを提供します。

[CPageSetupDialog](reference/cpagesetupdialog-class.md)<br/>
[Windows コモンページ設定] ダイアログボックスで提供されるサービスをカプセル化して、印刷の余白を設定および変更するための追加のサポートを提供します。

## <a name="ole-common-dialogs"></a>OLE コモンダイアログ

OLE では、いくつかのコモンダイアログボックスがウィンドウに追加されます。 これらのクラスは、OLE コモンダイアログボックスをカプセル化します。

[COleDialog](reference/coledialog-class.md)<br/>
すべての OLE ダイアログボックスの共通の実装を格納するために、フレームワークによって使用されます。 ユーザーインターフェイスカテゴリのすべてのダイアログボックスクラスは、この基本クラスから派生します。 `COleDialog` を直接使用することはできません。

[COleInsertDialog](reference/coleinsertdialog-class.md)<br/>
[オブジェクトの挿入] ダイアログボックスを表示します。これは、新しい OLE リンクまたは埋め込みアイテムを挿入するための標準ユーザーインターフェイスです。

[COlePasteSpecialDialog](reference/colepastespecialdialog-class.md)<br/>
[特殊な貼り付け] ダイアログボックスを表示します。このダイアログボックスは、[貼り付けの編集] を実装するための標準ユーザーインターフェイスです。

[COleLinksDialog](reference/colelinksdialog-class.md)<br/>
リンクされた項目に関する情報を変更するための標準ユーザーインターフェイスである [リンクの編集] ダイアログボックスを表示します。

[COleChangeIconDialog](reference/colechangeicondialog-class.md)<br/>
OLE 埋め込みまたはリンクされた項目に関連付けられているアイコンを変更するための標準ユーザーインターフェイスである [アイコンの変更] ダイアログボックスを表示します。

[COleConvertDialog](reference/coleconvertdialog-class.md)<br/>
OLE 項目をある種類から別の型に変換するための標準ユーザーインターフェイスである [変換] ダイアログボックスを表示します。

[COlePropertiesDialog](reference/colepropertiesdialog-class.md)<br/>
Windows のコモン OLE プロパティダイアログボックスをカプセル化します。 共通の OLE プロパティダイアログボックスを使用すると、Windows 標準と一貫性のある方法で OLE ドキュメントアイテムのプロパティを簡単に表示および変更することができます。

[COleUpdateDialog](reference/coleupdatedialog-class.md)<br/>
ドキュメント内のすべてのリンクを更新するための標準ユーザーインターフェイスである [更新] ダイアログボックスを表示します。 ダイアログボックスには、更新手順の終了方法を示す進行状況インジケーターが表示されます。

[COleChangeSourceDialog](reference/colechangesourcedialog-class.md)<br/>
リンク先を変更するための標準ユーザーインターフェイスである [変更ソース] ダイアログボックスを表示します。

[COleBusyDialog](reference/colebusydialog-class.md)<br/>
ビジー状態のアプリケーションの呼び出しを処理するための標準ユーザーインターフェイスである [サーバーがビジー] ダイアログボックスと [サーバーに応答しません] ダイアログボックスが表示されます。 通常、 [Colemessagefilter](reference/colemessagefilter-class.md) 実装によって自動的に表示されます。

## <a name="property-sheet-classes"></a>プロパティシートクラス

プロパティシートクラスを使用すると、アプリケーションでプロパティシート (タブ付きダイアログとも呼ばれます) を使用できます。 プロパティシートは、1つのダイアログボックスで多数のコントロールを整理するための効率的な方法です。

[CPropertyPage](reference/cpropertypage-class.md)<br/>
プロパティシート内の個々のページを提供します。 `CPropertyPage`プロパティシートに追加するページごとに、からクラスを派生させます。

[CPropertySheet](reference/cpropertysheet-class.md)<br/>
複数のプロパティページのフレームを提供します。 プロパティシートクラスをから派生させ `CPropertySheet` て、プロパティシートを迅速に実装します。

[COlePropertyPage](reference/colepropertypage-class.md)<br/>
ダイアログボックスと同様に、グラフィカルインターフェイスに OLE コントロールのプロパティを表示します。

## <a name="html-based-dialog-classes"></a>HTML ベースのダイアログクラス

[CDHtmlDialog](reference/cdhtmldialog-class.md)<br/>
ダイアログリソースではなく、HTML を使用してユーザーインターフェイスを実装するダイアログボックスを作成するために使用します。

[CMultiPageDHtmlDialog](reference/cmultipagedhtmldialog-class.md)<br/>
複数の HTML ページを順番に表示し、各ページのイベントを処理します。

## <a name="related-classes"></a>関連クラス

これらのクラスは、ユーザーごとのダイアログボックスではなく、ダイアログボックステンプレートを使用し、ダイアログボックスの動作の多くを備えています。

[CDialogBar](reference/cdialogbar-class.md)<br/>
ダイアログボックステンプレートに基づくコントロールバー。

[CFormView](reference/cformview-class.md)<br/>
ダイアログボックステンプレートでレイアウトが定義されているスクロールビュー。 からクラスを派生させ、 `CFormView` ダイアログボックステンプレートに基づいてユーザーインターフェイスを実装します。

[CDaoRecordView](reference/cdaorecordview-class.md)<br/>
データアクセスオブジェクト (DAO) レコードセットオブジェクトに直接接続されたフォームビューを提供します。 すべてのフォームビューと同様に、は `CDaoRecordView` ダイアログボックステンプレートに基づいています。

[CRecordView](reference/crecordview-class.md)<br/>
Open Database Connectivity (ODBC) レコードセットオブジェクトに直接接続されたフォームビューを提供します。 すべてのフォームビューと同様に、は `CRecordView` ダイアログボックステンプレートに基づいています。

[CPrintInfo](reference/cprintinfo-structure.md)<br/>
印刷または印刷プレビュージョブに関する情報を格納している構造体。 [CView](reference/cview-class.md)の印刷アーキテクチャで使用されます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
