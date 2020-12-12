---
description: 詳細については、「データオブジェクトとデータソース (OLE)」を参照してください。
title: データ オブジェクトとデータ ソース (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
ms.openlocfilehash: 719053e2a75b18fbf54440403351198acc66b9d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291208"
---
# <a name="data-objects-and-data-sources-ole"></a>データ オブジェクトとデータ ソース (OLE)

クリップボードまたはドラッグアンドドロップを使用してデータ転送を実行すると、データに変換元と変換先が表示されます。 1つのアプリケーションがコピー用のデータを提供し、別のアプリケーションがそのデータを貼り付けのために受け入れます。 転送を成功させるには、転送の各側で同じデータに対して異なる操作を実行する必要があります。 MFC (Microsoft Foundation Class) ライブラリには、この転送の各側を表す2つのクラスが用意されています。

- データソース (オブジェクトによって実装される) は、 `COleDataSource` データ転送のソース側を表します。 これらは、データがクリップボードにコピーされるとき、またはドラッグアンドドロップ操作のためにデータが提供されるときに、ソースアプリケーションによって作成されます。

- データオブジェクト (オブジェクトによって実装される `COleDataObject` ) は、データ転送の変換先を表します。 これらは、変換先アプリケーションにデータがドロップされたとき、またはクリップボードから貼り付け操作を実行するように求められたときに作成されます。

次の記事では、アプリケーションでデータオブジェクトとデータソースを使用する方法について説明します。 この情報は、コンテナーとサーバーアプリケーションの両方に適用されます。これは、データのコピーと貼り付けを行うために両方が呼び出される可能性があるためです。

- [データオブジェクトとデータソース: 作成と破棄](data-objects-and-data-sources-creation-and-destruction.md)

- [データオブジェクトとデータソース: 操作](data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>このセクションの内容

[ドラッグ アンド ドロップ](drag-and-drop-ole.md)

[クリップボード](clipboard.md)

## <a name="see-also"></a>関連項目

[OLE●ole○](ole-in-mfc.md)<br/>
[COleDataObject クラス](reference/coledataobject-class.md)<br/>
[COleDataSource クラス](reference/coledatasource-class.md)
