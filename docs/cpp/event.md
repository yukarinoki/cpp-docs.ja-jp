---
title: __event
ms.date: 11/04/2016
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
ms.openlocfilehash: c1c9fa5a6df4cbb1c18e5d5406bdde0197d155b2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498824"
---
# <a name="__event"></a>__event

イベントを宣言します。

## <a name="syntax"></a>構文

```
__event method-declarator;
__event __interface interface-specifier;
__event member-declarator;
```

## <a name="remarks"></a>解説

キーワードは、 **`__event`** メソッド宣言、インターフェイス宣言、またはデータメンバー宣言に適用できます。 ただし、キーワードを使用して、 **`__event`** 入れ子になったクラスのメンバーを修飾することはできません。

イベント ソースとイベント レシーバーがネイティブ C++、COM、またはマネージド (.NET Framework) であるかによって、次の構成体をイベントとして使用できます。

|ネイティブ C++|COM (COM)|マネージド (.NET Framework)|
|------------------|---------|--------------------------------|
|メソッド|—|メソッド|
|—|interface|—|
|—|—|データ メンバー (data member)|

ハンドラーメソッドをイベントメソッドに関連付けるには、イベントレシーバーで [__hook](../cpp/hook.md) を使用します。 キーワードを使用してイベントを作成した後 **`__event`** 、イベントが呼び出されると、そのイベントにフックされたすべてのイベントハンドラーが呼び出されることに注意してください。

**`__event`** メソッド宣言には定義を含めることができません。定義は暗黙的に生成されるため、通常のメソッドと同様にイベントメソッドを呼び出すことができます。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="native-events"></a>ネイティブ イベント

ネイティブ イベントはメソッドです。 戻り値の型は、通常は HRESULT またはですが、を **`void`** 含む任意の整数型にすることができ **`enum`** ます。 イベントが整数の戻り値の型を使用していて、イベント ハンドラーがゼロ以外の値を返すときのエラー条件が定義されていると、発生するイベントは他のデリゲートを呼び出します。

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

サンプルコードについては、「 [ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md) 」を参照してください。

## <a name="com-events"></a>COM イベント

COM イベントはインターフェイスです。 イベントソースインターフェイスのメソッドのパラメーターは、パラメーター *に含ま* れている必要があります (ただし、これは厳密には適用されません)。これは、 *out* パラメーターがマルチキャストでは役に立たないためです。 *Out*パラメーターを使用すると、レベル1の警告が発行されます。

戻り値の型は通常、HRESULT またはです **`void`** が、などの任意の整数型を指定でき **`enum`** ます。 イベントが整数の戻り値の型を使用していて、イベント ハンドラーがゼロ以外の値を返すと、これはエラー状態であり、発生するイベントは他のデリゲートの呼び出しをアボートします。 コンパイラは、生成された IDL の [ソース](../windows/attributes/source-cpp.md) としてイベントソースインターフェイスを自動的にマークすることに注意してください。

COM イベントソースの場合、 [__interface](../cpp/interface.md) キーワードは常にである必要が **`__event`** あります。

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

サンプルコードについては、「 [COM でのイベント処理](../cpp/event-handling-in-com.md) 」を参照してください。

## <a name="managed-events"></a>マネージド イベント

新しい構文でのイベントのコーディングの詳細については、「 [event](../extensions/event-cpp-component-extensions.md)」を参照してください。

マネージド イベントは、データ メンバーまたはメソッドです。 イベントと共に使用する場合、デリゲートの戻り値の型は [共通言語仕様](/dotnet/standard/language-independence-and-language-independent-components)に準拠している必要があります。 イベント ハンドラーの戻り値の型は、デリゲートの戻り値の型と一致する必要があります。 デリゲートの詳細については、「 [デリゲートとイベント](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。 マネージド イベントがメンバー関数である場合、その型はデリゲートへのポインターでなければなりません。

.NET Framework では、それ自身がメソッド (つまり、対応するデリゲートの `Invoke` メソッド) であるかのようにデータ メンバーを処理できます。 マネージド イベント データ メンバーを宣言するためのデリゲート型を事前に定義する必要があります。 これに対し、マネージド イベント メソッドは、まだ定義されていない場合、対応するマネージド デリゲートを暗黙的に定義します。 たとえば、次のように、`OnClick` などのイベント値をイベントとして宣言できます。

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

マネージド イベントを暗黙的に宣言するときは、イベント ハンドラーが追加または削除されたときに呼び出される追加および削除アクセサーを指定できます。 クラスの外部からイベントを呼び出す (発生させる) メソッドを定義することもできます。

## <a name="example-native-events"></a>例: ネイティブ イベント

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>例: COM イベント

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[イベント処理](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)
