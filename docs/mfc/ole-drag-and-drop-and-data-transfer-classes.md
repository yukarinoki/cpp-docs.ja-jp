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
ms.openlocfilehash: 7e01b6d5a7d14e0af4ca760e6e601e91359c8ab1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447617"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE ドラッグ アンド ドロップおよびデータ転送クラス

これらのクラスは、OLE データ転送で使用されます。 クリップボードまたはドラッグアンドドロップを使用して、アプリケーション間でデータを転送できます。

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
ドラッグアンドドロップ操作を開始から終了まで制御します。 このクラスは、ドラッグ操作がいつ開始され、いつ終了するかを決定します。 また、ドラッグアンドドロップ操作中のカーソルフィードバックも表示されます。

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
アプリケーションがデータ転送用のデータを提供するときに使用されます。 `COleDataSource` は、オブジェクト指向のクリップボードオブジェクトとして表示できます。

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
ドラッグアンドドロップ操作の対象を表します。 `COleDropTarget` オブジェクトは、画面上のウィンドウに対応します。 このメソッドは、削除されたデータを受け入れ、実際の削除操作を実装するかどうかを決定します。

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
`COleDataSource`する受信側として使用されます。 `COleDataObject` オブジェクトは、`COleDataSource` オブジェクトに格納されているデータへのアクセスを提供します。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
