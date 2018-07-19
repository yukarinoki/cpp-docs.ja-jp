---
title: _ATL_BASE_MODULE70 構造体 |Microsoft Docs
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
ms.openlocfilehash: d48d863cdbe8e5528824b3ffbad10e1117277e0c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885341"
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 構造体
ATL を使用するすべてのプロジェクトで使用されます。  
  
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
 `hInstance` (Exe または dll) は、このモジュールにします。  
  
 `m_hInstResource`  
 既定のインスタンスのリソース ハンドル。  
  
 `m_bNT5orWin98`  
 オペレーティング システムのバージョン情報。 ATL で内部的に使用  
  
 `dwAtlBuildVer`  
 ATL のバージョンが格納されます。 現在は 0x0700 です。  
  
 `pguidVer`  
 ATL の内部の GUID です。  
  
 `m_csResource`  
 アクセスを同期するため、`m_rgResourceInstance`配列。 ATL で内部的に使用  
  
 `m_rgResourceInstance`  
 ATL が対応であるすべてのリソース インスタンス内のリソースの検索に使用する配列。 ATL で内部的に使用  
  
## <a name="remarks"></a>Remarks  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) _ATL_BASE_MODULE70 の typedef として定義されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../../atl/reference/atl-classes.md)





