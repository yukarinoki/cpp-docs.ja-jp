---
title: OLE ドラッグ アンド ドロップおよびデータ転送クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: 530b1772dfb623689facd5b14eebe9ed1eacd4fd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624138"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE ドラッグ アンド ドロップおよびデータ転送クラス

これらのクラスは、OLE データ転送で使用されます。 クリップボードまたはドラッグアンドドロップを使用して、アプリケーション間でデータを転送できます。

[COleDropSource](reference/coledropsource-class.md)<br/>
ドラッグアンドドロップ操作を開始から終了まで制御します。 このクラスは、ドラッグ操作がいつ開始され、いつ終了するかを決定します。 また、ドラッグアンドドロップ操作中のカーソルフィードバックも表示されます。

[COleDataSource](reference/coledatasource-class.md)<br/>
アプリケーションがデータ転送用のデータを提供するときに使用されます。 `COleDataSource`オブジェクト指向のクリップボードオブジェクトとして表示できます。

[COleDropTarget](reference/coledroptarget-class.md)<br/>
ドラッグアンドドロップ操作の対象を表します。 オブジェクトは、 `COleDropTarget` 画面上のウィンドウに対応します。 このメソッドは、削除されたデータを受け入れ、実際の削除操作を実装するかどうかを決定します。

[COleDataObject](reference/coledataobject-class.md)<br/>
からへの受信側として使用され `COleDataSource` ます。 `COleDataObject`オブジェクトは、オブジェクトに格納されているデータへのアクセスを提供 `COleDataSource` します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
