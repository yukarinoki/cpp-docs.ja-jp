---
title: __hook
description: ネイティブイベント処理に Microsoft C++ extension キーワードを使用する方法につい `__hook` て説明します。
ms.date: 11/20/2020
f1_keywords:
- __hook_cpp
- __hook
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.openlocfilehash: 2a2bde221c53f0e1d420e2ab3a88eb299f6c284c
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483257"
---
# <a name="__hook-keyword"></a>`__hook` キーワード

ハンドラー メソッドをイベントに関連付けます。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>構文

```cpp
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);

long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>パラメーター

*`&SourceClass::EventMethod`*\
イベント ハンドラー メソッドをフックする先のイベント メソッドへのポインター。

- ネイティブ C++ イベント: *`SourceClass`* はイベントソースクラスであり、 *`EventMethod`* はイベントです。

- COM イベント: *`SourceClass`* はイベントソースインターフェイスであり、 *`EventMethod`* メソッドの1つです。

- マネージイベント: イベント *`SourceClass`* ソースクラスであり、 *`EventMethod`* はイベントです。

*`interface`*\
フックされているインターフェイス名 *`receiver`* *`layout_dependent`* 。属性のパラメーターがである COM イベントレシーバーに対してのみ [`event_receiver`](../windows/attributes/event-receiver.md) **`true`** です。

*`source`*\
イベント ソースのインスタンスへのポインター。 に指定されているコードに応じて `type` `event_receiver` 、 *`source`* 次のいずれかの型を指定できます。

- ネイティブ イベント ソース オブジェクト ポインター。

- `IUnknown`ベースのポインター (COM ソース)。

- マネージド オブジェクトのポインター (マネージド イベントの場合)。

*`&ReceiverClass::HandlerMethod`*\
イベントにフックするイベント ハンドラー メソッドへのポインター。 ハンドラーは、クラスのメソッドまたは同じへの参照として指定されています。 クラス名を指定しない場合、では、クラスが呼び出されているもの **`__hook`** と見なされます。

- ネイティブ C++ イベント: *`ReceiverClass`* はイベントレシーバークラスであり、 `HandlerMethod` はハンドラーです。

- COM イベント: *`ReceiverClass`* はイベントレシーバーインターフェイスで、 *`HandlerMethod`* はハンドラーの1つです。

- マネージイベント: *`ReceiverClass`* はイベントレシーバークラスであり、 *`HandlerMethod`* はハンドラーです。

*`receiver`*\
Optionalイベントレシーバークラスのインスタンスへのポインター。 レシーバーを指定しない場合、既定値は、が呼び出されるレシーバークラスまたは構造体です **`__hook`** 。

## <a name="usage"></a>使用

イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。

## <a name="remarks"></a>注釈

イベントレシーバーで組み込み関数を使用し **`__hook`** て、ハンドラーメソッドをイベントメソッドに関連付けるか、フックします。 ソースで指定されたイベントが発生すると、指定されたハンドラーが呼び出されます。 複数のイベント ハンドラーを 1 つのイベントに、または複数のイベントを 1 つのイベント ハンドラーにフックすることができます。

には、2つの形式があり **`__hook`** ます。 ほとんどの場合、最初の (4 つの引数) 形式を使用できます。具体的には、属性の *layout_dependent* パラメーターがである COM イベントレシーバーに対して使用し [`event_receiver`](../windows/attributes/event-receiver.md) **`false`** ます。

このような場合は、いずれかのメソッドでイベントを発生させる前に、インターフェイスのすべてのメソッドをフックする必要はありません。 イベントを処理するメソッドをフックするだけです。 の2番目 (引数が2つ) の形式は、の **`__hook`** COM イベントレシーバーに対してのみ使用でき *`layout_dependent`* **`= true`** ます。

**`__hook`** long 型の値を返します。 ゼロ以外の戻り値は、エラーが発生したことを示します (マネージド イベントは例外をスローします)。

コンパイラは、イベントが存在するかどうかをチェックし、イベント プロシージャがデリゲート シグネチャと一致することを確認します。

**`__hook`** **`__unhook`** COM イベントを除き、イベントレシーバーの外部でおよびを呼び出すことができます。

を使用する代わりに、 **`__hook`** + = 演算子を使用することもできます。

新しい構文でのマネージイベントのコーディングの詳細については、「」を参照してください [`event`](../extensions/event-cpp-component-extensions.md) 。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

サンプルについては、「 [ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md) 」および「 [COM でのイベント](../cpp/event-handling-in-com.md) 処理」を参照してください。

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)\
[イベント処理](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
