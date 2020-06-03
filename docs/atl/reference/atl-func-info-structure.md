---
title: _ATL_FUNC_INFO 構造体
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: b1c740cf1a1ed344dbceb028bd1f39a87fc09363
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168593"
---
# <a name="_atl_func_info-structure"></a>_ATL_FUNC_INFO 構造体

ディスパッチインターフェイスのメソッドまたはプロパティを記述するために使用される型情報を格納します。

## <a name="syntax"></a>構文

```cpp
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>メンバー

`cc`<br/>
呼び出し規則 この構造体を[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)クラスで使用する場合は、このメンバーを CC_STDCALL する必要があります。 `CC_CDECL`は、 `CALLCONV` `_ATL_FUNC_INFO`構造体のフィールドの Windows CE でサポートされている唯一のオプションです。 その他の値はサポートされていないため、動作は定義されていません。

`vtReturn`<br/>
関数の戻り値のバリアント型。

`nParams`<br/>
関数パラメーターの数。

`pVarTypes`<br/>
関数パラメーターのバリアント型の配列。

## <a name="remarks"></a>解説

内部的には、ATL は、この構造体を使用して、タイプライブラリから取得された情報を保持します。 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)クラスおよび[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロで使用されるイベントハンドラーの型情報を指定する場合は、この構造体を直接操作する必要があります。

## <a name="example"></a>例

IDL で定義されているディスパッチインターフェイスメソッドがあるとします。

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

構造体は次`_ATL_FUNC_INFO`のように定義します。

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>必要条件

ヘッダー: atlcom.h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl クラス](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
