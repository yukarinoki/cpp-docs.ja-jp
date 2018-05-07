---
title: CXMLAccessor クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 916e9dbe4e142192e4e716f57f97d5bd6865c709
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor クラス
データ ストアのスキーマ (構造体の基になる) の知識があるない場合に文字列データとしてデータ ソースにアクセスできます。  
  
## <a name="syntax"></a>構文

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|列情報を取得します。|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|行で、テーブルの内容全体を取得します。|  
  
## <a name="remarks"></a>コメント  
 ただし、`CXMLAccessor`とは異なります`CDynamicStringAccessorW`を XML 形式のタグ付きデータとしてデータ ストアからすべてのデータに変換します。 これは、XML 対応の Web ページへの出力に特に便利です。 XML タグ名は、データ ストアの列名をできるだけ一致されます。  
  
 使用して`CDynamicAccessor`列情報を取得するメソッド。 実行時に動的にアクセサーを作成するのにには、この列の情報を使用します。  
  
 列の情報は、このクラスによって作成および管理のバッファーに格納されます。 列情報を使用して取得[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)を使用して行で列のデータを取得または[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)です。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)