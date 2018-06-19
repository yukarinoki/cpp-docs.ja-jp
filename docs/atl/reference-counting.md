---
title: 参照カウント (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1ba27f00bf25f88575101b1299daf50f94000ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358249"
---
# <a name="reference-counting"></a>参照カウント
COM 自体は自動的に試みませんオブジェクトが使用されていないと思われるときに、メモリからオブジェクトを削除します。 代わりに、オブジェクトのプログラマが使用されていないオブジェクトを削除する必要があります。 プログラマは、オブジェクトを参照カウントに基づいて削除されることができるかどうかを判断します。  
  
 COM の使用、 **IUnknown**メソッド、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)をオブジェクト上のインターフェイスの参照カウントを管理します。 これらのメソッドを呼び出すための一般的な規則は次のとおりです。  
  
-   クライアントが、インターフェイス ポインターを受信するたびに`AddRef`インターフェイスで呼び出す必要があります。  
  
-   インターフェイス ポインターを使用して、クライアントが完了するたびに呼び出す必要があります**リリース**です。  
  
 単純な実装では、各`AddRef`インクリメントおよび各を呼び出す**リリース**オブジェクト内のカウンター変数をデクリメントを呼び出します。 カウントがゼロに返されるとき不要になったインターフェイスのすべてのユーザー、メモリから自身を削除するために解放します。  
  
 参照カウント実装することも (個別のインターフェイスにはしないオブジェクトへの参照がカウントされるようにします。 この場合、各`AddRef`と**リリース**オブジェクトで集約型の実装にデリゲートを呼び出すと**リリース**参照カウントが 0 になったときに、オブジェクト全体を解放します。  
  
> [!NOTE]
>  ときに、 `CComObject`-を使用して派生オブジェクトを構築、**新しい**演算子、参照カウントが 0 です。 そのため、呼び出しを`AddRef`が正常に作成した後に行う必要があります、 `CComObject`-派生オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [参照カウントをオブジェクトの有効期間を管理します。](http://msdn.microsoft.com/library/windows/desktop/ms687260)

