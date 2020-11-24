---
title: COM でのイベント処理
description: COM イベント処理に Microsoft C++ 拡張機能を使用する方法について説明します。
ms.date: 11/20/2020
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
ms.openlocfilehash: 0c664f052fe211c88ad097c9d2617ec47f180eff
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483114"
---
# <a name="event-handling-in-com"></a>COM でのイベント処理

COM イベント処理では、属性と属性を使用して、イベントソースとイベントレシーバーを [`event_source`](../windows/attributes/event-source.md) [`event_receiver`](../windows/attributes/event-receiver.md) それぞれ設定 `type` = `com` します。 これらの属性は、カスタム、ディスパッチ、およびデュアルインターフェイスに適切なコードを挿入します。 挿入されたコードは、属性付きクラスが COM 接続ポイントを使用してイベントを発生させ、イベントを処理できるようにします。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="declaring-events"></a>イベントの宣言

イベントソースクラスでは、 [`__event`](../cpp/event.md) インターフェイス宣言でキーワードを使用して、そのインターフェイスのメソッドをイベントとして宣言します。 このインターフェイスのイベントは、インターフェイス メソッドとして呼び出されたときに発生します。 イベントインターフェイスのメソッドには、0個以上のパラメーターを含めることができます (すべてがパラメーター *に含ま* れている必要があります)。 戻り値の型は void または任意の整数型です。

## <a name="defining-event-handlers"></a>イベントハンドラーの定義

イベントレシーバークラスでは、イベントハンドラーを定義します。 イベントハンドラーは、処理するイベントに一致するシグネチャ (戻り値の型、呼び出し規則、および引数) を持つメソッドです。 COM イベントの場合、呼び出し規約が一致する必要はありません。 詳細については、以下の「 [レイアウトに依存する COM イベント](#vcconeventhandlingincomanchorlayoutdependentcomevents) 」を参照してください。

## <a name="hooking-event-handlers-to-events"></a>イベントへのイベントハンドラーのフック

また、イベントレシーバークラスでは、イベントをイベント [`__hook`](../cpp/hook.md) ハンドラーに関連付けたり、イベントハンドラーからイベントの関連付けを解除したりするために、組み込み関数を使用し [`__unhook`](../cpp/unhook.md) ます。 複数のイベントを 1 つのイベント ハンドラーにフックすることも、複数のイベント ハンドラーを 1 つのイベントにフックすることもできます。

> [!NOTE]
> 通常、COM イベント レシーバーからイベント ソース インターフェイス定義へのアクセスを許可するには、2 つの方法があります。 最初の方法は、次に示すように、共通のヘッダー ファイルを共有することです。 2つ目の方法では、インポート修飾子を使用して [#import](../preprocessor/hash-import-directive-cpp.md) を使用します。これにより、属性によっ `embedded_idl` て生成されたコードが保存されたファイルにイベントソースタイプライブラリが書き込まれます。

## <a name="firing-events"></a>イベントの発生

イベントを発生させるには、 **`__event`** イベントソースクラスでキーワードを使用して宣言されたインターフェイスでメソッドを呼び出します。 ハンドラーがイベントにフックされている場合は、ハンドラーが呼び出されます。

### <a name="com-event-code"></a>COM イベントコード

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

## <a name="layout-dependent-com-events"></a><a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> レイアウトに依存する COM イベント

レイアウトの依存関係は、COM プログラミングにおいてのみ考慮する項目です。 ネイティブおよびマネージイベント処理では、ハンドラーのシグネチャ (戻り値の型、呼び出し規則、および引数) がイベントと一致している必要がありますが、ハンドラー名はイベントと一致する必要はありません。

ただし、COM イベント処理では、のパラメーターをに設定すると、 *`layout_dependent`* `event_receiver` **`true`** 名前とシグネチャの一致が適用されます。 イベントレシーバーおよびフックされたイベント内のハンドラーの名前とシグネチャは、正確に一致している必要があります。

*`layout_dependent`* がに設定されている場合 **`false`** 、呼び出し規約とストレージクラス (virtual、static など) は、発生イベントメソッドとフックメソッド (デリゲート) との間で混在させることができます。 の方がやや効率的 *`layout_dependent`* = **`true`** です。

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
