---
title: 'クリップボード : データのコピーと貼り付け'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: 74348dd3e790cceada9aafd718464694997316ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374566"
---
# <a name="clipboard-copying-and-pasting-data"></a>クリップボード : データのコピーと貼り付け

ここでは、OLE アプリケーションでクリップボードにコピーして貼り付ける場合に必要な最小限の作業について説明します。 先に進む前に、[データ オブジェクトとデータ ソース (OLE) の](../mfc/data-objects-and-data-sources-ole.md)トピックを読むことをお勧めします。

コピーまたは貼り付けを実装する前に、まず [編集] メニューの [コピー]、[切り取り]、および [貼り付け] オプションを処理する関数を用意する必要があります。

## <a name="copying-or-cutting-data"></a><a name="_core_copying_or_cutting_data"></a>データのコピーまたは切削

#### <a name="to-copy-data-to-the-clipboard"></a>クリップボードにデータをコピーするには

1. コピーするデータがネイティブ データであるか、埋め込みアイテムかリンク アイテムかを決定します。

   - データが埋め込みまたはリンクされている場合は、選択`COleClientItem`されているオブジェクトへのポインターを取得します。

   - データがネイティブで、アプリケーションがサーバーである場合は、選択したデータを含む`COleServerItem`オブジェクトから派生した新しいオブジェクトを作成します。 それ以外の場合`COleDataSource`は、データのオブジェクトを作成します。

1. 選択した項目のメンバー関数`CopyToClipboard`を呼び出します。

1. ユーザーがコピー操作ではなく切り取り操作を選択した場合は、選択したデータをアプリケーションから削除します。

このシーケンスの例については、MFC OLE`OnEditCut`サンプル`OnEditCopy`プログラム[OCLIENT](../overview/visual-cpp-samples.md)および[HIERSVR](../overview/visual-cpp-samples.md)の関数と関数を参照してください。 これらのサンプルは現在選択されているデータへのポインタを保持するので、手順 1 は既に完了しています。

## <a name="pasting-data"></a><a name="_core_pasting_data"></a>データの貼り付け

データをアプリケーションに貼り付ける際に使用する形式を選択する必要があるため、データの貼り付けはコピーよりも複雑です。

#### <a name="to-paste-data-from-the-clipboard"></a>クリップボードからデータを貼り付けるには

1. ビュー クラスで、[編集`OnEditPaste`] メニューの [貼り付け] オプションを選択するユーザーを処理するように実装します。

1. 関数で`OnEditPaste`オブジェクトを`COleDataObject`作成し、そのメンバー関数`AttachClipboard`を呼び出して、このオブジェクトをクリップボード上のデータにリンクします。

1. 特定`COleDataObject::IsDataAvailable`の形式が使用可能かどうかを確認する呼び出し。

   または、アプリケーション`COleDataObject::BeginEnumFormats`に最も適したものが見つかるまで、他の形式を探すこともできます。

1. 形式の貼り付けを行います。

この動作の例については、MFC OLE サンプル プログラム`OnEditPaste` [OCLIENT](../overview/visual-cpp-samples.md)および[HIERSVR](../overview/visual-cpp-samples.md)で定義されているビュー クラスのメンバー関数の実装を参照してください。

> [!TIP]
> 貼り付け操作を独自の関数に分割する主な利点は、ドラッグ アンド ドロップ操作中にアプリケーションでデータがドロップされたときに、同じ貼り付けコードを使用できることです。 OCLIENT や HIERSVR のように`OnDrop`、関数は`DoPasteItem`Paste 操作を実装するために記述されたコードを再利用して を呼び出すこともできます。

[編集] メニューの [形式を選択して貼り付け] オプションを使用するには[、「OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)」を参照してください。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [他のフォーマットの追加](../mfc/clipboard-adding-other-formats.md)

- [OLE データ オブジェクトとデータ ソースと統一されたデータ転送](../mfc/data-objects-and-data-sources-ole.md)

- [OLE のドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)

- [OLE●ole○](../mfc/ole-background.md)

## <a name="see-also"></a>関連項目

[クリップボード: OLE クリップボード機構の使用方法](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
