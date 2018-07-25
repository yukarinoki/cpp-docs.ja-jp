---
title: 属性の目的 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ea3b731cc22d144e2e20dc70f14e6b0b76b1479
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877837"
---
# <a name="purpose-of-attributes"></a>属性の目的
属性は、言語の従来の構造を分断することがなく、方向は現在不可能で C++ を拡張します。 属性は、プロバイダーの言語機能を動的に拡張する (個別の Dll) を使用します。 属性の主な目的では、コンポーネントの開発者の生産性を高めるだけでなく、COM コンポーネントのオーサリングを簡略化します。 属性を適用するクラス、データ メンバー、またはメンバー関数など、ほぼすべての C++ コンストラクトにします。 この新しいテクノロジが提供する利点の強調表示を次に示します。  
  
-   使い慣れたと単純な呼び出し規約を公開します。  
  
-   使用には、マクロとは異なり、デバッガーによって認識されているコードが挿入されます。  
  
-   により、簡単に耐え難い負担の実装の詳細なしの基本クラスから派生をします。  
  
-   大量のいくつかの簡潔な属性を持つ COM コンポーネントで必要な IDL コードに置き換えます。  
  
 たとえば、ATL のジェネリック クラスの単純なイベント シンクを実装する可能性がありますを適用する、 [event_receiver](../windows/event-receiver.md)など特定のクラスに属性`CMyReceiver`です。 **Event_receiver**属性は、オブジェクト ファイルに適切なコードを挿入する、Visual C コンパイラでコンパイルされます。  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 設定することができます、 **CMyReceiver**メソッド`handler1`と`handler2`イベントを処理する (組み込み関数を使用して[_ _hook](../cpp/hook.md))を使用してを作成することができるイベントソースから[event_source](../windows/event-source.md)です。  
  
## <a name="see-also"></a>関連項目  
 [概念](../windows/attributed-programming-concepts.md)