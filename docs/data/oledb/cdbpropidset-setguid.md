---
title: Cdbpropidset::setguid |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87878b6cc7ae38f2c9ffcf597a56ab020d8e9c8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090327"
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
GUID フィールドを設定、**コンス トラクターは**構造体。  
  
## <a name="syntax"></a>構文  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]設定に使用される GUID、**コンス トラクターは**のフィールド、[コンス トラクターは](https://msdn.microsoft.com/en-us/library/ms717981.aspx)構造体。  
  
## <a name="remarks"></a>コメント  
 このフィールドを設定することができます、[コンス トラクター](../../data/oledb/cdbpropidset-cdbpropidset.md)もします。 このクラスの既定のコンス トラクターを使用する場合は、この関数を呼び出します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)