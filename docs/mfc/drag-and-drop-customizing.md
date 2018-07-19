---
title: 'ドラッグ アンド ドロップ: カスタマイズ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ec5a5a493106750fa7bb8c7ec31b8dbb011070
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344244"
---
# <a name="drag-and-drop-customizing"></a>ドラッグ アンド ドロップ: カスタマイズ
ドラッグ アンド ドロップ機能の既定の実装は、ほとんどのアプリケーションです。 ただし、一部のアプリケーションでは、この標準動作を変更する必要があります。 この記事では、これらの既定値を変更するための手順について説明します。 さらに、ドロップ ソースとしての複合ドキュメントをサポートしていないアプリケーションを確立するためにこの手法を使用することができます。  
  
 標準の OLE ドラッグ アンド ドロップの動作をカスタマイズしている、または非 OLE アプリケーションがある場合、作成する必要が、`COleDataSource`データを格納するオブジェクト。 ユーザーは、ドラッグ アンド ドロップ操作を起動するときに、コードを呼び出す必要があります、`DoDragDrop`ドラッグ アンド ドロップ操作をサポートする他のクラスからの代わりに、このオブジェクトからの関数。  
  
 必要に応じて、作成することができます、`COleDropSource`オブジェクトを削除を制御し、いくつかの動作の変更対象の種類によってはその関数をオーバーライドします。 このドロップ ソース オブジェクトに渡され`COleDataSource::DoDragDrop`をこれらの関数の既定の動作を変更します。 これらのさまざまなオプションでは、アプリケーションでドラッグ アンド ドロップ操作をサポートする方法の柔軟性が大幅に向上できるようにします。 データ ソースの詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)です。  
  
 ドラッグ アンド ドロップ操作をカスタマイズするには、次の関数をオーバーライドできます。  
  
|上書き|カスタマイズするには|  
|--------------|------------------|  
|`OnBeginDrag`|どのようにドラッグを開始を呼び出した後`DoDragDrop`です。|  
|`GiveFeedback`|ドロップの結果に、カーソルの外観などの視覚的フィードバックします。|  
|`QueryContinueDrag`|ドラッグ アンド ドロップ操作の終了。 この関数では、ドラッグ操作中に修飾子キーの状態を確認することができます。|  
  
## <a name="see-also"></a>関連項目  
 [ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropSource クラス](../mfc/reference/coledropsource-class.md)   
 [COleDataSource クラス](../mfc/reference/coledatasource-class.md)
