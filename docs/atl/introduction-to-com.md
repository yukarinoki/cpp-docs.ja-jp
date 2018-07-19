---
title: COM の概要 |Microsoft ドキュメント
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 938d0c45cae5ec9a2988f77f539af1a3d5513b83
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356176"
---
# <a name="introduction-to-com"></a>COM の概要
COM では、どの OLE と ActiveX コントロールのビルドで、基本的な「オブジェクト モデル」がします。 COM は、他のコンポーネントおよびホスト アプリケーションには、その機能を公開するオブジェクトを許可します。 オブジェクトがそれ自体を公開する方法と、プロセス間やネットワークのこの公開の動作を定義します。 COM では、オブジェクトのライフ サイクルも定義します。  
  
 COM を基本にはこれらの概念を示します。  
  
-   [インターフェイス](../atl/interfaces-atl.md)— オブジェクトを使用するには、機能を公開するメカニズムです。  
  
-   [IUnknown](../atl/iunknown.md) -他のすべてのユーザーは基になる基本インターフェイスです。 参照カウントや COM を介して実行メカニズムを照会するインターフェイスを実装します。  
  
-   [参照カウント](../atl/reference-counting.md)— 手法を使用するオブジェクト (または、厳密には、インターフェイス) を決定が使用されていない、つまり、自身を削除するために解放場合にします。  
  
-   [QueryInterface](../atl/queryinterface.md) -特定のインターフェイスのオブジェクトをクエリに使用する方法です。  
  
-   [マーシャ リング](../atl/marshaling.md)— スレッド、プロセス、および場所に依存しないのため、ネットワークの境界を越えて使用するオブジェクトをできる機構です。  
  
-   [集計](../atl/aggregation.md)-別の 1 つのオブジェクトの作成に使用できる方法を使用します。  
  
## <a name="see-also"></a>関連項目  
 [COM と ATL の概要](../atl/introduction-to-com-and-atl.md)   
 [コンポーネント オブジェクト モデル](http://msdn.microsoft.com/library/windows/desktop/ms694363)

