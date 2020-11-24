---
title: __event
description: ネイティブイベント処理に Microsoft C++ extension キーワードを使用する方法につい `__event` て説明します。
ms.date: 11/20/2020
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.openlocfilehash: 1678699d9b66c1a49dd5ca2bb019a6229c37a031
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483143"
---
# <a name="__event-keyword"></a>`__event` キーワード

イベントを宣言します。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>Syntax

> **`__event`** *`member-function-declarator`* **`;`**\
> **`__event`** **`__interface`** *`interface-specifier`* **`;`**\
> **`__event`** *`data-member-declarator`* **`;`**

## <a name="remarks"></a>注釈

Microsoft 固有のキーワードは、 **`__event`** メンバー関数の宣言、インターフェイスの宣言、またはデータメンバーの宣言に適用できます。 ただし、キーワードを使用して、 **`__event`** 入れ子になったクラスのメンバーを修飾することはできません。

イベント ソースとイベント レシーバーがネイティブ C++、COM、またはマネージド (.NET Framework) であるかによって、次の構成体をイベントとして使用できます。

| ネイティブ C++ | COM (COM) | マネージド (.NET Framework) |
|--|--|--|
| メンバー関数 | - | method |
| - | interface | - |
| - | - | データ メンバー (data member) |

[`__hook`](../cpp/hook.md)ハンドラーメンバー関数をイベントメンバー関数に関連付けるには、イベントレシーバーでを使用します。 キーワードを使用してイベントを作成した後は **`__event`** 、イベントが呼び出されたときに呼び出された後に、すべてのイベントハンドラーがそのイベントにフックされます。

**`__event`** メンバー関数の宣言には定義を含めることができません。定義は暗黙的に生成されるため、通常のメンバー関数と同じように、イベントメンバー関数を呼び出すことができます。

> [!NOTE]
> テンプレートクラスまたは構造体にイベントを含めることはできません。

## <a name="native-events"></a>ネイティブイベント

ネイティブイベントは、メンバー関数です。 戻り値の型は、通常 `HRESULT` はまたはですが、を **`void`** 含む任意の整数型にすることができ **`enum`** ます。 イベントが整数の戻り値の型を使用する場合、イベントハンドラーが0以外の値を返すときにエラー状態が定義されます。 この場合、発生するイベントは他のデリゲートを呼び出します。

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

サンプルコードについては、「 [ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md) 」を参照してください。

## <a name="com-events"></a>COM イベント

COM イベントはインターフェイスです。 イベントソースインターフェイスのメンバー関数のパラメーターは、パラメーター *に含ま* れている必要がありますが、厳密には適用されません。 これは、マルチキャストを行うときに *out* パラメーターが役に立たないためです。 *Out* パラメーターを使用すると、レベル1の警告が発行されます。

戻り値の型は、通常 `HRESULT` はまたはです **`void`** が、などの任意の整数型を指定でき **`enum`** ます。 イベントが整数の戻り値の型を使用し、イベントハンドラーが0以外の値を返す場合、これはエラー状態になります。 発生するイベントによって、他のデリゲートへの呼び出しが中止されます。 コンパイラは、生成された IDL 内のとしてイベントソースインターフェイスを自動的にマークし [`source`](../windows/attributes/source-cpp.md) ます。

[`__interface`](../cpp/interface.md)COM イベントソースの場合、キーワードは常にである必要が **`__event`** あります。

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

サンプルコードについては、「 [COM でのイベント処理](../cpp/event-handling-in-com.md) 」を参照してください。

## <a name="managed-events"></a>マネージイベント

新しい構文でのイベントのコーディングの詳細については、「 [event](../extensions/event-cpp-component-extensions.md)」を参照してください。

マネージイベントは、データメンバーまたはメンバー関数です。 イベントと共に使用する場合、デリゲートの戻り値の型は [共通言語仕様](/dotnet/standard/language-independence-and-language-independent-components)に準拠している必要があります。 イベント ハンドラーの戻り値の型は、デリゲートの戻り値の型と一致する必要があります。 デリゲートの詳細については、「 [デリゲートとイベント](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。 マネージド イベントがメンバー関数である場合、その型はデリゲートへのポインターでなければなりません。

.NET Framework では、それ自身がメソッド (つまり、対応するデリゲートの `Invoke` メソッド) であるかのようにデータ メンバーを処理できます。 これを行うには、マネージイベントデータメンバーを宣言するためのデリゲート型を事前に定義します。 これに対し、マネージイベントメソッドは、まだ定義されていない場合は、対応するマネージデリゲートを暗黙的に定義します。 たとえば、次のように、`OnClick` などのイベント値をイベントとして宣言できます。

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

マネージイベントを暗黙的に宣言するときに、 `add` `remove` イベントハンドラーが追加または削除されたときに呼び出されるアクセサーとアクセサーを指定できます。 クラスの外部からイベントを呼び出す (発生する) メンバー関数を定義することもできます。

## <a name="example-native-events"></a>例: ネイティブイベント

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

[Keywords](../cpp/keywords-cpp.md)\
[イベント処理](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
