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
ms.openlocfilehash: 4de218188326dad434c5b0d355a3a15d39bb576c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502502"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet クラス

は `DBPROPIDSET` 構造体から継承し、キーフィールドと [AddPropertyID](#addpropertyid) アクセスメソッドを初期化するコンストラクターを追加します。

## <a name="syntax"></a>構文

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[AddPropertyID](#addpropertyid)|プロパティ ID セットにプロパティを追加します。|
|[CDBPropIDSet](#cdbpropidset)|コンストラクターです。|
|[SetGUID](#setguid)|プロパティ ID セットの GUID を設定します。|

### <a name="operators"></a>オペレーター

| 名前 | 説明 |
|-|-|
|[operator =](#op_equal)|あるプロパティ ID の内容を別のプロパティ ID に設定します。|

## <a name="remarks"></a>注釈

OLE DB コンシューマー `DBPROPIDSET` は、構造体を使用して、コンシューマーがプロパティ情報を取得するプロパティ id の配列を渡します。 1つの [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85)) 構造体で識別されるプロパティは、1つのプロパティセットに属します。

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a> CDBPropIDSet:: AddPropertyID

プロパティ id セットにプロパティ ID を追加します。

### <a name="syntax"></a>構文

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>パラメーター

*propid*<br/>
からプロパティ ID セットに追加するプロパティ ID。

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a> CDBPropIDSet:: CDBPropIDSet

コンストラクターです。 `rgProperties` `cProperties` `guidPropertySet` [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85))構造体の、、および (オプションで) フィールドを初期化します。

### <a name="syntax"></a>構文

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
からフィールドを初期化するために使用される GUID `guidPropertySet` 。

*propidset*<br/>
から `CDBPropIDSet` コピー構築用の別のオブジェクト。

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a> CDBPropIDSet:: SetGUID

構造体の GUID フィールドを設定し `DBPROPIDSET` ます。

### <a name="syntax"></a>構文

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
から `guidPropertySet` [Dbpropidset](/previous-versions/windows/desktop/ms717981(v=vs.85)) 構造体のフィールドを設定するために使用される GUID です。

### <a name="remarks"></a>注釈

このフィールドは、 [コンストラクター](#cdbpropidset) でも設定できます。 このクラスの既定のコンストラクターを使用する場合は、この関数を呼び出します。

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a> CDBPropIDSet:: operator =

1つのプロパティ ID セットの内容を別の ID プロパティセットに割り当てます。

### <a name="syntax"></a>構文

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
