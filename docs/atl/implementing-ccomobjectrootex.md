---
description: 詳細については、CComObjectRootEx の実装に関するページをご覧ください。
title: CComObjectRootEx の実装
ms.date: 11/04/2016
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: 235d10a8c390311230057da5dda11e5a8f093445
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152842"
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx の実装

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) は必須です。すべての ATL オブジェクトの `CComObjectRootEx` 継承には、または [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) のインスタンスが1つ必要です。 `CComObjectRootEx` は、COM マップ エントリに基づく既定の `QueryInterface` メカニズムを提供します。

その COM マップを介して、オブジェクトのインターフェイスは、クライアントによるインターフェイスの照会時にそのクライアントに公開されます。 照会は、`CComObjectRootEx::InternalQueryInterface` を介して実行されます。 `InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。

COM マップテーブルには、 [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) マクロまたはそのバリアントの1つを使用して、インターフェイスを入力できます。 たとえば、次のコードはインターフェイス `IDispatch`、`IBeeper`、および `ISupportErrorInfo` を COM マップ テーブルに入力します。

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)<br/>
[COM マップマクロ](../atl/reference/com-map-macros.md)
