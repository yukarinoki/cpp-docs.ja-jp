---
title: COM でのイベント処理
ms.date: 11/04/2016
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
ms.openlocfilehash: be71bd9eac44c51a2e6a7cdeb925a1ca0b8b5dfb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231209"
---
# <a name="event-handling-in-com"></a>COM でのイベント処理

COM イベント処理では、 [event_source](../windows/attributes/event-source.md)と[event_receiver](../windows/attributes/event-receiver.md)属性を使用して、イベントソースとイベントレシーバーをそれぞれ設定し `type` = `com` ます。 これらの属性により、カスタム、ディスパッチ、デュアルの各インターフェイスの適切なコードが挿入され、適用先のクラスでイベントを発生させ、COM 接続ポイントを通じてイベントを処理できるようになります。

## <a name="declaring-events"></a>イベントの宣言

イベントソースクラスでは、インターフェイス宣言で[__event](../cpp/event.md)キーワードを使用して、そのインターフェイスのメソッドをイベントとして宣言します。 このインターフェイスのイベントは、インターフェイス メソッドとして呼び出されたときに発生します。 イベントインターフェイスのメソッドには、0個以上のパラメーターを含めることができます (すべてがパラメーター*に含ま*れている必要があります)。 戻り値の型は void または任意の整数型です。

## <a name="defining-event-handlers"></a>イベント ハンドラーの定義

イベント レシーバー クラスでは、イベント ハンドラーを定義します。イベント ハンドラーは、処理するイベントと一致するシグニチャ (戻り値の型、呼び出し規則、引数) を持つメソッドです。 COM イベントの場合、呼び出し規約が一致している必要はありません。詳細については、以下の「[レイアウトに依存する COM イベント](#vcconeventhandlingincomanchorlayoutdependentcomevents)」を参照してください。

## <a name="hooking-event-handlers-to-events"></a>イベントへのイベント ハンドラーのフック

また、イベントレシーバークラスでは、組み込み関数[__hook](../cpp/hook.md)を使用してイベントをイベントハンドラーに関連付け[__unhook](../cpp/unhook.md)たり、イベントハンドラーからイベントの関連付けを解除したりできます。 複数のイベントを 1 つのイベント ハンドラーにフックすることも、複数のイベント ハンドラーを 1 つのイベントにフックすることもできます。

> [!NOTE]
> 通常、COM イベント レシーバーからイベント ソース インターフェイス定義へのアクセスを許可するには、2 つの方法があります。 最初の方法は、次に示すように、共通のヘッダー ファイルを共有することです。 2つ目の方法では、インポート修飾子を使用して[#import](../preprocessor/hash-import-directive-cpp.md)を使用します。これにより、属性によっ `embedded_idl` て生成されたコードが保存されたファイルにイベントソースタイプライブラリが書き込まれます。

## <a name="firing-events"></a>イベントの発生

イベントを発生させるには、 **`__event`** イベントソースクラスでキーワードを使用して宣言されたインターフェイスのメソッドを呼び出します。 ハンドラーがイベントにフックされている場合は、ハンドラーが呼び出されます。

### <a name="com-event-code"></a>COM イベント コード

次の例に、COM クラスでイベントを発生させる方法を示します。 例をコンパイルして実行するには、コード内のコメントを参照してください。

```cpp
// evh_server.h
#pragma once

[ dual, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IEvents {
   [id(1)] HRESULT MyEvent([in] int value);
};

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT FireEvent();
};

class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;
```

次は、サーバーです。

```cpp
// evh_server.cpp
// compile with: /LD
// post-build command: Regsvr32.exe /s evh_server.dll
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include "evh_server.h"

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      __raise MyEvent(123);
      return S_OK;
   }
};
```

次は、クライアントです。

```cpp
// evh_client.cpp
// compile with: /link /OPT:NOREF
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <stdio.h>
#include "evh_server.h"

[ module(name="EventReceiver") ];

[ event_receiver(com) ]
class CReceiver {
public:
   HRESULT MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
      return S_OK;
   }

   HRESULT MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
      return S_OK;
   }

   void HookEvent(IEventSource* pSource) {
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void UnhookEvent(IEventSource* pSource) {
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   // Create COM object
   CoInitialize(NULL);
   {
      IEventSource* pSource = 0;
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);
      if (FAILED(hr)) {
         return -1;
      }

      // Create receiver and fire event
      CReceiver receiver;
      receiver.HookEvent(pSource);
      pSource->FireEvent();
      receiver.UnhookEvent(pSource);
   }
   CoUninitialize();
   return 0;
}
```

### <a name="output"></a>出力

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

## <a name="layout-dependent-com-events"></a><a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a>レイアウト依存 COM イベント

レイアウトの依存関係は、COM プログラミングにおいてのみ考慮する項目です。 ネイティブおよびマネージド イベント処理では、ハンドラーのシグニチャ (戻り値の型、呼び出し規約、および引数) がイベントと一致する必要がありますが、イベント ハンドラー名はイベントと一致する必要はありません。

ただし、COM イベント処理では、の*layout_dependent*パラメーターをに設定すると、 `event_receiver` **`true`** 名前とシグネチャの一致が適用されます。 これは、イベント レシーバーのハンドラーの名前とシグニチャが、フックするイベントの名前とシグニチャに正確に一致する必要があることを意味します。

*Layout_dependent*がに設定されている場合 **`false`** 、呼び出し規約とストレージクラス (virtual、static など) は、イベントの発生メソッドとフックメソッド (デリゲート) との間で混在させて一致させることができます。 *Layout_dependent*を設定する方が少し効率的です = **`true`** 。

たとえば、次のメソッドを持つ `IEventSource` が定義されているとします。

```cpp
[id(1)] HRESULT MyEvent1([in] int value);
[id(2)] HRESULT MyEvent2([in] int value);
```

イベント ソースが次の形式になっているとします。

```cpp
[coclass, event_source(com)]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      MyEvent1(123);
      MyEvent2(123);
      return S_OK;
   }
};
```

そこで、イベント レシーバーでは、次のように、`IEventSource` のメソッドにフックされるハンドラーは名前およびシグネチャを一致させる必要があります。

```cpp
[coclass, event_receiver(com, true)]
class CReceiver {
public:
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1
      ...
   }
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2
      ...
   }
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)
      ...
   }
   void HookEvent(IEventSource* pSource) {
      __hook(IFace, pSource);  // Hooks up all name-matched events
                               // under layout_dependent = true
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid
   }
};
```

## <a name="see-also"></a>関連項目

[イベント処理](../cpp/event-handling.md)
