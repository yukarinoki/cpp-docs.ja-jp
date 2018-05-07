---
title: END_ACCESSOR |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- END_ACCESSOR
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f7bab52df0ed05886933a3df827fae5198651b39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="endaccessor"></a>END_ACCESSOR
アクセサーのエントリの終了を示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
END_ACCESSOR()  
  
```  
  
## <a name="remarks"></a>コメント  
 行セットで複数のアクセサーを指定する必要があります。`BEGIN_ACCESSOR_MAP`を使用して、`BEGIN_ACCESSOR`個々 のアクセサーに対してマクロです。 `BEGIN_ACCESSOR` マクロは `END_ACCESSOR` マクロで終了します。 `BEGIN_ACCESSOR_MAP`マクロが正常に完了しません、`END_ACCESSOR_MAP`マクロです。  
  
## <a name="example"></a>例  
 参照してください[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)