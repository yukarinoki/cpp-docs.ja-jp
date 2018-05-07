---
title: Iconverttypeimpl::canconvert |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs:
- C++
helpviewer_keywords:
- CanConvert method
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2f7e32fd01c932f24b617951d601ddcfe7fb5af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="iconverttypeimplcanconvert"></a>IConvertTypeImpl::CanConvert
コマンドまたは行セットでは、型変換の可用性の情報を提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(CanConvert)(DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 OLE DB データ変換を使用して`MSADC.DLL`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IConvertTypeImpl クラス](../../data/oledb/iconverttypeimpl-class.md)