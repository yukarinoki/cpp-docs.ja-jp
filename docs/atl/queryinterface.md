---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 28f3781706981b06d49829c0277014c09574ef6b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816062"
---
# <a name="queryinterface"></a>QueryInterface

COM の基本的なメカニズムは、使用するにはオブジェクトが静的に (前にインスタンス化されます) を提供する機能が express されるメカニズムは、`IUnknown`メソッドと呼ばれる[QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))します。

派生したすべてのインターフェイスは`IUnknown`ですべてのインターフェイスの実装があるため、`QueryInterface`します。 実装に関係なくは、このメソッドは、インターフェイスを呼び出し元が、ポインターの IID を使用して、オブジェクトを照会します。 オブジェクトは、そのインターフェイスをサポートしている場合`QueryInterface`も呼び出し中に、インターフェイスへのポインターを取得します。`AddRef`します。 それ以外の場合、E_NOINTERFACE エラー コードを返します。

従う必要がありますので注意[参照カウント](../atl/reference-counting.md)常時ルール。 呼び出す場合`Release`参照カウントがゼロにデクリメントするためのインターフェイス ポインターでする必要がありますいないポインターを使用する、もう一度です。 場合によっては、オブジェクトへの弱い参照を取得する必要があります (つまり、たい場合がありますの参照カウントをインクリメントせずにそのインターフェイスのいずれかへのポインターを取得) を呼び出すことでこれを実行する余裕がないが、`QueryInterface`続けて`Release`します。 このような方法で取得されたポインターは無効でありは使用できません。 これより簡単に明らかにいつ[_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces)が定義されている場合は、検索の参照カウントのバグの便利な方法は、このマクロを定義するようにします。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[QueryInterface:オブジェクト内を移動します。](/windows/desktop/com/queryinterface--navigating-in-an-object)
