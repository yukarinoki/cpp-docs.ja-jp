---
title: __hook
ms.date: 11/04/2016
f1_keywords:
- __hook_cpp
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
ms.openlocfilehash: 5a0eaf0a3bc0617dbcd1f43805af8a95291e7e47
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87188168"
---
# <a name="__hook"></a>__hook

ハンドラー メソッドをイベントに関連付けます。

## <a name="syntax"></a>構文

```
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

*&SourceClass:: EventMethod*<br/>
イベント ハンドラー メソッドをフックする先のイベント メソッドへのポインター。

- ネイティブ C++ イベント: *Sourceclass*はイベントソースクラスであり、 *eventmethod*はイベントです。

- COM イベント: *Sourceclass*はイベントソースインターフェイスであり、 *eventmethod*はそのメソッドの1つです。

- マネージイベント: *Sourceclass*はイベントソースクラスであり、 *eventmethod*はイベントです。

*interface*<br/>
*受信側*にフックされるインターフェイス名。 [event_receiver](../windows/attributes/event-receiver.md)属性の*LAYOUT_DEPENDENT*パラメーターがである COM イベントレシーバーに対してのみ使用され **`true`** ます。

*source*<br/>
イベント ソースのインスタンスへのポインター。 `type`に指定されたコードに応じて `event_receiver` 、 *source*は次のいずれかになります。

- ネイティブ イベント ソース オブジェクト ポインター。

- `IUnknown`ベースのポインター (COM ソース)。

- マネージド オブジェクトのポインター (マネージド イベントの場合)。

*ReceiverClass:: ハンドラメソッド&*<br/>
イベントにフックするイベント ハンドラー メソッドへのポインター。 ハンドラーは、クラスのメソッドまたは同じに対する参照として指定されています。クラス名を指定しない場合、は、 **`__hook`** クラスが呼び出されることを前提としています。

- ネイティブ C++ イベント: *Receiverclass*はイベントレシーバークラスであり、 `HandlerMethod` はハンドラーです。

- COM イベント: *Receiverclass*はイベントレシーバーインターフェイスであり、 `HandlerMethod` ハンドラーの1つです。

- マネージイベント: *Receiverclass*はイベントレシーバークラスであり、 `HandlerMethod` はハンドラーです。

*受取*<br/>
Optionalイベントレシーバークラスのインスタンスへのポインター。 レシーバーを指定しない場合、既定値は、が呼び出されるレシーバークラスまたは構造体です **`__hook`** 。

## <a name="usage"></a>使用法

イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。

## <a name="remarks"></a>解説

イベントレシーバーで組み込み関数を使用し **`__hook`** て、ハンドラーメソッドをイベントメソッドに関連付けるか、フックします。 ソースで指定されたイベントが発生すると、指定されたハンドラーが呼び出されます。 複数のイベント ハンドラーを 1 つのイベントに、または複数のイベントを 1 つのイベント ハンドラーにフックすることができます。

には、2つの形式があり **`__hook`** ます。 ほとんどの場合、最初の (4 つの引数) 形式を使用できます。具体的には、 [event_receiver](../windows/attributes/event-receiver.md)属性の*layout_dependent*パラメーターがである COM イベントレシーバーに対して使用し **`false`** ます。

このような場合、メソッドの 1 つでイベントを発生させる前に、インターフェイスのすべてのメソッドをフックする必要はありません。イベントを処理するメソッドのみフックする必要があります。 の2番目 (引数が2つ) の形式は、 **`__hook`** *layout_dependent* **= true**である COM イベントレシーバーに対してのみ使用できます。

**`__hook`** long 型の値を返します。 ゼロ以外の戻り値は、エラーが発生したことを示します (マネージド イベントは例外をスローします)。

コンパイラは、イベントが存在するかどうかをチェックし、イベント プロシージャがデリゲート シグネチャと一致することを確認します。

COM イベントを除き、およびは **`__hook`** 、 **`__unhook`** イベントレシーバーの外部で呼び出すことができます。

を使用する代わりに、 **`__hook`** + = 演算子を使用することもできます。

新しい構文でのマネージイベントのコーディングの詳細については、「 [event](../extensions/event-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

サンプルについては、「[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)」および「 [COM でのイベント](../cpp/event-handling-in-com.md)処理」を参照してください。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[イベント処理](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)<br/>
