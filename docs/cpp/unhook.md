---
title: __unhook
description: ネイティブイベント処理に Microsoft C++ extension キーワードを使用する方法につい `__unhook` て説明します。
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.openlocfilehash: 74f8b814ea23c5513b7b73bf90ef59984742a266
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483322"
---
# <a name="__unhook-keyword"></a>`__unhook` キーワード

イベントからハンドラーメソッドの関連付けを解除します。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

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

### <a name="parameters"></a>パラメーター

*`&SourceClass::EventMethod`*\
イベント ハンドラー メソッドをアンフックする元のイベント メソッドへのポインター。

- ネイティブ C++ イベント: *`SourceClass`* はイベントソースクラスであり、 *`EventMethod`* はイベントです。

- COM イベント: *`SourceClass`* はイベントソースインターフェイスであり、 *`EventMethod`* メソッドの1つです。

- マネージイベント: イベント *`SourceClass`* ソースクラスであり、 *`EventMethod`* はイベントです。

*`interface`*\
属性の *layout_dependent* パラメーターがである COM イベントレシーバーに対してのみ、*受信側* からアンフックされるインターフェイス名 [`event_receiver`](../windows/attributes/event-receiver.md) **`true`** 。

*`source`*\
イベント ソースのインスタンスへのポインター。 `type`に指定されたコードに応じて `event_receiver` 、 *source* は次のいずれかの型になります。

- ネイティブ イベント ソース オブジェクト ポインター。

- `IUnknown`ベースのポインター (COM ソース)。

- マネージド オブジェクトのポインター (マネージド イベントの場合)。

*`&ReceiverClass::HandlerMethod`* イベントからアンフックされるイベントハンドラーメソッドへのポインター。 ハンドラーは、クラスのメソッドまたは同じに対する参照として指定されています。クラス名を指定しない場合、は、 **`__unhook`** クラスが呼び出されているものであると想定します。

- ネイティブ C++ イベント: *`ReceiverClass`* はイベントレシーバークラスであり、 `HandlerMethod` はハンドラーです。

- COM イベント: *`ReceiverClass`* はイベントレシーバーインターフェイスで、 *`HandlerMethod`* はハンドラーの1つです。

- マネージイベント: *`ReceiverClass`* はイベントレシーバークラスであり、 *`HandlerMethod`* はハンドラーです。

*`receiver`* optionalイベントレシーバークラスのインスタンスへのポインター。 レシーバーを指定しない場合、既定値は、が呼び出されるレシーバークラスまたは構造体です **`__unhook`** 。

## <a name="usage"></a>使用

は、を含むすべての関数スコープで、 `main` イベントレシーバークラスの外部で使用できます。

## <a name="remarks"></a>注釈

イベントレシーバーで組み込み関数を使用して、 **`__unhook`** イベントメソッドからのハンドラーメソッドの関連付けの解除、または "アンフック" を行います。

には3つの形式があり **`__unhook`** ます。 ほとんどの場合、最初の形式 (引数が 4 つ) を使用できます。 の2番目 (引数が2つ) の形式は、COM イベントレシーバーに対してのみ使用できます。これにより、 **`__unhook`** イベントインターフェイス全体がアンフックされます。 3 番目 (引数が 1 つ) の形式は、指定したソースからすべてのデリゲートをアンフックする場合に使用します。

ゼロ以外の戻り値は、エラーが発生したことを示します (マネージド イベントは例外をスローします)。

**`__unhook`** まだフックされていないイベントおよびイベントハンドラーに対してを呼び出すと、無効になります。

コンパイル時に、コンパイラはイベントが存在することを確認し、指定されたハンドラーを使用してパラメーターの型チェックを実行します。

**`__hook`** **`__unhook`** COM イベントを除き、イベントレシーバーの外部でおよびを呼び出すことができます。

を使用する代わりに、 **`__unhook`** -= 演算子を使用することもできます。

新しい構文でのマネージイベントのコーディングの詳細については、「 [event](../extensions/event-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

サンプルについては、「 [ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md) 」および「 [COM でのイベント](../cpp/event-handling-in-com.md) 処理」を参照してください。

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__raise`](../cpp/raise.md)
