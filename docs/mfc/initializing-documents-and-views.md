---
title: ドキュメントとビューの初期化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43610a08d5a3713cc40de0a2279286735a27d1da
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928183"
---
# <a name="initializing-documents-and-views"></a>ドキュメントとビューの初期化
ドキュメント クラスは、両方の方法をサポートする必要がありますので、2 つの異なる方法でドキュメントが作成されます。 最初に、ユーザーは、ファイルの新しいコマンドを使用して新しい空のドキュメントを作成することができます。 その場合は、オーバーライドでドキュメントの初期化、[でも実質的](../mfc/reference/cdocument-class.md#onnewdocument)クラスのメンバー関数[CDocument](../mfc/reference/cdocument-class.md)です。 第二に、ユーザーは、ファイルから内容の読み取りが新しいドキュメントを作成するのに、[ファイル] メニュー、開いているコマンドを使用できます。 その場合は、オーバーライドでドキュメントの初期化、[かまいません](../mfc/reference/cdocument-class.md#onopendocument)クラスのメンバー関数`CDocument`です。 両方の初期化が同じ場合は、両方のオーバーライドから共通のメンバー関数を呼び出すことができますか`OnOpenDocument`呼び出すことができます`OnNewDocument`をクリーンなドキュメントを初期化して開く操作を完了します。  
  
 ビューは、ドキュメントの作成後に作成されます。 ビューを初期化するために最適な時期は、ドキュメント、フレーム ウィンドウとビューを作成するために、フレームワークが完了した後です。 オーバーライドすることで、ビューを初期化することができます、[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)のメンバー関数[CView](../mfc/reference/cview-class.md)です。 再初期化または調整する必要がある場合は、ドキュメントの変更されるたびに、オーバーライドすることができます[OnUpdate](../mfc/reference/cview-class.md#onupdate)です。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

