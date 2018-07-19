---
title: Crowsetimpl::namefromdbid |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs:
- C++
helpviewer_keywords:
- NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 54ee345d4bf97c6f77398e62d1cb31614868a568
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097255"
---
# <a name="crowsetimplnamefromdbid"></a>CRowsetImpl::NameFromDBID
文字列を抽出、 **DBID**をコピーし、`bstr`で渡されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pDBID*  
 [in]ポインター、 **DBID**元となる文字列を抽出します。  
  
 `bstr`  
 [in]A [CComBSTR](../../atl/reference/ccombstr-class.md)のコピーを配置への参照、 **DBID**文字列。  
  
 `bIndex`  
 [in]**true**インデックスの場合**DBID**です。**false**テーブル**DBID**です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。 かどうかに応じて、 **DBID**がテーブルまたはインデックス (で示される`bIndex`)、メソッドはどちらの戻り値**DB_E_NOINDEX**または**DB_E_NOTABLE**です。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、`CRowsetImpl`の実装[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)と[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)