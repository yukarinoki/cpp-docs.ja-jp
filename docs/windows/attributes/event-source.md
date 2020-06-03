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
ms.openlocfilehash: e187e57f21e9c94068c0b3396b93deed617fef2a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167070"
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

- COM コード用の`com` 。 =`com``type`場合は、`coclass` を使用する必要があります。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
*Type*が `native`の場合、`optimize=size`を指定して、`optimize=speed` クラス内のすべてのイベントに対して4バイト (最小) のストレージがあることを示すことができます (既定)。ストレージの 4 * (イベントの数) バイトがあることを示します。

*decorate*<br/>
*Type*が `native`の場合、`decorate=false`を指定して、結合された (.mrg) ファイルの拡張名に外側のクラス名を含めないように指定できます。 [/Fx](../../build/reference/fx-merge-injected-code.md) では、.mrg ファイルを生成できます。 `decorate=false`(既定) の場合、マージされたファイルには完全修飾型名が生成されます。

## <a name="remarks"></a>解説

**event_source** C++ 属性では、それが適用されているクラスまたは構造がイベント ソースとなることを指定します。

**event_source** は、 [event_receiver](event-receiver.md) 属性と [__event](../../cpp/event.md) キーワードと共に使用します。 イベントレシーバーを作成するには、`event_receiver` を使用します。 イベントソース内のメソッドに **__event**を使用して、それらのメソッドをイベントとして指定します。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|`type`=場合の**コクラス**`com`|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[コンパイラ属性](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[クラス属性](class-attributes.md)
