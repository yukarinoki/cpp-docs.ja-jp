---
title: コンパイラ エラー C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 2d474db5a4d50aed7b59e6f48fb5a3e8165f10c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468616"
---
# <a name="compiler-error-c3706"></a>コンパイラ エラー C3706

'function': COM イベントを発生させる COM インターフェイスを使用する必要があります

COM イベントを発生させるを使用するイベント インターフェイスでは、COM インターフェイスを使用する必要があります。 このような状況で、インターフェイスは Visual C 属性を使用して定義する必要がありますか、またはを使用してインポート[#import](../../preprocessor/hash-import-directive-cpp.md) #import の embedded_idl 属性を持つタイプ ライブラリから。

なお、`#include`次の例に示すように、ATL ヘッダー ファイルの行は COM イベントを使用するために必要です。 このエラーを修正するように`IEvents`(イベントのインターフェイス)、次のいずれかの操作を適用することで、COM インターフェイスのインターフェイス定義に属性:[オブジェクト](../../windows/object-cpp.md)、[デュアル](../../windows/dual.md)、または[dispinterface](../../windows/dispinterface.md)します。

インターフェイスは、MIDL によって生成されたヘッダー ファイルからは場合、コンパイラは認識されず、COM インターフェイスとして。

次の例では、C3706 が生成されます。

```
// C3706.cpp
// compile with: /c
// C3706 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following line to resolve.
// [object, uuid="12341234-1234-1234-1234-123412341237"]
__interface IEvents : IUnknown {
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]
};

[dual, uuid="12341234-1234-1234-1234-123412341235"]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]
class CEventSrc : public IBase {
   public:
   __event __interface IEvents;

   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```