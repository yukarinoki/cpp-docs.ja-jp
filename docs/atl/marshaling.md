---
description: 詳細については、「マーシャリング」を参照してください。
title: マーシャリング
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 2931bd9ab5e2fb8376ced44dd519a6de107be88e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152634"
---
# <a name="marshaling"></a>マーシャリング

マーシャリングの COM 手法を使用すると、あるプロセスでオブジェクトによって公開されているインターフェイスを別のプロセスで使用できます。 マーシャリングでは、COM はコード (またはインターフェイス実装によって提供されるコード) を提供して、メソッドのパラメーターを、プロセス間で移動できる形式に (またはネットワーク経由で他のマシンで実行されているプロセスに)、もう一方の終端でそれらのパラメーターをアンパックします。 同様に、COM は呼び出しから返されたものと同じ手順を実行する必要があります。

> [!NOTE]
> オブジェクトによって提供されるインターフェイスがオブジェクトと同じプロセスで使用されている場合、通常、マーシャリングは必要ありません。 ただし、スレッド間でマーシャリングが必要になる場合があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[マーシャリングの詳細](/windows/win32/com/marshaling-details)
