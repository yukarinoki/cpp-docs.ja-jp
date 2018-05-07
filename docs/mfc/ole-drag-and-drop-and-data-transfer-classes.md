---
title: OLE ドラッグ アンド ドロップおよびデータ転送クラス |Microsoft ドキュメント
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
ms.openlocfilehash: d55d6d171f490631afe17a605f50607fb55f070b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE ドラッグ アンド ドロップおよびデータ転送クラス
これらのクラスは、OLE データ転送に使用されます。 これらは、アプリケーションでクリップボードの使用方法やドラッグ アンド ドロップの間で転送されるデータを許可します。  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 開始から終了までドラッグ アンド ドロップ操作を制御します。 このクラスは、ドラッグ操作の開始時と終了時に決定します。 カーソルからのフィードバックは、ドラッグ アンド ドロップ操作中にも表示されます。  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 アプリケーション データをデータ転送を提供するときに使用されます。 `COleDataSource` オブジェクト指向クリップボード オブジェクトとして表示できませんでした。  
  
 [関数](../mfc/reference/coledroptarget-class.md)  
 ドラッグ アンド ドロップ操作の対象を表します。 A`COleDropTarget`オブジェクトは、画面上のウィンドウに対応しています。 これは、すべてのデータにドロップし、実際のドロップ操作を実装をそのまま使用するかどうかを判断します。  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 受信者側として使用される`COleDataSource`です。 `COleDataObject` オブジェクトによって格納されるデータへのアクセスを提供する、`COleDataSource`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

