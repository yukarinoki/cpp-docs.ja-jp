---
title: CXMLAccessor クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 16ced0ce1d6c5531b7210231315f001cda4c0bc4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337214"
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor クラス
データ ストアのスキーマ (構造体の基になる) の知識があるない場合に文字列データとしてデータ ソースにアクセスすることができます。  
  
## <a name="syntax"></a>構文

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  

## <a name="requirements"></a>要件  
 **ヘッダー**: atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetXMLColumnData](#getxmlcolumndata)|列情報を取得します。|  
|[GetXMLRowData](#getxmlrowdata)|行がテーブルの内容全体を取得します。|  
  
## <a name="remarks"></a>Remarks  
 ただし、`CXMLAccessor`とは異なります`CDynamicStringAccessorW`を XML 形式のタグ付きデータとしてデータ ストアからすべてのデータに変換します。 これは、XML 対応の Web ページへの出力に特に便利です。 XML タグ名は、可能な限りデータ ストアの列名が一致されます。  
  
 使用`CDynamicAccessor`列情報を取得するメソッド。 実行時に動的にアクセサーを作成するのにには、この列の情報を使用します。  
  
 列の情報は、このクラスによって作成および管理のバッファーに格納されます。 列の情報を使用して取得[GetXMLColumnData](#getxmlcolumndata)を使用して行で列のデータを取得または[GetXMLRowData](#getxmlrowdata)します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  

## <a name="getxmlcolumndata"></a> Cxmlaccessor::getxmlcolumndata
列で、XML 形式の文字列データとして、テーブルの列の型情報を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *キャンセルします。*  
 [out]取得する列の型情報を含む文字列バッファーへの参照。 文字列には、データ ストアの列名に一致する XML タグ名が表示されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 列の型情報が XML で書式設定方法を次に示します。 `type` 列のデータ型を指定します。 データ型はなく、そのアクセスされていたデータベースの OLE DB データ型をに基づいてことに注意してください。  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>` 

## <a name="getxmlrowdata"></a> Cxmlaccessor::getxmlrowdata
行で、XML 形式の文字列データとして、テーブルの内容全体を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,   
   bool bAppend = false) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *キャンセルします。*  
 [out]取得するテーブルのデータを格納するバッファーへの参照。 データは、データ ストアの列名に一致する XML タグ名でデータを文字列として書式設定します。  
  
 *bAppend*  
 [in]出力データの末尾に文字列を追加するかどうかを示すブール値。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 行のデータが XML で書式設定方法を次に示します。 `DATA` 以下の行のデータを表します。 目的の行に移動するメソッドを使用してに移動します。  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`   
  
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