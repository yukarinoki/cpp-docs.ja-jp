---
title: マーシャ リング
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 0661a4cdde0a3a875cf27221e884f6c65b9fea55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262399"
---
# <a name="marshaling"></a>マーシャ リング

マーシャ リングの COM の手法は、別のプロセスで使用する 1 つのプロセス内のオブジェクトによって公開されるインターフェイスを使用できます。 マーシャ リングすると、COM コードを提供します (またはインターフェイスの実装者によって提供されるコードを使用) をプロセス間で (および、他のコンピューターで実行されているプロセスをネットワーク経由で) に移動できる形式にメソッドのパラメーターをパックして、これらのパラメーターをアンパックするのにはもう一方の end。 同様に、COM では、呼び出しから返された場合は、同様の手順を実行する必要があります。

> [!NOTE]
>  マーシャ リングは通常必要ありませんオブジェクトによって提供されるインターフェイスは、オブジェクトと同じプロセスで使用されている場合です。 ただし、スレッド間マーシャ リングを必要に可能性があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[マーシャ リングの詳細](/windows/desktop/com/marshaling-details)
