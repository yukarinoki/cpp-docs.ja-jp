---
title: IConvertTypeImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IConvertTypeImpl class
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b9a8fdef3abf0c33fb6fca857086e6490ec959e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl クラス
実装を提供、 [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IConvertTypeImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[CanConvert](../../data/oledb/iconverttypeimpl-canconvert.md)|コマンドまたは行セットでは、型変換の可用性の情報を提供します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、コマンド、行セット、およびインデックス行セットでは必須です。 **IConvertTypeImpl** OLE DB で指定されている変換オブジェクトに委任することで、インターフェイスを実装します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)