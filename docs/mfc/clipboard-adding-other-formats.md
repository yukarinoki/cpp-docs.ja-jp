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
ms.openlocfilehash: 52089364a6be423c69a7031cd0d99e1924de1444
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626060"
---
# <a name="clipboard-adding-other-formats"></a>クリップボード : その他のデータ形式の追加

このトピックでは、サポートされている形式の一覧を拡張する方法について説明します (特に OLE サポートの場合)。 トピック「[クリップボード: データのコピーと貼り付け](clipboard-copying-and-pasting-data.md)」では、クリップボードからのコピーと貼り付けをサポートするために必要な最小限の実装について説明します。 これがすべて実装されている場合、クリップボードに配置される形式は、 **CF_METAFILEPICT**、 **CF_EMBEDSOURCE**、 **CF_OBJECTDESCRIPTOR**、および場合によっては**CF_LINKSOURCE**です。 ほとんどのアプリケーションでは、これら3つよりも多くの形式がクリップボードに必要になります。

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>登録 (カスタム形式を)

独自のカスタム形式を作成するには、カスタムクリップボード形式を登録するときと同じ手順に従います。形式の名前を**RegisterClipboardFormat**関数に渡し、その戻り値を形式 ID として使用します。

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>クリップボードに形式を配置する

クリップボードに格納されている形式を追加するには、 `OnGetClipboardData` またはから派生したクラスの関数をオーバーライドする必要があり `COleClientItem` `COleServerItem` ます (コピーするデータがネイティブかどうかによって異なります)。 この関数では、次の手順を使用する必要があります。

#### <a name="to-place-formats-on-the-clipboard"></a>クリップボードに形式を配置するには

1. `COleDataSource` オブジェクトを作成します。

1. を呼び出して、このデータソースを、サポートされている形式の一覧に追加する関数に渡し `COleDataSource::CacheGlobalData` ます。

1. `COleDataSource::CacheGlobalData`サポートする標準形式ごとにを呼び出して、標準形式を追加します。

この手法は、MFC OLE サンプルプログラム[HIERSVR](../overview/visual-cpp-samples.md) ( `OnGetClipboardData` **CServerItem**クラスのメンバー関数を調べる) で使用されます。 このサンプルの唯一の違いは、HIERSVR では他の標準形式がサポートされていないため、手順3は実装されていないことです。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [OLE データオブジェクトとデータソース、および uniform data transfer](data-objects-and-data-sources-ole.md)

- [OLE のドラッグ アンド ドロップ](drag-and-drop-ole.md)

- [OLE●ole○](ole-background.md)

## <a name="see-also"></a>関連項目

[クリップボード: OLE クリップボード機構の使用方法](clipboard-using-the-ole-clipboard-mechanism.md)
