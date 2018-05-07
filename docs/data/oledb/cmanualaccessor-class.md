---
title: CManualAccessor クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7b8efc46971b1aa72f8c5e572aa540bfed250d2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmanualaccessor-class"></a>CManualAccessor クラス
高度な用途用に設計されたアクセサーの種類を表します。  
  
## <a name="syntax"></a>構文

```cpp
class CManualAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|出力列にバインド エントリを追加します。|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|パラメーターのアクセサーにパラメーターの入力を追加します。|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|列バインド構造体のメモリを割り当て、列のデータ メンバーを初期化します。|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|パラメーター バインド構造体のメモリを割り当て、パラメーターのデータ メンバーを初期化します。|  
  
## <a name="remarks"></a>コメント  
 使用して`CManualAccessor`実行時の関数の呼び出しによって出力される列のバインドと、パラメーターを指定できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)