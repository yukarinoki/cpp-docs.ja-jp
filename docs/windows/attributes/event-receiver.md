---
title: event_receiver (C++ COM 属性)
ms.date: 10/02/2018
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
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
ms.openlocfilehash: 7280729a9ae3a054468e1f11bdcc4a563b32effe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845290"
---
# <a name="event_receiver"></a>event_receiver

イベント レシーバー (シンク) を作成します。

## <a name="syntax"></a>構文

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>パラメーター

*type*<br/>
次の値のいずれかの列挙です。

- `native` アンマネージ C/c + + コードの場合 (ネイティブクラスの場合は既定)。

- COM コード用の`com` 。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Com の場合にのみ*layout_dependent*を指定し `type` = **com**ます。 *layout_dependent* はブール型です。

- **`true`** は、イベントレシーバー内のデリゲートのシグネチャが、イベントソースでフックされるデリゲートと完全に一致する必要があることを意味します。 イベントレシーバーハンドラー名は、関連するイベントソースインターフェイスで指定されている名前と一致している必要があります。 `coclass` *Layout_dependent*がの場合は、を使用する必要があり **`true`** ます。 を指定する方が少し効率的です **`true`** 。

- **`false`** (既定値) は、呼び出し規約とストレージクラス (virtual、static など) がイベントメソッドとハンドラーに一致する必要がないことを意味します。また、ハンドラー名は、イベントソースインターフェイスのメソッド名と一致する必要があります。

## <a name="remarks"></a>解説

**Event_receiver** C++ 属性は、Visual C++ 統合イベントモデルを使用して、適用先のクラスまたは構造体がイベントレシーバーであることを指定します。

**event_receiver** は、 [event_source](event-source.md) 属性および [__hook](../../cpp/hook.md) および [__unhook](../../cpp/unhook.md) キーワードと共に使用されます。 `event_source`イベントソースを作成するには、を使用します。 イベントレシーバーのメソッド内でを使用して、イベントの **`__hook`** レシーバーメソッドをイベントソースのイベントに関連付けます。 これらの関連付け **`__unhook`** を解除するには、を使用します。

*layout_dependent*は com イベントレシーバー (com) に対してのみ指定され `type` = **com**ます。 *Layout_dependent*の既定値は **`false`** です。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|`coclass`*layout_dependent*時=**`true`**|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[クラス属性](class-attributes.md)
