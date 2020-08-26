---
title: event_source (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
ms.openlocfilehash: bea90020c3ec570149e11db95ff6d6f8fd0a5507
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845303"
---
# <a name="event_source"></a>event_source

イベント ソースを作成します。

## <a name="syntax"></a>構文

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>パラメーター

*type*<br/>
次の値のいずれかの列挙です。

- アンマネージ C/C++ コード用の`native` (アンマネージ クラスの既定)。

- COM コード用の`com` 。 When を使用する必要があり `coclass` `type` = `com` ます。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
*型*がの場合は `native` 、を指定して `optimize=size` 、クラスのすべてのイベントに対して4バイト (最小) のストレージがあることを示すことができ `optimize=speed` ます。または (既定値) ストレージの 4 * (イベントの数) バイトがあることを示します。

*decorate*<br/>
*Type*がの場合は `native` 、を指定して `decorate=false` 、結合された (.mrg) ファイル内の拡張名に外側のクラス名を含めることができないことを示すことができます。 [/Fx](../../build/reference/fx-merge-injected-code.md) では、.mrg ファイルを生成できます。 `decorate=false`既定では、マージされたファイルには完全修飾型名が生成されます。

## <a name="remarks"></a>解説

**event_source** C++ 属性では、それが適用されているクラスまたは構造がイベント ソースとなることを指定します。

**event_source** は、 [event_receiver](event-receiver.md) 属性と [__event](../../cpp/event.md) キーワードと共に使用します。 `event_receiver`イベントレシーバーを作成するには、を使用します。 **`__event`** イベントソース内のメソッドでを使用して、これらのメソッドをイベントとして指定します。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|**コクラス**`type`=`com`|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[クラス属性](class-attributes.md)
