---
title: OLE のダイアログ ボックス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fe7f9b4b97fd17e73c3dd9f113a87d8f087b93c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929664"
---
# <a name="dialog-boxes-in-ole"></a>OLE のダイアログ ボックス
ユーザーは、OLE 対応アプリケーションを実行するときに、操作を実行するために、アプリケーションがユーザーからの情報をしなければならない場合があります。 MFC OLE クラスは、いくつかの必要な情報を収集するダイアログ ボックスを提供します。 このトピックでは、OLE のダイアログ ボックスで処理されるタスクと対応するダイアログ ボックスを表示するために必要なクラスを示します。 OLE ダイアログ ボックスとその動作をカスタマイズするために使用する構造体の詳細については、次を参照してください。 [『 MFC リファレンス](../mfc/mfc-desktop-applications.md)です。  
  
 *オブジェクトを挿入します。*  
 このダイアログ ボックスで、ユーザーに新しく作成された挿入または既存のオブジェクト複合ドキュメント。 により、ユーザーは、項目のアイコンとして表示するかを選択し、アイコンの変更コマンド ボタンを有効にします。 オブジェクトの挿入を編集 メニューから選択すると、このダイアログ ボックスを表示します。 使用して、[メンバー](../mfc/reference/coleinsertdialog-class.md)をこのダイアログ ボックスを表示するクラス。 それ自体に MDI アプリケーションを挿入することはできませんに注意してください。 SDI アプリケーションである場合を除き、コンテナー/サーバー アプリケーションをそれ自体に挿入できません。  
  
 *貼り付け*  
 このダイアログ ボックスは、複合ドキュメントにデータを貼り付けるときに使用される書式を制御できます。 ユーザーには、データの形式を埋め込むか、データをリンクするかどうか、アイコンとして表示するかどうかを選択できます。 [編集] メニューから選択して貼り付け、ユーザーが選択すると、このダイアログ ボックスを表示します。 使用して、[関数](../mfc/reference/colepastespecialdialog-class.md)このダイアログ ボックスを表示するクラス。  
  
 *アイコンの変更*  
 このダイアログ ボックスで、ユーザーがリンクまたは埋め込み項目を表すために表示するアイコンを選択します。 ユーザーが編集 メニューからアイコンの変更 を選択または貼り付けまたは変換 ダイアログ ボックスで、アイコンの変更 ボタンを選択したときに、このダイアログ ボックスを表示します。 またときにも表示、ユーザーがオブジェクトの挿入 ダイアログ ボックスを開き、アイコンで表示を選択します。 使用して、[メンバー](../mfc/reference/colechangeicondialog-class.md)をこのダイアログ ボックスを表示するクラス。  
  
 *変換*  
 このダイアログ ボックスは、埋め込みまたはリンクされた項目の種類を変更できます。 たとえば、メタファイルを複合ドキュメントに埋め込まれているして後で埋め込みメタファイルを変更する別のアプリケーションを使用する場合は、変換 ダイアログ ボックスを使用できます。 このダイアログ ボックスは、通常 をクリックして表示される*項目の種類*オブジェクト 編集 メニュー、カスケード メニューで、変換 をクリックします。 使用して、[メンバー](../mfc/reference/coleconvertdialog-class.md)をこのダイアログ ボックスを表示するクラス。 例については、MFC OLE サンプルを実行[OCLIENT](../visual-cpp-samples.md)です。  
  
 *リンク または 更新プログラムへのリンク*  
 リンクの編集 ダイアログ ボックスは、リンク オブジェクトのソースに関する情報を変更できます。 リンクの更新 ダイアログ ボックスでは、現在のダイアログ ボックスのすべてのリンクされた項目のソースを確認し、必要に応じてリンクの編集 ダイアログ ボックスを表示します。 編集 メニューからのリンクを選択すると、リンクの編集 ダイアログ ボックスを表示します。 リンクの更新 ダイアログ ボックスには、複合ドキュメントを初めて開いたときに通常表示されます。 いずれかを使用して、[関数](../mfc/reference/colelinksdialog-class.md)または[関数](../mfc/reference/coleupdatedialog-class.md)クラス、に応じてどの ダイアログ ボックスを表示します。  
  
 *サーバーがビジー状態または応答していないサーバー*  
 ユーザーが項目をアクティブ化しようとして、サーバーが要求を処理、通常、サーバーが別のユーザーによって使用中か、またはタスクに現在できないときに、サーバーがビジー状態のダイアログ ボックスが表示されます。 サーバーがすべてのアクティブ化要求に応答しない場合は、サーバーが応答しません ダイアログ ボックスが表示されます。 使用してこれらのダイアログ ボックスが表示される`COleMessageFilter`OLE インターフェイスの実装に基づいて、`IMessageFilter`ユーザーは、アクティブ化要求を再試行するかどうかを決定できます。 使用して、 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)をこのダイアログ ボックスを表示するクラス。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE](../mfc/ole-in-mfc.md)

