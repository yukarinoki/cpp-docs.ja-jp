---
title: CDBPropIDSet クラス
ms.date: 11/04/2016
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
ms.openlocfilehash: a52d7443ab335e8546a4bcce03cf68c3b1d60e3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212027"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet クラス

`DBPROPIDSET` 構造体から継承し、キーフィールドと[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)アクセスメソッドを初期化するコンストラクターを追加します。

## <a name="syntax"></a>構文

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddPropertyID](#addpropertyid)|プロパティ ID セットにプロパティを追加します。|
|[CDBPropIDSet](#cdbpropidset)|コンストラクターです。|
|[SetGUID](#setguid)|プロパティ ID セットの GUID を設定します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator =](#op_equal)|あるプロパティ ID の内容を別のプロパティ ID に設定します。|

## <a name="remarks"></a>解説

OLE DB コンシューマーは、`DBPROPIDSET` 構造体を使用して、コンシューマーがプロパティ情報を取得するプロパティ Id の配列を渡します。 1つの[Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85))構造体で識別されるプロパティは、1つのプロパティセットに属します。

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a>CDBPropIDSet:: AddPropertyID

プロパティ id セットにプロパティ ID を追加します。

### <a name="syntax"></a>構文

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>パラメーター

*propid*<br/>
からプロパティ ID セットに追加するプロパティ ID。

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a>CDBPropIDSet:: CDBPropIDSet

コンストラクターです。 [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85))構造体の `rgProperties`、`cProperties`、および (必要に応じて) `guidPropertySet` フィールドを初期化します。

### <a name="syntax"></a>構文

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
から`guidPropertySet` フィールドを初期化するために使用される GUID。

*propidset*<br/>
からコピー構築用の別の `CDBPropIDSet` オブジェクト。

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a>CDBPropIDSet:: SetGUID

`DBPROPIDSET` 構造体の GUID フィールドを設定します。

### <a name="syntax"></a>構文

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
から[Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85))構造体の `guidPropertySet` フィールドを設定するために使用される GUID です。

### <a name="remarks"></a>解説

このフィールドは、[コンストラクター](../../data/oledb/cdbpropidset-cdbpropidset.md)でも設定できます。 このクラスの既定のコンストラクターを使用する場合は、この関数を呼び出します。

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a>CDBPropIDSet:: operator =

1つのプロパティ ID セットの内容を別の ID プロパティセットに割り当てます。

### <a name="syntax"></a>構文

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
