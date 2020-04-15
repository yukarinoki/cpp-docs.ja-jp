---
title: マーシャリング
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 83cf29fb45347b7bfcfc1644546684f074061d25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319346"
---
# <a name="marshaling"></a>マーシャリング

マーシャリングの COM 手法を使用すると、あるプロセス内のオブジェクトによって公開されるインターフェイスを別のプロセスで使用できます。 マーシャリングでは、COM は、メソッドのパラメーターをプロセス間で (他のマシンで実行されているプロセスに渡って) 移動できる形式にパックし、もう一方の端でそれらのパラメーターをアンパックするために、コードを提供します (またはインターフェイスの実装者によって提供されるコードを使用します)。 同様に、COM は呼び出しからのリターンでこれらの同じ手順を実行する必要があります。

> [!NOTE]
> マーシャリングは、オブジェクトによって提供されるインターフェイスがオブジェクトと同じプロセスで使用されている場合には、通常は必要ありません。 ただし、スレッド間でマーシャリングが必要になる場合があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[マーシャリングの詳細](/windows/win32/com/marshaling-details)
