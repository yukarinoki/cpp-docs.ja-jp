---
title: 弱い参照および中断サイクル (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92076ac919664fb8ebf6a01513b9382ade52f2a5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754121"
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>弱い参照および中断サイクル (C++/CX)
参照カウントに基づいているどの型システムでも、型への参照は *循環参照*を形成できます。つまり、1 番目のオブジェクトが 2 番目のオブジェクトを、2 番目のオブジェクトが 3 番目のオブジェクトを、のように順次参照していき、最終オブジェクトが最初のオブジェクトを参照します。 この循環参照では、1 つのオブジェクトの参照カウントがゼロになると、オブジェクト全体を正しく削除できません。 この問題 C + の解決に役立つ/cli CX の提供、 [platform::weakreference クラス](../cppcx/platform-weakreference-class.md)クラス。 `WeakReference` オブジェクトは、 [Resolve](../cppcx/platform-weakreference-class.md#resolve) メソッドをサポートしており、オブジェクトが既に存在しない場合は null を返します。また、オブジェクトが生きている状態であっても [型でない場合は、](../cppcx/platform-invalidcastexception-class.md) Platform::InvalidCastException `T`をスローします。  
  
 `WeakReference` を使用する必要がある 1 つのシナリオは、 `this` ポインターがイベント ハンドラーを定義するために使用されるラムダ式にキャプチャされるときです。 イベント ハンドラーを定義するときは、名前付きメソッドを使用することをお勧めします。ただし、イベント ハンドラーにラムダを使用するか、またはその他の状況で参照カウント サイクルを中断する必要がある場合には、 `WeakReference`を使用してください。 次に例を示します。  
  
```  
  
using namespace Platform::Details;  
using namespace Windows::UI::Xaml;  
using namespace Windows::UI::Xaml::Input;  
using namespace Windows::UI::Xaml::Controls;  
  
Class1::Class1()  
{  
    // Class1 has a reference to m_Page  
    m_Page = ref new Page();  
  
    // m_Page will have a reference to this Class1  
    // so create a weak reference to this  
    WeakReference wr(this);  
    m_Page->DoubleTapped += ref new DoubleTappedEventHandler(   
        [wr](Object^ sender, DoubleTappedRoutedEventArgs^ args)  
    {  
       // Use the weak reference to get the object  
       Class1^ c = wr.Resolve<Class1>();  
       if (c != nullptr)  
       {  
           c->m_eventFired = true;  
       }  
       else  
       {  
           // Inform the event that this handler should be removed  
           // from the subscriber list  
           throw ref new DisconnectedException();  
       }  
    });   
}  
  
}  
```  
  
 イベント ハンドラーが `DisconnectedException`をスローした場合、そのハンドラーはサブスクライバー リストから削除されます。  
  
## <a name="see-also"></a>関連項目  


