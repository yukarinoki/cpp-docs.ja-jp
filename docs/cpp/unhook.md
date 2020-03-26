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
ms.openlocfilehash: 2a259b80b941e37e0c3040ad55894c114fe4bc82
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160529"
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

**&** *Sourceclass* `::` *eventmethod*は、イベントハンドラーメソッドをアンフックするイベントメソッドへのポインターです。

- ネイティブC++イベント:*Sourceclass*はイベントソースクラスであり、 *eventmethod*はイベントです。

- COM イベント:*Sourceclass*はイベントソースインターフェイスであり、 *eventmethod*はそのメソッドの1つです。

- マネージイベント:*Sourceclass*はイベントソースクラスであり、 *eventmethod*はイベントです。

*interface*<br/>
[Event_receiver](../windows/attributes/event-receiver.md)属性の*layout_dependent*パラメーターが**true**である COM イベントレシーバーに対してのみ、*受信側*からアンフックされるインターフェイス名。

*source*<br/>
イベント ソースのインスタンスへのポインター。 `event_receiver`に指定されているコード `type` に応じて、 *source*には次のいずれかを指定できます。

- ネイティブ イベント ソース オブジェクト ポインター。

- `IUnknown`ベースのポインター (COM ソース)。

- マネージド オブジェクトのポインター (マネージド イベントの場合)。

**&** *receiverclass* `::`&、イベントからアンフックされるイベントハンドラーメソッドへのポインターを `HandlerMethod` します。 ハンドラーは、クラスのメソッドまたは同じに対する参照として指定されています。クラス名を指定しない場合、 **__unhook**は、クラスが呼び出されることを前提とします。

- ネイティブC++イベント:*Receiverclass*はイベントレシーバークラスであり、`HandlerMethod` はハンドラーです。

- COM イベント:*Receiverclass*はイベントレシーバーインターフェイスであり、`HandlerMethod` はそのハンドラーの1つです。

- マネージイベント:*Receiverclass*はイベントレシーバークラスであり、`HandlerMethod` はハンドラーです。

*レシーバー*(省略可能) イベントレシーバークラスのインスタンスへのポインター。 受信側を指定しない場合、既定値は **__unhook**が呼び出されるレシーバークラスまたは構造体です。

## <a name="usage"></a>使用方法

イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。

## <a name="remarks"></a>Remarks

イベントレシーバーで組み込み **__unhook**関数を使用して、イベントメソッドからのハンドラーメソッドを関連付け解除または "アンフック" します。

**__Unhook**には3つの形式があります。 ほとんどの場合、最初の形式 (引数が 4 つ) を使用できます。 2番目 (引数が2つ) の形式の **__unhook**は、COM イベントレシーバーに対してのみ使用できます。これにより、イベントインターフェイス全体がアンフックされます。 3 番目 (引数が 1 つ) の形式は、指定したソースからすべてのデリゲートをアンフックする場合に使用します。

ゼロ以外の戻り値は、エラーが発生したことを示します (マネージド イベントは例外をスローします)。

まだフックされていないイベントおよびイベントハンドラーに対して **__unhook**を呼び出すと、無効になります。

コンパイル時に、コンパイラはイベントが存在することを確認し、指定されたハンドラーを使用してパラメーターの型チェックを実行します。

COM イベントを除き、 **__hook**と **__unhook**は、イベントレシーバーの外部で呼び出すことができます。

**__Unhook**を使用する代わりに、-= 演算子を使用することもできます。

新しい構文でのマネージイベントのコーディングの詳細については、「 [event](../extensions/event-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

サンプルについては、「 [COM で](../cpp/event-handling-in-com.md)のネイティブ[ C++ ](../cpp/event-handling-in-native-cpp.md)およびイベント処理のイベント処理」を参照してください。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
