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
ms.openlocfilehash: f90c818e58ae7ef6e4a0b771cb53ae5b185d1617
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224345"
---
# <a name="reference-counting"></a>参照カウント

COM 自体は、オブジェクトが使用されなくなったと判断された場合に、メモリからオブジェクトを自動的に削除しようとしません。 代わりに、オブジェクトプログラマは、使用されていないオブジェクトを削除する必要があります。 プログラマは、参照カウントに基づいてオブジェクトを削除できるかどうかを判断します。

COM では、 `IUnknown` [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)および[Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)メソッドを使用して、オブジェクトのインターフェイスの参照カウントを管理します。 これらのメソッドを呼び出すための一般的な規則は次のとおりです。

- クライアントは、インターフェイスポインターを受け取るたびに、 `AddRef` インターフェイスでを呼び出す必要があります。

- クライアントがインターフェイスポインターの使用を終了するたびに、を呼び出す必要があり `Release` ます。

単純な実装では、各 `AddRef` 呼び出しがインクリメントされ、各呼び出しが `Release` オブジェクト内のカウンター変数をデクリメントします。 カウントが0に戻ると、インターフェイスにはユーザーが含まれなくなり、メモリから自由に削除できます。

参照カウントは、(個々のインターフェイスではなく) オブジェクトへの各参照がカウントされるように実装することもできます。 この場合、各およびは、 `AddRef` `Release` オブジェクトの中心の実装にデリゲートし、 `Release` 参照カウントが0になるとオブジェクト全体を解放します。

> [!NOTE]
> `CComObject`派生オブジェクトが演算子を使用して構築された場合 **`new`** 、参照カウントは0になります。 したがって、の呼び出しは、が `AddRef` 派生したオブジェクトを正常に作成した後に行う必要があり `CComObject` ます。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[参照カウントによるオブジェクトの有効期間の管理](/windows/win32/com/managing-object-lifetimes-through-reference-counting)
