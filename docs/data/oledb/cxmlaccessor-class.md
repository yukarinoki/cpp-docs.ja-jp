---
title: CXMLAccessor クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
ms.openlocfilehash: 36419e85554982d1c3784d0d73663b48cc820b6d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845628"
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor クラス

では、データストアのスキーマ (基になる構造) に関する知識がない場合に、データソースに文字列データとしてアクセスできます。

## <a name="syntax"></a>構文

```cpp
class CXMLAccessor : public CDynamicStringAccessorW
```

## <a name="requirements"></a>必要条件

**ヘッダー**: atldbcli. h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[GetXMLColumnData](#getxmlcolumndata)|列情報を取得します。|
|[GetXMLRowData](#getxmlrowdata)|行ごとにテーブルの内容全体を取得します。|

## <a name="remarks"></a>解説

ただし、は、 `CXMLAccessor` `CDynamicStringAccessorW` データストアからアクセスされるすべてのデータを XML 形式の (タグ付けされた) データとして変換する点が異なります。 これは、XML 対応の Web ページに出力する場合に特に便利です。 XML タグ名は、データストアの列名とできるだけ一致します。

`CDynamicAccessor`列情報を取得するには、メソッドを使用します。 この列情報は、実行時にアクセサーを動的に作成するために使用します。

列情報は、このクラスによって作成および管理されるバッファーに格納されます。 [Getxmlcolumndata](#getxmlcolumndata)を使用して列情報を取得するか、 [GetXMLRowData](#getxmlrowdata)を使用して列データを行ごとに取得します。

## <a name="example"></a>例

[!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]

## <a name="cxmlaccessorgetxmlcolumndata"></a><a name="getxmlcolumndata"></a> CXMLAccessor:: GetXMLColumnData

列によって、テーブルの列の型情報を XML 形式の文字列データとして取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();
```

#### <a name="parameters"></a>パラメーター

*strOutput*<br/>
入出力取得する列の型情報を格納している文字列バッファーへの参照。 文字列は、データストアの列名と一致する XML タグ名で書式設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

次に、列の型情報が XML 形式でどのように書式設定されるかを示します。 `type` 列のデータ型を指定します。 データ型は、アクセスされるデータベースのデータ型ではなく、OLE DB のデータ型に基づいていることに注意してください。

`<columninfo>`

`<column type = I2/> ColumnName`

`</columninfo>`

## <a name="cxmlaccessorgetxmlrowdata"></a><a name="getxmlrowdata"></a> CXMLAccessor:: GetXMLRowData

テーブルの内容全体を XML 形式の文字列データとして行単位で取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,
   bool bAppend = false) throw();
```

#### <a name="parameters"></a>パラメーター

*strOutput*<br/>
入出力取得するテーブルデータを格納しているバッファーへの参照。 データは、データストアの列名と一致する XML タグ名を持つ文字列データとして書式設定されます。

*bAppend*<br/>
から出力データの末尾に文字列を追加するかどうかを指定するブール値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

次に、行データが XML 形式でどのように書式設定されるかを示します。 `DATA` 行データを次に示します。 目的の行に移動するには、move メソッドを使用します。

`<row>`

`<column name>DATA</column name>`

`</row>`

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)
