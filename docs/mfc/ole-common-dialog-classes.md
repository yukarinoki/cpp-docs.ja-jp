---
title: OLE コモン ダイアログ クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e3cedbe3cd08a425bd2bde2b4a6ca8c5a493c72
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348105"
---
# <a name="ole-common-dialog-classes"></a>OLE コモン ダイアログ クラス
これらのクラスは、いくつかの標準の OLE ダイアログ ボックスを実装することで、OLE の一般的なタスクを処理します。 OLE の機能の一貫性のあるユーザー インターフェイスも提供します。  
  
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
 サーバーがビジー状態、サーバーが応答していないダイアログ ボックス、ビジー状態のアプリケーションへの呼び出しを処理するための標準のユーザー インターフェイスを表示します。 通常、によって自動的に表示されます、`COleMessageFilter`実装します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

