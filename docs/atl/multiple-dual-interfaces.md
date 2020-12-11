---
description: 詳細については、「複数のデュアルインターフェイス」を参照してください。
title: 複数のデュアルインターフェイス
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
ms.openlocfilehash: d90c0176b3165cc0e5b976a29ec58b58fd3a7a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159416"
---
# <a name="multiple-dual-interfaces"></a>複数のデュアルインターフェイス

デュアルインターフェイスの利点 (つまり、vtable と遅延バインディングの両方の柔軟性) を組み合わせることで、複数の継承の手法でクラスをスクリプト言語と C++ で利用できるようにすることができます。

複数のデュアルインターフェイスを1つの COM オブジェクトで公開することもできますが、推奨されません。 複数のデュアルインターフェイスがある場合は、1つのインターフェイスのみを公開する必要があり `IDispatch` ます。 関数が失われたり、コードの複雑さが増したりするなど、この問題が発生する可能性を保証するために使用できる手法。 このアプローチを検討している開発者は、長所と短所を慎重に検討する必要があります。

## <a name="exposing-a-single-idispatch-interface"></a>単一の IDispatch インターフェイスの公開

1つのオブジェクトで複数のデュアルインターフェイスを公開するには、の2つ以上の特殊化から派生させることができ `IDispatchImpl` ます。 ただし、クライアントがインターフェイスのクエリを実行できるようにする場合は、 `IDispatch` [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) マクロ (または [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) を使用して、の実装に使用する基底クラスを指定する必要があり `IDispatch` ます。

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

公開されるインターフェイスは1つだけなので、 `IDispatch` インターフェイスを介してオブジェクトにアクセスできるのは、 `IDispatch` 他のインターフェイスのメソッドまたはプロパティにはアクセスできません。

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>複数のデュアルインターフェイスを1つの IDispatch の実装に結合する

ATL では、複数のデュアルインターフェイスをの1つの実装に組み合わせることはサポートされていません `IDispatch` 。 ただし、インターフェイスを手動で組み合わせる方法はいくつかあります。たとえば、個別のインターフェイスの共用体を含むテンプレートクラスを作成し `IDispatch` たり、関数を実行するための新しいオブジェクトを作成し `QueryInterface` たり、入れ子になったオブジェクトの typeinfo ベースの実装を使用してインターフェイスを作成したりすることが `IDispatch` できます。

これらのアプローチには、潜在的な名前空間の競合や、コードの複雑さと保守性に関する問題があります。 複数のデュアルインターフェイスを作成することはお勧めしません。

## <a name="see-also"></a>関連項目

[デュアルインターフェイスと ATL](../atl/dual-interfaces-and-atl.md)
