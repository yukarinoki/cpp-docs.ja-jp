---
title: _ATL_FUNC_INFO 構造 |Microsoft ドキュメント
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
ms.openlocfilehash: fa81e83d353c542ea5b2b6e8e5e8fe32f7c57606
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
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
 **cc**  
 呼び出し規則 この構造体を使用する場合、[されます](../../atl/reference/idispeventsimpleimpl-class.md)このメンバーである必要がありますクラス、 **CC_STDCALL**です。 `CC_CDECL` Windows CE でサポートされる唯一のオプションは、`CALLCONV`のフィールド、`_ATL_FUNC_INFO`構造体。 その他の値はサポートされていないためその動作が定義されていません。  
  
 **vtReturn**  
 関数のバリアント型は、値を返します。  
  
 **nParams**  
 関数パラメーターの数。  
  
 **pVarTypes**  
 関数のパラメーターのバリアント型の配列。  
  
## <a name="remarks"></a>コメント  
 内部的には、ATL は、タイプ ライブラリから取得した情報を保持するためにこの構造を使用します。 使用するイベント ハンドラーの型情報を提供する場合は、この構造体を直接操作する必要があります、[されます](../../atl/reference/idispeventsimpleimpl-class.md)クラスと[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)マクロです。  
  
## <a name="example"></a>例  
 IDL で定義されたディスパッチ インターフェイス メソッドを指定します。  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 定義して、`_ATL_FUNC_INFO`構造体。  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
## <a name="see-also"></a>関連項目  
  [クラスと構造体](../../atl/reference/atl-classes.md)  
 [されますクラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





