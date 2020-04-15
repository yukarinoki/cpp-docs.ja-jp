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
ms.openlocfilehash: 221ffc30a9b8a40c44f8009dfa511b72aa160e01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337561"
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

**&** イベント ハンドラー*メソッド*をアンフックするイベント メソッドへのポインター。 *SourceClass* `::`

- ネイティブ C++ イベント: *SourceClass*はイベント ソース クラスであり、*イベント メソッド*はイベントです。

- COM イベント: *SourceClass*はイベント ソース インターフェイスであり、*イベント メソッド*はそのメソッドの 1 つです。

- マネージ イベント: *SourceClass*はイベント ソース クラスで、*イベント メソッド*はイベントです。

*interface*<br/>
event_receiver[属性の](../windows/attributes/event-receiver.md)*layout_dependent*パラメータが**true**である COM イベント レシーバーの場合のみ *、receiver*からフック解除されるインターフェイス名。

*ソース*<br/>
イベント ソースのインスタンスへのポインター。 で`event_receiver`指定したコード`type`に応じて *、source*は次のいずれかになります。

- ネイティブ イベント ソース オブジェクト ポインター。

- ベース`IUnknown`ポインタ (COM ソース)。

- マネージド オブジェクトのポインター (マネージド イベントの場合)。

**&** イベントからフック解除されるイベント ハンドラー メソッドへの*ReceiverClass* `::` `HandlerMethod` A ポインター。 ハンドラーは、クラスのメソッドまたは同じメソッドへの参照として指定されます。クラス名を指定しない場合 **、__unhook**はクラスが呼び出されるクラスであると見なします。

- ネイティブ C++ イベント: *ReceiverClass*はイベント`HandlerMethod`レシーバー クラスであり、ハンドラーです。

- COM イベント: *ReceiverClass*はイベント`HandlerMethod`レシーバー インターフェイスであり、そのハンドラーの 1 つです。

- マネージ イベント: *ReceiverClass*はイベント`HandlerMethod`レシーバー クラスであり、ハンドラーです。

*receiver*(オプション) イベント レシーバー クラスのインスタンスへのポインター。 レシーバーを指定しない場合、デフォルトは **、__unhook**が呼び出されるレシーバー・クラスまたはレシーバー・ストラクチャーです。

## <a name="usage"></a>使用法

イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。

## <a name="remarks"></a>解説

イベント レシーバーの組み込み関数 **__unhook**を使用して、イベント メソッドからハンドラー メソッドの関連付けを解除または "アンフック" します。

**__unhook**には 3 つの形式があります。 ほとんどの場合、最初の形式 (引数が 4 つ) を使用できます。 2 番目の (2 つの引数) 形式の **__unhook**は、COM イベント レシーバーに対してのみ使用できます。これにより、イベント インターフェイス全体がアンフックされます。 3 番目 (引数が 1 つ) の形式は、指定したソースからすべてのデリゲートをアンフックする場合に使用します。

ゼロ以外の戻り値は、エラーが発生したことを示します (マネージド イベントは例外をスローします)。

__unhook**をフックされていない**イベントおよびイベント ハンドラーで呼び出しても、そのイベント ハンドラーは無効になります。

コンパイル時に、コンパイラはイベントが存在することを確認し、指定されたハンドラーを使用してパラメーターの型チェックを実行します。

COM イベントを除き **、__hook**と **__unhook**はイベント レシーバーの外部で呼び出すことができます。

**__unhook**を使用する代わりに、-= 演算子を使用する方法があります。

新しい構文でのマネージ イベントのコーディングについては、「[イベント](../extensions/event-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="example"></a>例

サンプルについては、「[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)」および[「COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
