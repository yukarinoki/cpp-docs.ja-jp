---
title: QueryInterface |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c361bc9510c610f2004af9f09c061d6f4b8b8cd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057451"
---
# <a name="queryinterface"></a>QueryInterface

COM の基本的なメカニズムは、使用するにはオブジェクトが静的に (前にインスタンス化されます) を提供する機能が express されるメカニズムは、`IUnknown`メソッドと呼ばれる[QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))します。

派生したすべてのインターフェイスは`IUnknown`ですべてのインターフェイスの実装があるため、`QueryInterface`します。 実装に関係なくは、このメソッドは、インターフェイスを呼び出し元が、ポインターの IID を使用して、オブジェクトを照会します。 オブジェクトは、そのインターフェイスをサポートしている場合`QueryInterface`も呼び出し中に、インターフェイスへのポインターを取得します。`AddRef`します。 それ以外の場合、E_NOINTERFACE エラー コードを返します。

従う必要がありますので注意[参照カウント](../atl/reference-counting.md)常時ルール。 呼び出す場合`Release`参照カウントがゼロにデクリメントするためのインターフェイス ポインターでする必要がありますいないポインターを使用する、もう一度です。 場合によっては、オブジェクトへの弱い参照を取得する必要があります (つまり、たい場合がありますの参照カウントをインクリメントせずにそのインターフェイスのいずれかへのポインターを取得) を呼び出すことでこれを実行する余裕がないが、`QueryInterface`続けて`Release`します。 このような方法で取得されたポインターは無効でありは使用できません。 これより簡単に明らかにいつ[_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces)が定義されている場合は、検索の参照カウントのバグの便利な方法は、このマクロを定義するようにします。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[オブジェクト内の移動を QueryInterface:](/windows/desktop/com/queryinterface--navigating-in-an-object)

