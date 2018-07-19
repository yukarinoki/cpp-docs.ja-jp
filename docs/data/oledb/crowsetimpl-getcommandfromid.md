---
title: Crowsetimpl::getcommandfromid |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f79e9287bf8d546ba5007257899a6b6ddc27ad40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091295"
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
いずれかまたは両方のパラメーターには、文字列値が含まれている場合を確認するためのチェックは、データ メンバーに文字列値をコピー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pTableID`  
 [in]ポインター、 **DBID**テーブルの ID を表す  
  
 `pIndexID`  
 [in]ポインター、 **DBID**インデックスの ID を表す  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、静的キャスト`CRowsetImpl`データ メンバーを設定する[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。 既定では、このメソッドは、いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。 文字列値を含まれている場合、このメソッドは、データ メンバーに文字列値をコピーします。 このシグネチャを持つメソッドを配置することによって、 `CRowsetImpl`-派生クラスでは、基底の実装ではなく、メソッドが呼び出されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)