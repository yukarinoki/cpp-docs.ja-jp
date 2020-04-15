---
title: デュアル インターフェイスとイベント
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 4ce5048c25bd55feb0f1eb20fc04ec6bfeead746
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319602"
---
# <a name="dual-interfaces-and-events"></a>デュアル インターフェイスとイベント

イベント インターフェイスをデュアルとして設計することは可能ですが、デザインを設計しない理由はたくさんあります。 根本的な理由は、イベントの発生源がイベントを起動する場合に、vtable または`Invoke`経由でイベントを起動する場合のみであり、両方ではなく、イベントを実行する必要があります。 イベント ソースが直接 vtable メソッド呼び出しとしてイベント`IDispatch`を発生させた場合、メソッドは使用されず、インターフェイスが純粋な vtable インターフェイスであるはずであることは明らかです。 イベント ソースがイベントを 呼`Invoke`び出しとして起動する場合、vtable メソッドは使用されず、インターフェイスが dispinterface であるはずであることは明らかです。 イベント インターフェイスをデュアルとして定義する場合は、使用しないインターフェイスの一部をクライアントに実装する必要があります。

> [!NOTE]
> この引数は、一般にデュアル インターフェイスには適用されません。 実装の観点から見ると、デュアルは、幅広いクライアントからアクセス可能なインターフェイスを実装する、迅速で便利で適切にサポートされる方法です。

デュアルイベントインタフェースを回避する理由は、さらにあります。これらの機能はサポートしていません。

## <a name="see-also"></a>関連項目

[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)
