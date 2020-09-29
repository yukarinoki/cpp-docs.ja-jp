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
ms.openlocfilehash: 45772896cac520eba35ec475f8b6ae7bd2993045
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502465"
---
# <a name="cdbpropset-class"></a>CDBPropSet クラス

は `DBPROPSET` 構造体から継承し、キーフィールドおよびアクセスメソッドを初期化するコンストラクターを追加し `AddProperty` ます。

## <a name="syntax"></a>構文

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[AddProperty](#addproperty)|プロパティセットにプロパティを追加します。|
|[CDBPropSet](#cdbpropset)|コンストラクターです。|
|[SetGUID](#setguid)|`guidPropertySet`構造体のフィールドを設定 `DBPROPSET` します。|

### <a name="operators"></a>オペレーター

| 名前 | 説明 |
|-|-|
|[operator =](#op_equal)|1つのプロパティセットの内容を別のプロパティに割り当てます。|

## <a name="remarks"></a>注釈

OLE DB プロバイダーとコンシューマーは、構造体を使用して `DBPROPSET` 構造体の配列を渡し `DBPROP` ます。 各 `DBPROP` 構造体は、設定できる1つのプロパティを表します。

## <a name="cdbpropsetaddproperty"></a><a name="addproperty"></a> CDBPropSet:: AddProperty

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
から追加するプロパティの ID。 `dwPropertyID` `DBPROP` プロパティセットに追加された構造体のを初期化するために使用します。

*var*<br/>
から `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用されるバリアント。

*szValue*<br/>
から `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用される文字列。

*bValue*<br/>
から `BYTE` `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用されるまたはブール値。

*N 値*<br/>
から `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用される整数値。

*fltValue*<br/>
から `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用される浮動小数点値。

*dblValue*<br/>
から `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用される倍精度浮動小数点値。

*cyValue*<br/>
から `DBPROP` プロパティセットに追加された構造体のプロパティ値を初期化するために使用される CY の通貨値。

### <a name="return-value"></a>戻り値

**`true`** プロパティが正常に追加された場合は。 それ以外の場合は **`false`** 。

## <a name="cdbpropsetcdbpropset"></a><a name="cdbpropset"></a> CDBPropSet:: CDBPropSet

コンストラクターです。 `rgProperties` `cProperties` `guidPropertySet` [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の、、およびの各フィールドを初期化します。

### <a name="syntax"></a>構文

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
からフィールドを初期化するために使用される GUID `guidPropertySet` 。

*propset*<br/>
から `CDBPropSet` コピー構築用の別のオブジェクト。

## <a name="cdbpropsetsetguid"></a><a name="setguid"></a> CDBPropSet:: SetGUID

`guidPropertySet`構造体のフィールドを設定 `DBPROPSET` します。

### <a name="syntax"></a>構文

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>パラメーター

*guid*<br/>
から `guidPropertySet` [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体のフィールドを設定するために使用される GUID。

### <a name="remarks"></a>注釈

このフィールドは、 [コンストラクター](#cdbpropset) でも設定できます。

## <a name="cdbpropsetoperator-"></a><a name="op_equal"></a> CDBPropSet:: operator =

1つのプロパティセットの内容を別のプロパティセットに割り当てます。

### <a name="syntax"></a>構文

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)<br/>
[DBPROPSET 構造体](/previous-versions/windows/desktop/ms714367(v=vs.85)) 
[DBPROP 構造体](/previous-versions/windows/desktop/ms717970(v=vs.85))
