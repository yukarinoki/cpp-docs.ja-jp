---
description: 詳細については、「弱い参照と中断サイクル (C++/CX)」を参照してください。
title: 弱い参照および中断サイクル (C++/CX)
ms.date: 01/22/2017
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
ms.openlocfilehash: 0c42081b0030ee697eab63fa519e2f6cbe4fe090
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288023"
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>弱い参照および中断サイクル (C++/CX)

参照カウントに基づいているどの型システムでも、型への参照は *循環参照* を形成できます。つまり、1 番目のオブジェクトが 2 番目のオブジェクトを、2 番目のオブジェクトが 3 番目のオブジェクトを、のように順次参照していき、最終オブジェクトが最初のオブジェクトを参照します。 この循環参照では、1 つのオブジェクトの参照カウントがゼロになると、オブジェクト全体を正しく削除できません。 この問題を解決するために、C++/CX には [Platform:: WeakReference class](../cppcx/platform-weakreference-class.md) クラスが用意されています。 `WeakReference` オブジェクトは、 [Resolve](../cppcx/platform-weakreference-class.md#resolve) メソッドをサポートしており、オブジェクトが既に存在しない場合は null を返します。また、オブジェクトが生きている状態であっても [型でない場合は、](../cppcx/platform-invalidcastexception-class.md) Platform::InvalidCastException `T`をスローします。

を使用する必要があるシナリオの1つ `WeakReference` は、 **`this`** イベントハンドラーを定義するために使用されるラムダ式でポインターをキャプチャする場合です。 イベント ハンドラーを定義するときは、名前付きメソッドを使用することをお勧めします。ただし、イベント ハンドラーにラムダを使用するか、またはその他の状況で参照カウント サイクルを中断する必要がある場合には、 `WeakReference`を使用してください。 次に例を示します。

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
