---
title: event_receiver (C++ COM 属性)
description: Microsoft C++ extension COM 属性の使用方法について説明 `event_receiver` します。
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.openlocfilehash: 8ed6ef6113d72a9565b275dff4e035dc56f11e82
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483283"
---
# <a name="event_receiver-attribute"></a>`event_receiver` 属性

イベント レシーバー (シンク) を作成します。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>構文

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>パラメーター

*`type`*\
次の値のいずれかの列挙です。

- `native` アンマネージ C/c + + コードの場合 (ネイティブクラスの場合は既定)。

- COM コード用の`com` 。 この値を使用するには、次のヘッダーファイルをインクルードする必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`layout_dependent`*\
*`layout_dependent`* Com の場合にのみ指定し `type` = **com** ます。 *`layout_dependent`* はブール値です。

- **`true`** は、イベントレシーバー内のデリゲートのシグネチャが、イベントソース内でフックされているデリゲートと完全に一致する必要があることを意味します。 イベントレシーバーハンドラー名は、関連するイベントソースインターフェイスで指定されている名前と一致している必要があります。 `coclass` *`layout_dependent`* がの場合は、を使用し **`true`** ます。 を指定する方が少し効率的 **`true`** です。

- **`false`** (既定値) は、呼び出し規約とストレージクラス ( `virtual` 、 `static` など) がイベントメソッドとハンドラーに一致する必要がないことを意味します。 ハンドラー名は、イベントソースインターフェイスのメソッド名と一致する必要もありません。

## <a name="remarks"></a>注釈

C++ 属性は、適用される **`event_receiver`** クラスまたは構造体が、Microsoft C++ の統合イベントモデルを使用してイベントレシーバーとなることを指定します。

**`event_receiver`** は、 [`event_source`](event-source.md) 属性とキーワードおよびキーワードと共に使用され [`__hook`](../../cpp/hook.md) [`__unhook`](../../cpp/unhook.md) ます。 `event_source`イベントソースを作成するには、を使用します。 イベントレシーバーのメソッド内でを使用して、イベントの **`__hook`** レシーバーメソッドをイベントソースのイベントに関連付けます。 **`__unhook`** これらの関連付けを解除するには、を使用します。

*`layout_dependent`* は、COM イベントレシーバー () に対してのみ指定され `type` = **`com`** ます。 の既定値 *`layout_dependent`* は **`false`** です。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|--|--|
| **適用対象** | **`class`**, **`struct`** |
| **Repeatable** | いいえ |
| **必須属性** | `coclass` いつ *`layout_dependent`*=**`true`** |
| **無効な属性** | なし |

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)\
[`event_source`](event-source.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[クラス属性](class-attributes.md)
