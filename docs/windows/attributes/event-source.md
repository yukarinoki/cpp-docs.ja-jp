---
title: event_source (C++ COM 属性)
description: Microsoft C++ extension COM 属性の使用方法について説明 `event_source` します。
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.openlocfilehash: 3cdfaaa86f8fc36bf0dc90d7961077546362a662
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483270"
---
# <a name="event_source-attribute"></a>`event_source` 属性

イベント ソースを作成します。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../../build/reference/permissive-standards-conformance.md) 。

## <a name="syntax"></a>構文

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>パラメーター

*`type`*\
次の値のいずれかの列挙です。

- アンマネージ C/C++ コード用の`native` (アンマネージ クラスの既定)。

- COM コード用の`com` 。 When を使用 `coclass` *`type`* = `com` します。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`optimize`*\
*型* がの場合は `native` 、を指定して `optimize=size` 、クラスのすべてのイベントに対して4バイトのストレージ (最小値) があることを示すことができ `optimize=speed` ます。または (既定値) ストレージの 4 * (# of イベント) バイトがあることを示します。

*`decorate`*\
*Type* がの場合は `native` 、を指定して、マージされた `decorate=false` () ファイル内の拡張名に外側のクラス名を含めることができないことを示すことができ *`.mrg`* ます。 [`/Fx`](../../build/reference/fx-merge-injected-code.md) では、ファイルを生成でき *`.mrg`* ます。 `decorate=false`既定では、マージされたファイルに完全修飾型名が生成されます。

## <a name="remarks"></a>注釈

C++ 属性は、それが適用される **`event_source`** クラスまたは構造体がイベントソースであることを指定します。

**`event_source`** は、属性とキーワードと組み合わせて使用され [`event_receiver`](event-receiver.md) [`__event`](../../cpp/event.md) ます。 `event_receiver`イベントレシーバーを作成するには、を使用します。 **`__event`** イベントソース内のメソッドでを使用して、これらのメソッドをイベントとして指定します。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|--|--|
| **適用対象** | **`class`**, **`struct`** |
| **Repeatable** | いいえ |
| **必須属性** | **`coclass`** いつ `type`=`com` |
| **無効な属性** | なし |

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)\
[`event_receiver`](event-receiver.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[クラス属性](class-attributes.md)
