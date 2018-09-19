---
title: CComObjectRootEx の実装 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CComObjectRootEx
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f91346febbb84ab7c1978740e0cbc6f0c43cbb4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052635"
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx の実装

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)は不可欠です。 すべての ATL オブジェクトは、1 つのインスタンスをいる必要があります`CComObjectRootEx`または[CComObjectRoot](../atl/reference/ccomobjectroot-class.md)その継承内。 `CComObjectRootEx` は、COM マップ エントリに基づく既定の `QueryInterface` メカニズムを提供します。

その COM マップを介して、オブジェクトのインターフェイスは、クライアントによるインターフェイスの照会時にそのクライアントに公開されます。 照会は、`CComObjectRootEx::InternalQueryInterface` を介して実行されます。 `InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。

インターフェイスを使用して、COM マップ テーブルに入力する、 [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry)マクロ、またはそのバリエーションの 1 つ。 たとえば、次のコードはインターフェイス `IDispatch`、`IBeeper`、および `ISupportErrorInfo` を COM マップ テーブルに入力します。

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)<br/>
[COM マップに関するマクロ](../atl/reference/com-map-macros.md)

