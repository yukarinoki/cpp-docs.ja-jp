---
title: event_receiver |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d30ac0d2e1d18b22c6130212503576f5fe343a8d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407544"
---
# <a name="eventreceiver"></a>event_receiver

イベント レシーバー (シンク) を作成します。

## <a name="syntax"></a>構文

```cpp
[ event_receiver(
   type
   [, layout_dependent=false]
) ]
```

### <a name="parameters"></a>パラメーター

*type*<br/>
次の値のいずれかの列挙です。

- `native` アンマネージ C/C++ コード (ネイティブ クラスの既定値)。

- COM コード用の`com` 。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
指定*layout_dependent*場合にのみ`type` = **com**します。 *layout_dependent*ブール値です。

- **true**ことに、受信する必要がありますと正確に一致するが、フック イベント ソース、イベント、デリゲートのシグネチャを意味します。 イベント レシーバーのハンドラー名は、関連するイベント ソース インターフェイスで指定された名前と一致する必要があります。 使用する必要があります`coclass`とき*layout_dependent*は**true**します。 指定するより効率的です**true**します。

- **false** (既定値) を意味する呼び出し規約とストレージ クラス (virtual、static、およびその他の) イベント メソッドとハンドラー; に一致する必要はありませんもハンドラー名は行うイベント ソース インターフェイスのメソッド名に一致する必要があります。

## <a name="remarks"></a>Remarks

**Event_receiver** C++ 属性は、クラスまたは構造体を適用するによって Visual C の統一イベント モデルを使用して、イベント レシーバーがなることを指定します。

**event_receiver**を併用、 [event_source](../windows/event-source.md)属性と[_ _hook](../cpp/hook.md)と[_ _unhook](../cpp/unhook.md)キーワード。 使用`event_source`イベント ソースを作成します。 使用 **_ _hook**にイベント ソースのイベントをイベント レシーバー メソッドを (「フック」) を関連付けるイベント レシーバーのメソッド内で。 使用 **_ _unhook**の関連付けを解除しています。

*layout_dependent* COM イベント レシーバーのみ指定 (`type`=**com**)。 既定の*layout_dependent*は**false**します。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|`coclass` ときに*layout_dependent*=**は true。**|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](../windows/compiler-attributes.md)<br/>
[event_source](../windows/event-source.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[クラス属性](../windows/class-attributes.md)  