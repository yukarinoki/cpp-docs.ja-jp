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
ms.openlocfilehash: 9653a0b5c756857d92914496b9c5c6f8aee56ebb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167083"
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

- アンマネージ C/C++ code (ネイティブクラスの既定値) の `native`。

- COM コード用の`com` 。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
**Com**=`type`場合にのみ、 *layout_dependent*を指定します。 *layout_dependent*はブール型です。

- **true**は、イベントレシーバー内のデリゲートのシグネチャが、イベントソースでフックされているデリゲートと完全に一致する必要があることを意味します。 イベントレシーバーハンドラー名は、関連するイベントソースインターフェイスで指定されている名前と一致している必要があります。 *Layout_dependent*が**true**の場合は、`coclass` を使用する必要があります。 **True**を指定すると、もう少し効率的になります。

- **false** (既定値) は、呼び出し規約とストレージクラス (virtual、static など) がイベントメソッドとハンドラーに一致する必要がないことを意味します。また、ハンドラー名は、イベントソースインターフェイスのメソッド名と一致する必要があります。

## <a name="remarks"></a>解説

**Event_receiver** C++属性は、ビジュアルC++統合イベントモデルを使用して、適用されるクラスまたは構造体がイベントレシーバーになることを指定します。

**event_receiver**は、 [event_source](event-source.md)属性および[__hook](../../cpp/hook.md)および[__unhook](../../cpp/unhook.md)キーワードと共に使用されます。 イベントソースを作成するには、`event_source` を使用します。 イベントレシーバーのメソッド内で **__hook**を使用して、イベントレシーバーメソッドをイベントソースのイベントに関連付けます ("フック")。 これらの関連付けを解除するには、 **__unhook**を使用します。

*layout_dependent*は、com イベントレシーバー (`type`=**com**) に対してのみ指定されます。 *Layout_dependent*の既定値は**false**です。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|*layout_dependent*=**true**の場合に `coclass`|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[コンパイラ属性](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[クラス属性](class-attributes.md)
