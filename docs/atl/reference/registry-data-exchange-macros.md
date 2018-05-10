---
title: レジストリ データ交換マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62a26e8d602010ce637114464a844d2f95e635c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="registry-data-exchange-macros"></a>レジストリ データ交換マクロ
これらのマクロは、レジストリ データの交換操作を実行します。  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|レジストリ データ エクス チェンジ マップの開始位置をマークします。|  
|[END_RDX_MAP](#end_rdx_map)|レジストリ データ エクス チェンジ マップの最後をマークします。|  
|[RDX_BINARY](#rdx_binary)|BYTE 型の指定したメンバー変数に指定したレジストリ エントリを関連付けます。|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定したレジストリ エントリを CString 型の指定したメンバー変数に関連付けます。|  
|[RDX_DWORD](#rdx_dword)|指定したレジストリ エントリを DWORD 型の指定したメンバー変数に関連付けます。|  
|[RDX_TEXT](#rdx_text)|TCHAR 型の指定したメンバー変数に指定したレジストリ エントリを関連付けます。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlplus.h  
   
##  <a name="begin_rdx_map"></a>  BEGIN_RDX_MAP  
 レジストリ データ エクス チェンジ マップの開始位置をマークします。  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>コメント  
 次のマクロは、システム レジストリのエントリを読み書きをレジストリ データ エクス チェンジ マップ内で使用されます。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|BYTE 型の指定したメンバー変数に指定したレジストリ エントリを関連付けます。|  
|[RDX_DWORD](#rdx_dword)|指定したレジストリ エントリを DWORD 型の指定したメンバー変数に関連付けます。|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定したレジストリ エントリを CString 型の指定したメンバー変数に関連付けます。|  
|[RDX_TEXT](#rdx_text)|TCHAR 型の指定したメンバー変数に指定したレジストリ エントリを関連付けます。|  
  
 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはで作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`コードがシステム レジストリの間でデータを交換する必要があるたびに、マクロを使用する必要があります、RDX マップで指定された変数です。  
  
##  <a name="end_rdx_map"></a>  END_RDX_MAP  
 レジストリ データ エクス チェンジ マップの最後をマークします。  
  
```
END_RDX_MAP
```  
  
##  <a name="rdx_binary"></a>  RDX_BINARY  
 BYTE 型の指定したメンバー変数に指定したレジストリ エントリを関連付けます。  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キー。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`にメンバー変数を指定されたレジストリ エントリに関連付けるマクロです。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはで作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して、システム レジストリとメンバー間のデータ交換を実行する必要がありますRDX マップ内の変数。  
  
##  <a name="rdx_cstring_text"></a>  RDX_CSTRING_TEXT  
 指定したレジストリ エントリを CString 型の指定したメンバー変数に関連付けます。  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キー。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`にメンバー変数を指定されたレジストリ エントリに関連付けるマクロです。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはで作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して、システム レジストリとメンバー間のデータ交換を実行する必要がありますRDX マップ内の変数。  
  
##  <a name="rdx_dword"></a>  RDX_DWORD  
 指定したレジストリ エントリを DWORD 型の指定したメンバー変数に関連付けます。  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キー。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`にメンバー変数を指定されたレジストリ エントリに関連付けるマクロです。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはで作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して、システム レジストリとメンバー間のデータ交換を実行する必要がありますRDX マップ内の変数。  
  
##  <a name="rdx_text"></a>  RDX_TEXT  
 TCHAR 型の指定したメンバー変数に指定したレジストリ エントリを関連付けます。  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キー。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`にメンバー変数を指定されたレジストリ エントリに関連付けるマクロです。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはで作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して、システム レジストリとメンバー間のデータ交換を実行する必要がありますRDX マップ内の変数。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)







