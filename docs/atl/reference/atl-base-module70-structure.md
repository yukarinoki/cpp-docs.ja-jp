---
title: _ATL_BASE_MODULE70 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 484fc4a68d0421cb12e901b2d56f30e95f6cb79b
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 構造体
ATL を使用する他のプロジェクトで使用されます。  
  
## <a name="syntax"></a>構文  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バージョン管理に使用される、構造のサイズ。  
  
 `m_hInst`  
 **HInstance**このモジュール (exe または dll) です。  
  
 `m_hInstResource`  
 既定のインスタンスのリソース ハンドル。  
  
 **m_bNT5orWin98**  
 オペレーティング システムのバージョン情報です。 ATL で内部的に使用  
  
 **dwAtlBuildVer**  
 ATL のバージョンを格納します。 現在は 0x0700 です。  
  
 **pguidVer**  
 ATL の内部の GUID です。  
  
 **m_csResource**  
 アクセスを同期するために使用される、 **m_rgResourceInstance**配列。 ATL で内部的に使用  
  
 **m_rgResourceInstance**  
 ATL が対応であるすべてのリソース インスタンスのリソースを検索するために使用する配列。 ATL で内部的に使用  
  
## <a name="remarks"></a>コメント  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)の typedef として定義された`_ATL_BASE_MODULE70`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../../atl/reference/atl-classes.md)





