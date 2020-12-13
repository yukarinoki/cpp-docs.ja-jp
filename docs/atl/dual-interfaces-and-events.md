---
description: 詳細については、デュアルインターフェイスとイベントに関するページを参照してください。
title: デュアルインターフェイスとイベント
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 231df7a0dfc8376acd6a9a0f9d85d0ed68fdd0b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153028"
---
# <a name="dual-interfaces-and-events"></a>デュアルインターフェイスとイベント

イベントインターフェイスをデュアルとして設計することもできますが、これを行うことはできません。 基本的な理由は、イベントのソースは、vtable または via の両方ではなく、イベントのみを発生させるということです `Invoke` 。 イベントソースが直接 vtable メソッド呼び出しとしてイベントを発生させた場合、メソッドは使用され `IDispatch` ず、インターフェイスが純粋な vtable インターフェイスである必要があることがわかります。 イベントソースがの呼び出しとしてイベントを発生させた場合、 `Invoke` vtable メソッドは使用されず、インターフェイスがディスパッチインターフェイスである必要があることがわかります。 イベントインターフェイスを duals として定義する場合は、使用されないインターフェイスの一部をクライアントに実装する必要があります。

> [!NOTE]
> この引数は、一般にデュアルインターフェイスには適用されません。 実装の観点からは、duals は、幅広いクライアントからアクセス可能なインターフェイスを実装するための、簡単で便利な、適切にサポートされた方法です。

2つのイベントインターフェイスを回避する理由は他にもあります。Visual Basic も Internet Explorer もサポートしていません。

## <a name="see-also"></a>関連項目

[デュアルインターフェイスと ATL](../atl/dual-interfaces-and-atl.md)
