---
title: 'クリップボード: コピーと貼り付けデータ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4756da7459f3e584dd02b882f5c790412c095561
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929469"
---
# <a name="clipboard-copying-and-pasting-data"></a>クリップボード : データのコピーと貼り付け
このトピックでは、コピーと OLE アプリケーションでクリップボードから貼り付ける実装に必要な最小限の作業について説明します。 参照することをお勧め、[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)続行する前にトピックです。  
  
 コピーまたは貼り付けのいずれかを実装することができます、前に、[編集] メニュー、コピー、切り取り、および貼り付けのオプションを処理する関数を指定してください。  
  
##  <a name="_core_copying_or_cutting_data"></a> コピーまたは切り取りデータ  
  
#### <a name="to-copy-data-to-the-clipboard"></a>データをクリップボードにコピーするには  
  
1.  データをコピーするは、ネイティブ データ埋め込みまたはリンクされた項目は、かを判断します。  
  
    -   場合は、データが埋め込まれているか、リンクへのポインターを取得、`COleClientItem`が選択されているオブジェクト。  
  
    -   場合は、データがネイティブ アプリケーションは、サーバーから派生した新しいオブジェクトを作成する`COleServerItem`選択したデータを格納します。 それ以外の場合、作成、`COleDataSource`データ用オブジェクトです。  
  
2.  選択した項目を呼び出す`CopyToClipboard`メンバー関数。  
  
3.  ユーザーがコピー操作ではなく、切り取り操作を選択する場合は、選択したデータをアプリケーションから削除します。  
  
 このシーケンスの例を参照してください、`OnEditCut`と`OnEditCopy`関数、MFC OLE サンプル プログラム[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)です。 手順 1 が既に完了しているために、これらのサンプルが、現在選択されているデータへのポインターを維持できるに注意してください。  
  
##  <a name="_core_pasting_data"></a> データを貼り付ける  
 データの貼り付けは、アプリケーションに、データの貼り付けで使用される形式を選択する必要があるため、コピーよりも複雑です。  
  
#### <a name="to-paste-data-from-the-clipboard"></a>クリップボードからデータを貼り付ける  
  
1.  ビュー クラスで実装`OnEditPaste`編集 メニューから、貼り付け オプションを選択するユーザーを処理します。  
  
2.  `OnEditPaste`関数を作成、`COleDataObject`オブジェクトと呼び出しの`AttachClipboard`クリップボード上のデータにこのオブジェクトをリンクするメンバー関数。  
  
3.  呼び出す`COleDataObject::IsDataAvailable`を特定の形式が使用できるかどうかを確認します。  
  
     また、使用することができます`COleDataObject::BeginEnumFormats`をアプリケーションに最適なものが見つかるまで、その他の形式を探しています。  
  
4.  形式の貼り付けを実行します。  
  
 このしくみの例は、の実装を参照してください、 `OnEditPaste` MFC OLE サンプル プログラムで定義されたビュー クラスのメンバー関数[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)です。  
  
> [!TIP]
>  貼り付け操作を独自の関数を分離することの主な利点は、ドラッグ アンド ドロップ操作中に、アプリケーションでデータが削除されるときに、同じコードで貼り付けを使用できることです。 OCLIENT および HIERSVR と同様に、`OnDrop`関数が呼び出すことができますも`DoPasteItem`、貼り付け操作を実装する記述されたコードを再利用します。  
  
 [編集] メニューの貼り付け コマンドを処理するには、トピックを参照してください。 [OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)です。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [その他の形式の追加](../mfc/clipboard-adding-other-formats.md)  
  
-   [OLE データ オブジェクトとデータ ソースと統一されたデータの転送します。](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE のドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>関連項目  
 [クリップボード: OLE クリップボード機構の使用方法](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

