---
title: CDynamicStringAccessor クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessor class
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1b8888bdac7d605ce1832ef7074955fab4893b33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor クラス
データベース スキーマ (データベースの基になる構造) の知識があるない場合にデータ ソースにアクセスできます。  
  
## <a name="syntax"></a>構文  
  
```cpp
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|指定された列のデータを文字列として取得します。|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|文字列として指定された列のデータを設定します。|  
  
## <a name="remarks"></a>コメント  
 中に[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 、プロバイダーによって報告されたネイティブ形式でデータを要求`CDynamicStringAccessor`要求プロバイダーが文字列データとしてデータ ストアからアクセスされるすべてのデータをフェッチします。 これは、表示またはデータ ストアの内容を印刷するなど、データ ストア内の値の計算を必要としない単純なタスクに特に便利です。  
  
 データ ストア内の列データのネイティブな型がありませんでした。プロバイダーは、データ変換をサポートできますが、限りの文字列形式のデータが供給されます。 要求側の呼び出しが成功値を返す、プロバイダーが、ネイティブ データ型から文字列 (一般的ではありません) への変換をサポートしていない場合**DB_S_ERRORSOCCURED**、対応する列の状態が、変換問題がある**DBSTATUS_E_CANTCONVERTVALUE**です。  
  
 使用して`CDynamicStringAccessor`列情報を取得するメソッド。 実行時に動的にアクセサーを作成するのにには、この列の情報を使用します。  
  
 列の情報は、このクラスによって作成および管理のバッファーに格納されます。 使用して、バッファーからデータを取得[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)、またはを使用して、バッファーに格納[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)です。  
  
 ディスカッションと動的なアクセサー クラスを使用しての例では、次を参照してください。[動的アクセサーの使用](../../data/oledb/using-dynamic-accessors.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor クラス](../../data/oledb/cxmlaccessor-class.md)