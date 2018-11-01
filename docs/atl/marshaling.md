---
title: マーシャ リング
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: a6129ba96cf3ac11339a8ab953e0838127f8fb3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569794"
---
# <a name="marshaling"></a>マーシャ リング

マーシャ リングの COM の手法は、別のプロセスで使用する 1 つのプロセス内のオブジェクトによって公開されるインターフェイスを使用できます。 マーシャ リングすると、COM コードを提供します (またはインターフェイスの実装者によって提供されるコードを使用) をプロセス間で (および、他のコンピューターで実行されているプロセスをネットワーク経由で) に移動できる形式にメソッドのパラメーターをパックして、これらのパラメーターをアンパックするのにはもう一方の end。 同様に、COM では、呼び出しから返された場合は、同様の手順を実行する必要があります。

> [!NOTE]
>  マーシャ リングは通常必要ありませんオブジェクトによって提供されるインターフェイスは、オブジェクトと同じプロセスで使用されている場合です。 ただし、スレッド間マーシャ リングを必要に可能性があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[マーシャ リングの詳細](/windows/desktop/com/marshaling-details)

