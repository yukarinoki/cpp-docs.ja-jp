---
title: 複数のデュアル インターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: e23682bd0b7c923a1e377463405f84a6c6ee1221
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356720"
---
# <a name="multiple-dual-interfaces"></a>複数のデュアル インターフェイス
デュアル インターフェイス (つまり、vtable と遅延バインディング、したがってクラスを使用できるようにスクリプト言語と C++ の両方の柔軟性を高めて) の利点を結合することも複数継承の方法を使用します。  
  
 単一の COM オブジェクトに対して複数のデュアル インターフェイスを公開することはできますが、これは推奨されません。 複数のデュアル インターフェイスがある場合がある必要があります 1 つだけ`IDispatch`公開されるインターフェイス。 大文字と小文字であることを確認に使用できる手法は、関数または増加したコードの複雑さの損失などの低下を実行します。 このアプローチを検討している開発者は、長所と短所に慎重に比較検討する必要があります。  
  
## <a name="exposing-a-single-idispatch-interface"></a>1 つの IDispatch インターフェイスを公開します。  
 2 つ以上の特殊な形式から派生することによって、単一のオブジェクトに対して複数のデュアル インターフェイスを公開することは`IDispatchImpl`します。 ただし、クエリを実行するクライアントを許可する場合、`IDispatch`インターフェイスを使用する必要が、 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2)マクロ (または[COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) を使用する基本クラスを指定します実装`IDispatch`です。  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 1 つだけ`IDispatch`インターフェイスを公開すると、クライアントを通じて、オブジェクトにのみアクセスできる、`IDispatch`インターフェイスはメソッドまたはその他のインターフェイスでプロパティにアクセスできません。  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>複数のデュアル インターフェイスを IDispatch の単一実装に結合  
 ATL の単一実装に複数のデュアル インターフェイスを結合するためのサポートを行いません`IDispatch`です。 ただし、個々 の和集合を表すテンプレート クラスの作成などのインターフェイスを手動で結合するいくつかの既知のアプローチがある`IDispatch`インターフェイスを実行する新しいオブジェクトを作成する、`QueryInterface`関数、またはを使用して、typeinfo ベースの実装を作成する入れ子になったオブジェクトの`IDispatch`インターフェイスです。  
  
 これらのアプローチでは、潜在的な名前空間の競合だけでなくコードの複雑さと保守性に問題があります。 複数のデュアル インターフェイスを作成することは推奨されません。  
  
## <a name="see-also"></a>関連項目  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

