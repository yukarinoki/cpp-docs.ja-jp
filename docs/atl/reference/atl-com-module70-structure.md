---
title: _ATL_COM_MODULE70 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d78165481c8f2e9d8bba33ad14ebd0794f04fde
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70 構造体
ATL で COM に関連するコードで使用されます。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```  
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バージョン管理に使用される、構造のサイズ。  
  
 `m_hInstTypeLib`  
 このモジュールのタイプ ライブラリへのハンドルのインスタンス。  
  
 **m_ppAutoObjMapFirst**  
 このモジュールのオブジェクトのマップ エントリの先頭を示す、配列要素のアドレスです。  
  
 **m_ppAutoObjMapLast**  
 このモジュールのオブジェクトのマップ エントリの終了を示す、配列要素のアドレスです。  
  
 `m_csObjMap`  
 オブジェクト マップ エントリへのアクセスをシリアル化するクリティカル セクション。 ATL で内部的に使用  
  
## <a name="remarks"></a>コメント  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)の typedef として定義された`_ATL_COM_MODULE70`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../../atl/reference/atl-classes.md)





