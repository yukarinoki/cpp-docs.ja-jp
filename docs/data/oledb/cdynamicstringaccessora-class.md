---
title: CDynamicStringAccessorA クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e56f71a427fda2444992cc0ed2c3b6166993af1d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341024"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA クラス
データベース スキーマ (構造体の基になる) の知識があるない場合にデータ ソースにアクセスすることができます。  
  
## <a name="syntax"></a>構文

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Remarks  
 プロバイダーが、文字列データとしてデータ ストアからすべてのデータをフェッチすることを要求するには両方が`CDynamicStringAccessor`要求 ANSI 文字列データ。  
  
 `CDynamicStringAccessorA` 継承`GetString`と`SetString`から`CDynamicStringAccessor`します。 これらのメソッドを使用すると、`CDynamicStringAccessorA`オブジェクト、 ***BaseType***は**CHAR**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)