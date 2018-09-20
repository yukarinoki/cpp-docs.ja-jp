---
title: OLE ドラッグ アンド ドロップおよびデータ転送クラス |Microsoft Docs
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
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4b5d694d0081fbe2d852884c4a379e962c22f2a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444139"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE ドラッグ アンド ドロップおよびデータ転送クラス

これらのクラスは、OLE データ転送で使用されます。 これらは、アプリケーションによってクリップボードの使用方法やドラッグ アンド ドロップの間で転送されるデータを許可します。

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
最初から最後までドラッグ アンド ドロップ操作を制御します。 このクラスは、ドラッグ操作の開始時と終了時に決定します。 カーソルからのフィードバックは、ドラッグ アンド ドロップ操作中にも表示されます。

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
アプリケーションでは、データ転送のデータを提供するときに使用します。 `COleDataSource` オブジェクト指向クリップボード オブジェクトとして表示でした。

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
ドラッグ アンド ドロップ操作の対象を表します。 A`COleDropTarget`オブジェクトは画面上のウィンドウに対応します。 すべてのデータにドロップし、実際のドロップ操作を実装をそのまま使用するかどうかが決定します。

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
受信側として使用される`COleDataSource`します。 `COleDataObject` オブジェクトによって格納されるデータにアクセスできるように、`COleDataSource`オブジェクト。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

