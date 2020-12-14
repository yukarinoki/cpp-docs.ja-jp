---
description: '詳細情報: クリップボード: データのコピーと貼り付け'
title: 'クリップボード : データのコピーと貼り付け'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: fdc102cf7a92bc78df83419269bb5de828dc9d19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251233"
---
# <a name="clipboard-copying-and-pasting-data"></a>クリップボード : データのコピーと貼り付け

このトピックでは、OLE アプリケーションでクリップボードへのコピーと貼り付けを実装するために必要な最小限の作業について説明します。 続行する前に、「 [データオブジェクトとデータソース (OLE)](data-objects-and-data-sources-ole.md) 」のトピックを読むことをお勧めします。

コピーまたは貼り付けを実装するには、まず、[編集] メニューの [コピー]、[切り取り]、[貼り付け] の各オプションを処理する関数を用意する必要があります。

## <a name="copying-or-cutting-data"></a><a name="_core_copying_or_cutting_data"></a> データのコピーまたは切り取り

#### <a name="to-copy-data-to-the-clipboard"></a>クリップボードにデータをコピーするには

1. コピーするデータがネイティブデータであるか、または埋め込みまたはリンクされたアイテムであるかを判断します。

   - データが埋め込まれている場合、またはリンクされている場合は、 `COleClientItem` 選択されているオブジェクトへのポインターを取得します。

   - データがネイティブで、アプリケーションがサーバーである場合は、選択したデータを格納するから派生した新しいオブジェクトを作成し `COleServerItem` ます。 それ以外の場合は、 `COleDataSource` データのオブジェクトを作成します。

1. 選択した項目の `CopyToClipboard` メンバー関数を呼び出します。

1. ユーザーがコピー操作ではなく切り取り操作を選択した場合は、選択したデータをアプリケーションから削除します。

このシーケンスの例を参照するには、 `OnEditCut` `OnEditCopy` MFC OLE サンプルプログラム [OCLIENT](../overview/visual-cpp-samples.md) および [HIERSVR](../overview/visual-cpp-samples.md)の関数と関数を参照してください。 これらのサンプルは現在選択されているデータへのポインターを保持しているので、手順1は既に完了しています。

## <a name="pasting-data"></a><a name="_core_pasting_data"></a> データの貼り付け

データの貼り付けは、アプリケーションにデータを貼り付けるときに使用する形式を選択する必要があるため、コピーするよりも複雑です。

#### <a name="to-paste-data-from-the-clipboard"></a>クリップボードからデータを貼り付けるには

1. ビュークラスで、[ `OnEditPaste` 編集] メニューの [貼り付け] オプションを選択するユーザーを処理するためにを実装します。

1. 関数で、 `OnEditPaste` オブジェクトを作成 `COleDataObject` し、その `AttachClipboard` メンバー関数を呼び出して、このオブジェクトをクリップボードのデータにリンクします。

1. を呼び出して `COleDataObject::IsDataAvailable` 、特定の形式が使用可能かどうかを確認します。

   または、を使用し `COleDataObject::BeginEnumFormats` て、アプリケーションに最も適した形式を見つけるまで他の書式を検索することもできます。

1. 形式の貼り付けを実行します。

このしくみの例については、「 `OnEditPaste` MFC OLE サンプルプログラム [OCLIENT](../overview/visual-cpp-samples.md) および [HIERSVR](../overview/visual-cpp-samples.md)で定義されているビュークラスのメンバー関数の実装」を参照してください。

> [!TIP]
> 貼り付け操作を独自の関数に分離する主な利点は、ドラッグアンドドロップ操作中にアプリケーションでデータを削除するときに、同じ貼り付けコードを使用できることです。 OCLIENT や HIERSVR と同様に、 `OnDrop` 関数はを呼び出して `DoPasteItem` 、貼り付け操作を実装するために記述されたコードを再利用することもできます。

[編集] メニューの [特殊文字の貼り付け] オプションを処理するには、 [OLE のトピックダイアログボックス](dialog-boxes-in-ole.md)を参照してください。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [その他の形式の追加](clipboard-adding-other-formats.md)

- [OLE データオブジェクトとデータソース、および uniform data transfer](data-objects-and-data-sources-ole.md)

- [OLE のドラッグ アンド ドロップ](drag-and-drop-ole.md)

- [OLE●ole○](ole-background.md)

## <a name="see-also"></a>関連項目

[クリップボード: OLE クリップボード機構の使用](clipboard-using-the-ole-clipboard-mechanism.md)
