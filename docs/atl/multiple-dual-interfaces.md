---
title: 複数のデュアル インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80bc2d4cc112c87c5c7a4e7d30f680631c1a1506
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758288"
---
# <a name="multiple-dual-interfaces"></a>複数のデュアル インターフェイス

デュアル インターフェイス (つまり、vtable とそのため、クラスを使用できるようにスクリプト言語と C++ での遅延バインディングの両方の柔軟性など) の利点を結合することが多重継承の手法を使用します。

1 つの COM オブジェクトに複数のデュアル インターフェイスを公開することはできますが、これは推奨されません。 複数のデュアル インターフェイスがある場合は、必要があります 1 つだけ`IDispatch`インターフェイスを公開します。 大文字と小文字であることを確認できる手法は、関数または増加のコードの複雑さの損失などのペナルティを実行します。 このアプローチを検討している開発者は、長所と短所について慎重に評価する必要があります。

## <a name="exposing-a-single-idispatch-interface"></a>1 つの IDispatch インターフェイスを公開します。

2 つ以上の特殊化から派生することによって、単一のオブジェクトに対して複数のデュアル インターフェイスを公開することは`IDispatchImpl`します。 ただし、クエリを実行するクライアントを許可する場合、`IDispatch`インターフェイスを使用する必要が、 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2)マクロ (または[COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) を使用する基本クラスを指定する、実装`IDispatch`します。

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

ため、1 つだけ`IDispatch`インターフェイスを公開すると、クライアントを通じてオブジェクトにアクセスできるのみ、`IDispatch`インターフェイスでは、メソッドまたはその他のインターフェイスでプロパティにアクセスできません。

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>複数のデュアル インターフェイスを IDispatch の単一の実装に組み合わせる

ATL はの単一の実装に複数のデュアル インターフェイスを結合するためのサポートを提供しない`IDispatch`します。 ただしは、個別の共用体を含むテンプレート クラスの作成など、インターフェイスに手動で結合する方法はいくつか既知`IDispatch`インターフェイスを実行する新しいオブジェクトを作成、`QueryInterface`関数、またはを使用して、入れ子になったオブジェクトを作成する typeinfo ベースの実装、`IDispatch`インターフェイス。

これらの方法では、潜在的な名前空間の競合、およびコードの複雑さと保守容易性に問題があります。 複数のデュアル インターフェイスを作成することは推奨されません。

## <a name="see-also"></a>関連項目

[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

