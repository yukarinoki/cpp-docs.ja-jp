---
title: _ATL_FUNC_INFO 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac285921500107b85c30eba4d2f1940c93721d0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113059"
---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO 構造体

ディスパッチ インターフェイスでメソッドまたはプロパティを記述するために使用する型情報が含まれています。

## <a name="syntax"></a>構文

```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>メンバー

`cc`<br/>
呼び出し規則 この構造体を使用する場合、 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)クラスでは、このメンバーは CC_STDCALL である必要があります。 `CC_CDECL` Windows CE でサポートされている唯一のオプションは、`CALLCONV`のフィールド、`_ATL_FUNC_INFO`構造体。 その他の値はサポートされていませんので、動作が定義されていません。

`vtReturn`<br/>
関数のバリアント型は、値を返します。

`nParams`<br/>
関数のパラメーターの数。

`pVarTypes`<br/>
関数のパラメーターのバリアント型の配列。

## <a name="remarks"></a>Remarks

内部的には、ATL は、タイプ ライブラリから取得した情報を保持するためにこの構造体を使用します。 型情報を使用するイベント ハンドラーを指定する場合は、この構造体を直接操作する必要があります、 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)クラスと[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロ。

## <a name="example"></a>例

IDL で定義されたディスパッチ インターフェイス メソッドを指定します。

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

定義して、`_ATL_FUNC_INFO`構造体。

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>要件

ヘッダー: atlcom.h

## <a name="see-also"></a>関連項目

[クラスと構造体](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl クラス](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)

