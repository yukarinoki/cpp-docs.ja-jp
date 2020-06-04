---
title: 'クリップボード : その他のデータ形式の追加'
ms.date: 11/04/2016
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
ms.openlocfilehash: 6f4e159cc1b6918843d4a164dcca88500eb7b038
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374603"
---
# <a name="clipboard-adding-other-formats"></a>クリップボード : その他のデータ形式の追加

ここでは、特に OLE サポートでサポートされている形式の一覧を展開する方法について説明します。 「[クリップボード: データのコピーと貼り付け](../mfc/clipboard-copying-and-pasting-data.md)」では、クリップボードからのコピーと貼り付けのサポートに必要な最小限の実装について説明します。 これがすべて実装されている場合、クリップボードに配置される形式は、 、 **CF_EMBEDSOURCE 、**、 CF_OBJECTDESCRIPTOR 、 および場合によっては**CF_LINKSOURCE** **CF_METAFILEPICT**だけです。 **CF_OBJECTDESCRIPTOR** ほとんどのアプリケーションでは、クリップボードにこれらの 3 つよりも多くの形式が必要になります。

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>カスタム書式の登録

独自のカスタム書式を作成するには、カスタムクリップボード形式を登録するときに使用するのと同じ手順に従います。 **RegisterClipboardFormat**

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>クリップボードに書式を配置する

クリップボードに配置された形式にさらに書式を追加するには、派生元のクラス`OnGetClipboardData`で関数をオーバーライド`COleClientItem`するか、コピー`COleServerItem`するデータがネイティブかどうかに応じてオーバーライドする必要があります。 この関数では、次の手順を使用する必要があります。

#### <a name="to-place-formats-on-the-clipboard"></a>クリップボードに書式を配置するには

1. `COleDataSource` オブジェクトを作成します。

1. このデータ ソースを関数に渡し、 を呼び出`COleDataSource::CacheGlobalData`して、サポートされている形式の一覧にネイティブ データ形式を追加します。

1. サポートする標準フォーマットごとに`COleDataSource::CacheGlobalData`呼び出して、標準フォーマットを追加します。

この手法は、MFC OLE サンプル プログラム[HIERSVR](../overview/visual-cpp-samples.md) `OnGetClipboardData`で使用されます **(CServerItem**クラスのメンバー関数を確認します)。 このサンプルの唯一の違いは、HIERSVR が他の標準フォーマットをサポートしていないため、ステップ 3 が実装されないことです。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [OLE データ オブジェクトとデータ ソースと統一されたデータ転送](../mfc/data-objects-and-data-sources-ole.md)

- [OLE のドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)

- [OLE●ole○](../mfc/ole-background.md)

## <a name="see-also"></a>関連項目

[クリップボード: OLE クリップボード機構の使用方法](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
