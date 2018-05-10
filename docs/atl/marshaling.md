---
title: マーシャ リング |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2b8b82d5369aa536dab638efa379089325d10b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="marshaling"></a>マーシャ リング
マーシャ リングの COM 手法では、別のプロセスで使用する 1 つのプロセス内のオブジェクトによって公開されるインターフェイスを使用します。 マーシャ リングすると、COM コードを示します (またはインターフェイスの実装者により提供されるコードを使用) プロセス全体にわたり (だけでなく、他のコンピューターで実行されているプロセスをネットワーク経由で) に移動することができる形式にメソッドのパラメーターをパックし、これらのパラメーターをアンパックするのにはもう一方の端。 同様に、COM では、呼び出しから返された場合は、同じ手順を実行する必要があります。  
  
> [!NOTE]
>  マーシャ リングは通常必要ありませんオブジェクトと同じプロセスでオブジェクトによって提供されるインターフェイスを使用する場合です。 ただし、スレッド間でマーシャ リングを必要になる可能性です。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [マーシャ リングの詳細](http://msdn.microsoft.com/library/windows/desktop/ms692621)

