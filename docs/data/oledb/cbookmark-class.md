---
title: CBookmark クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
dev_langs:
- C++
helpviewer_keywords:
- CBookmark class
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c14fde6fb07a35ef9e2955ce61f991bede6b11a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094752"
---
# <a name="cbookmark-class"></a>CBookmark クラス
バッファーには、ブックマークの値を保持します。  
  
## <a name="syntax"></a>構文

```cpp
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase
  
template <>  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nSize`  
 ブックマーク バッファーのバイト単位のサイズ。 ときに`nSize`0 の場合は、ブックマークのバッファーは実行時に動的に作成されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|コンス トラクター|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|バッファーへのポインターを取得します。|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|バッファーのバイト単位のサイズを取得します。|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|ブックマークの値を設定します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../../data/oledb/cbookmark-operator-equal.md)|1 つ割り当てます`CBookmark`を別のクラスです。|  
  
## <a name="remarks"></a>コメント  
 **CBookmark\<0 >** テンプレート特殊化`CBookmark`; そのバッファーは実行時に動的に作成します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)