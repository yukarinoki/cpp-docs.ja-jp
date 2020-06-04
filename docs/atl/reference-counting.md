---
title: 参照カウント (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: 095f0ad2ecc1e1a870077899d61a3c594f8cc95f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321739"
---
# <a name="reference-counting"></a>参照カウント

COM 自体は、オブジェクトが使用されていないと思われる場合、自動的にメモリからオブジェクトを削除しようとしません。 代わりに、オブジェクト プログラマは未使用のオブジェクトを削除する必要があります。 プログラマは、参照カウントに基づいてオブジェクトを削除できるかどうかを判断します。

COM は`IUnknown`、メソッド[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)および[Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)を使用して、オブジェクトのインターフェイスの参照カウントを管理します。 これらのメソッドを呼び出す一般的な規則は次のとおりです。

- クライアントがインターフェイス ポインタを受け取`AddRef`る場合は、そのインターフェイスで呼び出す必要があります。

- クライアントがインターフェイス ポインターを使用し終えた場合は、`Release`常に を呼び出す必要があります。

単純な実装では、各`AddRef`呼び出しが`Release`インクリメントされ、各呼び出しはオブジェクト内のカウンター変数を減分します。 カウントがゼロに戻ると、インターフェイスにはユーザーがなくなり、メモリから解放されます。

参照カウントは、オブジェクトへの各参照 (個別のインターフェイスではなく) がカウントされるように実装することもできます。 この場合、各オブジェクト`AddRef`の`Release`中央実装に対して各デリゲートを呼び出`Release`し、参照カウントが 0 に達するとオブジェクト全体を解放します。

> [!NOTE]
> new`CComObject`演算子を使用して派生オブジェクトを**new**構築する場合、参照カウントは 0 です。 したがって、派生オブジェクトの`AddRef`作成が正常に完了した後に`CComObject`、 に呼び出しを行う必要があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[参照カウントによるオブジェクトの有効期間の管理](/windows/win32/com/managing-object-lifetimes-through-reference-counting)
