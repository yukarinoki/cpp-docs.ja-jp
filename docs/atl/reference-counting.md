---
title: 参照カウント (ATL) |Microsoft Docs
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
ms.openlocfilehash: 8e0ce8b2cc412c576b0eded9662d8e70b34cf2ec
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850814"
---
# <a name="reference-counting"></a>参照カウント
COM 自体は自動的にオブジェクトが使用されていないと思われるときに、メモリからオブジェクトを削除する試行されません。 代わりに、オブジェクトのプログラマが使用されていないオブジェクトを削除する必要があります。 プログラマは、オブジェクトを参照カウントに基づいて削除されることがあるかどうかを判断します。  
  
 COM の使用、`IUnknown`メソッド、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)オブジェクトのインターフェイスの参照カウントを管理します。 これらのメソッドを呼び出すための一般的な規則は次のとおりです。  
  
-   クライアントが、インターフェイス ポインターを受け取るたびに`AddRef`インターフェイスで呼び出す必要があります。  
  
-   インターフェイス ポインターを使用して、クライアントが完了するたびに呼び出す必要があります`Release`します。  
  
 単純な実装では、各`AddRef`インクリメントおよび各を呼び出す`Release`オブジェクト内のカウンター変数をデクリメントを呼び出します。 カウントが 0 に戻るときインターフェイスを不要になったすべてのユーザーがあり、無料自体をメモリから削除します。  
  
 (個別のインターフェイスにはしないオブジェクトへの参照をカウントするため、参照カウントを実装こともできます。 この場合、各`AddRef`と`Release`、オブジェクトのサーバーの全体の実装にデリゲートを呼び出すと`Release`参照カウントがゼロになったときに、オブジェクト全体を解放します。  
  
> [!NOTE]
>  ときに、 `CComObject`-を使用して派生オブジェクトを構築、**新しい**演算子、参照カウントが 0 です。 そのため、呼び出しを`AddRef`正常に作成した後に行う必要があります、 `CComObject`-派生オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [参照カウントをオブジェクトの有効期間を管理します。](http://msdn.microsoft.com/library/windows/desktop/ms687260)

