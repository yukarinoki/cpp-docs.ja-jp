---
title: CComObjectRootEx を実装する |Microsoft ドキュメント
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
ms.openlocfilehash: 44c62e7589b9b300ceaa2886760bf2c3d85550ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356535"
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx を実装します。
[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)は不可欠です。 すべての ATL オブジェクトが 1 つのインスタンスを持つ必要があります`CComObjectRootEx`または[CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 、継承にします。 `CComObjectRootEx` は、COM マップ エントリに基づく既定の `QueryInterface` メカニズムを提供します。  
  
 その COM マップを介して、オブジェクトのインターフェイスは、クライアントによるインターフェイスの照会時にそのクライアントに公開されます。 照会は、`CComObjectRootEx::InternalQueryInterface` を介して実行されます。 `InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。  
  
 インターフェイスを使用して、COM マップ テーブルに入力する、 [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry)マクロまたはそのバリエーションの 1 つです。 たとえば、次のコードはインターフェイス `IDispatch`、`IBeeper`、および `ISupportErrorInfo` を COM マップ テーブルに入力します。  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)   
 [COM マップに関するマクロ](../atl/reference/com-map-macros.md)

