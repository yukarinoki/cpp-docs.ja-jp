---
title: OLE のダイアログ ボックス
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
ms.openlocfilehash: 1081a831cc2b9fc0ab22e2c80a4f657466534d86
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270892"
---
# <a name="dialog-boxes-in-ole"></a>OLE のダイアログ ボックス

OLE が有効なアプリケーションを実行中に操作を実行するために、アプリケーションがユーザーからの情報をしなければならない場合があります。 MFC OLE クラスは、さまざまな必要な情報を収集するダイアログ ボックスを提供します。 このトピックでは、OLE のダイアログ ボックスで処理されるタスクとこれらのダイアログ ボックスを表示するために必要なクラスを示します。 OLE ダイアログ ボックスとその動作をカスタマイズするために使用する構造体の詳細については、次を参照してください。 [MFC リファレンス](../mfc/mfc-desktop-applications.md)します。

*オブジェクトを挿入します。*<br/>
新規または既存のオブジェクトに、ユーザーは、このダイアログ ボックスと、複合ドキュメントにできます。 ユーザー項目のアイコンとして表示するかを選択できるようにし、アイコンの変更 コマンド ボタンを有効にします。 ユーザーがオブジェクトの挿入 [編集] メニューからこのダイアログ ボックスを表示します。 使用して、 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)クラスがこのダイアログ ボックスを表示します。 それ自体に MDI アプリケーションを挿入することはできませんに注意してください。 SDI アプリケーションである場合を除き、コンテナー/サーバー アプリケーションを自体に挿入できません。

*貼り付け*<br/>
このダイアログ ボックスは、複合ドキュメントにデータを貼り付けるときに使用される形式を制御できます。 ユーザーは、データの形式、アイコンとして表示するかどうかおよび埋め込む、または、データをリンクするかどうかを選択できます。 ユーザーが [編集] メニューから選択して貼り付け、このダイアログ ボックスを表示します。 使用して、 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)クラスがこのダイアログ ボックスを表示します。

*アイコンの変更*<br/>
このダイアログ ボックスは、ユーザーがリンクまたは埋め込み項目を表すために表示するアイコンを選択できます。 ユーザーの編集 メニューからアイコンの変更 を選択または貼り付けまたは変換 ダイアログ ボックスで、アイコンの変更 ボタンを選択したときに、このダイアログ ボックスを表示します。 ユーザーがオブジェクトの挿入 ダイアログ ボックスが開きますアイコンで表示を選択したときに、それを表示します。 使用して、 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)クラスがこのダイアログ ボックスを表示します。

*変換*<br/>
このダイアログ ボックスは、埋め込みまたはリンクされた項目の種類を変更できます。 たとえば、メタファイルを複合ドキュメントに埋め込むことはして後で別のアプリケーションを使用して、埋め込みのメタファイルを変更する場合、[変換] ダイアログ ボックスを使用できます。 クリックしてこのダイアログ ボックスが表示される通常*項目の種類*オブジェクトの 編集 メニューとし、カスケード メニューの変換 をクリックします。 使用して、 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)クラスがこのダイアログ ボックスを表示します。 MFC OLE サンプルの実行例については、 [OCLIENT](../visual-cpp-samples.md)します。

*編集リンクまたはリンクを更新します。*<br/>
リンクの編集 ダイアログ ボックスは、リンク オブジェクトのソースに関する情報を変更できます。 更新プログラムのリンク ダイアログ ボックスでは ダイアログ ボックスで現在のすべてのリンクされた項目のソースを検証し、必要に応じて、リンクの編集 ダイアログ ボックスが表示されます。 ユーザーが 編集 メニューからのリンクは、リンクの編集 ダイアログ ボックスを表示します。 複合ドキュメントを初めて開いたときに、更新プログラムのリンク ダイアログ ボックスは、通常は表示されます。 いずれかを使用して、 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)または[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)クラス、ダイアログ ボックスによって表示します。

*サーバーはビジー状態または応答していないサーバー*<br/>
ユーザーがアイテムをアクティブにしようし、して、サーバーは別のユーザーによって使用またはタスクを通常、サーバーがあるため、要求を処理することはできませんが、サーバーがビジー状態のダイアログ ボックスが表示されます。 サーバーがすべてのアクティブ化要求に応答しない場合は、サーバーが応答しません ダイアログ ボックスが表示されます。 使用してこれらのダイアログ ボックスが表示される`COleMessageFilter`OLE インターフェイスの実装に基づいて、`IMessageFilter`とユーザーがライセンス認証要求を再試行するかどうかを決定できます。 使用して、 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)クラスがこのダイアログ ボックスを表示します。

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE](../mfc/ole-in-mfc.md)
