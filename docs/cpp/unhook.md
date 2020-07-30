---
title: __unhook
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
ms.openlocfilehash: 84df5ad0ff27e6b09134b0f92f14f8e9b6fdc817
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233575"
---
# <a name="__unhook"></a>__unhook

イベントからハンドラー メソッドの関連付けを解除します。

## <a name="syntax"></a>構文

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);
long  __unhook(
   interface,
   source
);
long  __unhook(
   source
);
```

#### <a name="parameters"></a>パラメーター

**&***Sourceclass* `::`*Eventmethod*イベントハンドラーメソッドをアンフックするイベントメソッドへのポインター。

- ネイティブ C++ イベント: *Sourceclass*はイベントソースクラスであり、 *eventmethod*はイベントです。

- COM イベント: *Sourceclass*はイベントソースインターフェイスであり、 *eventmethod*はそのメソッドの1つです。

- マネージイベント: *Sourceclass*はイベントソースクラスであり、 *eventmethod*はイベントです。

*interface*<br/>
[Event_receiver](../windows/attributes/event-receiver.md)属性の*layout_dependent*パラメーターがである COM イベントレシーバーの場合にのみ、*受信側*からアンフックされるインターフェイス名 **`true`** 。

*source*<br/>
イベント ソースのインスタンスへのポインター。 `type`に指定されたコードに応じて `event_receiver` 、 *source*は次のいずれかになります。

- ネイティブ イベント ソース オブジェクト ポインター。

- `IUnknown`ベースのポインター (COM ソース)。

- マネージド オブジェクトのポインター (マネージド イベントの場合)。

**&***Receiverclass* `::``HandlerMethod`イベントからアンフックされるイベントハンドラーメソッドへのポインター。 ハンドラーは、クラスのメソッドまたは同じに対する参照として指定されています。クラス名を指定しない場合、は、 **`__unhook`** クラスが呼び出されることを前提としています。

- ネイティブ C++ イベント: *Receiverclass*はイベントレシーバークラスであり、 `HandlerMethod` はハンドラーです。

- COM イベント: *Receiverclass*はイベントレシーバーインターフェイスであり、 `HandlerMethod` ハンドラーの1つです。

- マネージイベント: *Receiverclass*はイベントレシーバークラスであり、 `HandlerMethod` はハンドラーです。

*レシーバー*(省略可能) イベントレシーバークラスのインスタンスへのポインター。 レシーバーを指定しない場合、既定値は、が呼び出されるレシーバークラスまたは構造体です **`__unhook`** 。

## <a name="usage"></a>使用法

イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。

## <a name="remarks"></a>解説

イベントレシーバーで組み込み関数を使用して、イベントメソッドからのハンドラーメソッドの関連付けの解除、 **`__unhook`** または "アンフック" を行います。

には3つの形式があり **`__unhook`** ます。 ほとんどの場合、最初の形式 (引数が 4 つ) を使用できます。 の2番目 (引数が2つ) の形式は、COM イベントレシーバーに対してのみ使用できます。これにより、 **`__unhook`** イベントインターフェイス全体がアンフックされます。 3 番目 (引数が 1 つ) の形式は、指定したソースからすべてのデリゲートをアンフックする場合に使用します。

ゼロ以外の戻り値は、エラーが発生したことを示します (マネージド イベントは例外をスローします)。

まだフックされて **`__unhook`** いないイベントおよびイベントハンドラーに対してを呼び出すと、無効になります。

コンパイル時に、コンパイラはイベントが存在することを確認し、指定されたハンドラーを使用してパラメーターの型チェックを実行します。

COM イベントを除き、およびは **`__hook`** 、 **`__unhook`** イベントレシーバーの外部で呼び出すことができます。

を使用する代わりに、 **`__unhook`** -= 演算子を使用することもできます。

新しい構文でのマネージイベントのコーディングの詳細については、「 [event](../extensions/event-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

サンプルについては、「[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)」および「 [COM でのイベント](../cpp/event-handling-in-com.md)処理」を参照してください。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
