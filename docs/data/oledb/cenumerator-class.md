---
title: CEnumerator クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b7e390212da53f85cb50dd5bb151ea6740784b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cenumerator-class"></a>CEnumerator クラス
公開する OLE DB 列挙子オブジェクトを使用して、 [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx)インターフェイスをすべてのデータ ソースと列挙子を記述する行セットを返します。  
  
## <a name="syntax"></a>構文

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[検索](../../data/oledb/cenumerator-find.md)|指定した名前のいずれかを探して使用可能なプロバイダー (データ ソース) で検索します。|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|取得、`IMoniker`現在のレコードのインターフェイスです。|  
|[開く](../../data/oledb/cenumerator-open.md)|列挙子を開きます。|  
  
## <a name="remarks"></a>コメント  
 取得することができます、 **ISourcesRowset**このクラスから間接的にデータ。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)