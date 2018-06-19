---
title: ドキュメントとビューをクリーンアップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dfe54c13db6f44bc70289380ae5f50d99c3722b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341327"
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理
ドキュメントを閉じるときに、まずフレームワークその[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)メンバー関数。 ドキュメントの操作の実行中にヒープにメモリを割り当てた場合`DeleteContents`割り当てを解除することをお勧めします。  
  
> [!NOTE]
>  ドキュメントのデストラクターでドキュメントのデータの割り当てを解除する必要がありますされません。 SDI アプリケーションの場合は、ドキュメント オブジェクトを再利用する可能性があります。  
  
 ヒープに割り当てられたメモリの割り当てを解除するビューのデストラクターを上書きすることができます。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

