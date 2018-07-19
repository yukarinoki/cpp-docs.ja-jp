---
title: コレクションと列挙子インターフェイス (ATL) の設計 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab8b42804ca892c80971928b869e09ccdf479d68
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851328"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>コレクションと列挙子インターフェイスの設計原則
インターフェイスの種類ごとの背後にあるさまざまな設計原則があります。  
  
-   コレクション インターフェイスを提供します*ランダム*へのアクセス、*単一*を使用してコレクション内の項目、`Item`メソッドでは、クライアントを使用してコレクション内の項目の数を検出できます、 `Count`プロパティ、および多くの場合、クライアントが追加および削除できるようにします。  
  
-   列挙子インターフェイス*シリアル*へのアクセスを*複数*コレクション内の項目を検出 (列挙子が返すことを停止するまでに、コレクション内に項目の数は、クライアントを許可しません。アイテム)、および追加の項目を削除する方法を提供しません。  
  
 インターフェイスの種類ごとでは、コレクション内の要素へのアクセスを提供するためにさまざまな役割を果たします。  
  
## <a name="see-also"></a>関連項目  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)

