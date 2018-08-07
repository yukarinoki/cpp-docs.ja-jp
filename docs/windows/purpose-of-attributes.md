---
title: 属性の目的 |Microsoft Docs
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
ms.openlocfilehash: 2ca7757c1b9a8ebf034f68b9a380c09d4a5b08f1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607025"
---
# <a name="purpose-of-attributes"></a>属性の目的
属性は、方向は現在不可能で、言語の従来の構造を損なうことがなく C++ を拡張します。 属性は、プロバイダーの言語機能を動的に拡張する (個別の Dll) を使用します。 属性の主な目的が、コンポーネントの開発者の生産性を高めるだけでなく、COM コンポーネントの作成を簡素化します。 属性を適用するクラス、データ メンバー、またはメンバー関数など、ほぼすべての C++ コンストラクトにします。 この新しいテクノロジが提供する利点の強調表示を次に示します。  
  
-   親しみやすく、単純な呼び出し規則を公開します。  
  
-   使用は、マクロとは異なり、デバッガーによって認識されているコードを挿入します。  
  
-   簡単に大きな負担の実装の詳細なしの基本クラスから派生を使用できます。  
  
-   大量の簡潔ないくつかの属性を持つ COM コンポーネントで必要な IDL コードに置き換えます。  
  
 たとえば、ATL のジェネリック クラスの単純なイベント シンクを実装する可能性がありますを適用する、 [event_receiver](../windows/event-receiver.md)など特定のクラスに属性`CMyReceiver`します。 `event_receiver`属性は、オブジェクト ファイルに適切なコードを挿入する Visual C コンパイラでコンパイルされます。  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 設定することができますし、`CMyReceiver`メソッド`handler1`と`handler2`イベントを処理する (組み込み関数を使用して[_ _hook](../cpp/hook.md)) を使用して作成できるイベント ソースから[event_source](../windows/event-source.md).  
  
## <a name="see-also"></a>関連項目  
 [概念](../windows/attributed-programming-concepts.md)