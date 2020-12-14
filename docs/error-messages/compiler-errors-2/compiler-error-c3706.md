---
description: 詳細については、「コンパイラエラー C3706」を参照してください。
title: コンパイラ エラー C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: e4dcb65d29e24ae40bc311f1d4229edca173e916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241860"
---
# <a name="compiler-error-c3706"></a>コンパイラ エラー C3706

' function ': COM イベントを発生させる COM インターフェイスでなければなりません。

COM イベントを発生させるために使用するイベントインターフェイスは、COM インターフェイスである必要があります。 このような場合は、インターフェイスを Visual C++ 属性を使用して定義するか、#import の embedded_idl 属性を持つタイプライブラリの [#import](../../preprocessor/hash-import-directive-cpp.md) を使用してインポートする必要があります。

`#include`COM イベントを使用するには、次のサンプルに示されている ATL ヘッダーファイルの行が必要です。 このエラーを解決するには、 `IEvents` インターフェイス定義に次の属性のいずれかを適用して (イベントインターフェイス)、COM インターフェイスを作成します ( [オブジェクト](../../windows/attributes/object-cpp.md)、 [デュアル](../../windows/attributes/dual.md)、または [ディスパッチ](../../windows/attributes/dispinterface.md)インターフェイス)。

インターフェイスが MIDL によって生成されたヘッダーファイルからのものである場合、コンパイラは COM インターフェイスとして認識しません。

次の例では、C3706 が生成されます。

```cpp
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
