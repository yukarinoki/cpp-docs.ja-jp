---
title: BEGIN_ACCESSOR |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_ACCESSOR
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ffb1d506a198586a5a625664f21c29954aada40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="beginaccessor"></a>BEGIN_ACCESSOR
アクセサーのエントリの先頭を示します。  
  
## <a name="syntax"></a>構文  
  
```  
BEGIN_ACCESSOR(num, bAuto)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *num*  
 [in]このアクセサー マップのアクセサーのゼロ オフセットの数です。  
  
 *bAuto*  
 [in]このアクセサーが自動アクセサーまたは手動のアクセサーを指定します。 場合**true**、アクセサーは自動; 場合**false**アクセサーは手動です。 自動アクセサーでは、移動操作でデータをフェッチすることを意味します。  
  
## <a name="remarks"></a>コメント  
 行セットで複数のアクセサーを指定する必要があります。`BEGIN_ACCESSOR_MAP`を使用して、`BEGIN_ACCESSOR`個々 のアクセサーに対してマクロです。 `BEGIN_ACCESSOR` マクロは `END_ACCESSOR` マクロで終了します。 `BEGIN_ACCESSOR_MAP`マクロが正常に完了しません、`END_ACCESSOR_MAP`マクロです。  
  
## <a name="example"></a>例  
 参照してください[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)