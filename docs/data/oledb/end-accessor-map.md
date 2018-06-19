---
title: END_ACCESSOR_MAP |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- END_ACCESSOR_MAP
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR_MAP macro
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 647e581a86564221ad409caf9addd03ae3d11fb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101566"
---
# <a name="endaccessormap"></a>END_ACCESSOR_MAP
アクセサー マップ エントリの末尾をマークします。  
  
## <a name="syntax"></a>構文  
  
```cpp
END_ACCESSOR_MAP()  
  
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