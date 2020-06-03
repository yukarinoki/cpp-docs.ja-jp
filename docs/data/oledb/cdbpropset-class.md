---
title: CDBPropSet クラス
ms.date: 11/04/2016
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
- CDBPropSet.operator=
- ATL::CDBPropSet::operator=
- ATL.CDBPropSet.operator=
- CDBPropSet::operator=
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- CDBPropSet::SetGUID
helpviewer_keywords:
- CDBPropSet class
- AddProperty method
- CDBPropSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
- AddProperty method
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
ms.openlocfilehash: e2bb01e6acb9298b08fddc3117ec93dd7c0c2417
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212029"
---
# <a name="cdbpropset-class"></a>CDBPropSet クラス

`DBPROPSET` 構造体から継承し、キーフィールドと `AddProperty` アクセスメソッドを初期化するコンストラクターを追加します。

## <a name="syntax"></a>構文

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddProperty](#addproperty)|プロパティセットにプロパティを追加します。|
|[CDBPropSet](#cdbpropset)|コンストラクターです。|
|[SetGUID](#setguid)|`DBPROPSET` 構造の `guidPropertySet` フィールドを設定します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator =](#op_equal)|1つのプロパティセットの内容を別のプロパティに割り当てます。|

## <a name="remarks"></a>解説

OLE DB プロバイダーとコンシューマーは、`DBPROPSET` 構造体を使用して `DBPROP` 構造体の配列を渡します。 各 `DBPROP` 構造体は、設定できる1つのプロパティを表します。

## <a name="cdbpropsetaddproperty"></a><a name="addproperty"></a>CDBPropSet:: AddProperty

プロパティセットにプロパティを追加します。

### <a name="syntax"></a>構文

```cpp
bool AddProperty(DWORD dwPropertyID,
   constVARIANT& var,
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();
```

#### <a name="parameters"></a>パラメーター

*dwPropertyID*<br/>
から追加するプロパティの ID。 プロパティセットに追加された `DBPROP` 構造体の `dwPropertyID` を初期化するために使用します。

*var*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用されるバリアント。

*szValue*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用される文字列。

*bValue*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用する `BYTE` またはブール値。

*N 値*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用される整数値。

*fltValue*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用される浮動小数点値。

*dblValue*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用される倍精度浮動小数点値。

*cyValue*<br/>
からプロパティセットに追加された `DBPROP` 構造体のプロパティ値を初期化するために使用される CY の通貨値。

### <a name="return-value"></a>戻り値

プロパティが正常に追加された場合は**true** 。 それ以外の場合は、 **false**です。

## <a name="cdbpropsetcdbpropset"></a><a name="cdbpropset"></a>CDBPropSet:: CDBPropSet

コンストラクターです。 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の `rgProperties`、`cProperties`、および `guidPropertySet` の各フィールドを初期化します。

### <a name="syntax"></a>構文

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
から`guidPropertySet` フィールドを初期化するために使用される GUID。

*propset*<br/>
からコピー構築用の別の `CDBPropSet` オブジェクト。

## <a name="cdbpropsetsetguid"></a><a name="setguid"></a>CDBPropSet:: SetGUID

`DBPROPSET` 構造体の `guidPropertySet` フィールドを設定します。

### <a name="syntax"></a>構文

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
から[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の `guidPropertySet` フィールドを設定するために使用される GUID。

### <a name="remarks"></a>解説

このフィールドは、[コンストラクター](../../data/oledb/cdbpropset-cdbpropset.md)でも設定できます。

## <a name="cdbpropsetoperator-"></a><a name="op_equal"></a>CDBPropSet:: operator =

1つのプロパティセットの内容を別のプロパティセットに割り当てます。

### <a name="syntax"></a>構文

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)<br/>
[DBPROPSET 構造](/previous-versions/windows/desktop/ms714367(v=vs.85))体
[DBPROP 構造体](/previous-versions/windows/desktop/ms717970(v=vs.85))
