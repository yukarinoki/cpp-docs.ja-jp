---
title: CRowsetImpl クラス
ms.date: 11/04/2016
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
- CRowsetImpl::m_strCommandText
- CRowsetImpl.m_strCommandText
- CRowsetImpl::m_strIndexText
- CRowsetImpl.m_strIndexText
helpviewer_keywords:
- CRowsetImpl class
- NameFromDBID method
- SetCommandText method
- GetColumnInfo method
- GetCommandFromID method
- ValidateCommandID method
- m_rgRowData
- m_strCommandText
- m_strIndexText
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
ms.openlocfilehash: 97a79dee826dfba4b42053bbeba8c65e4d2b429c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211186"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl クラス

多くの実装インターフェイスを多重継承せずに、標準の OLE DB 行セットの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <
   class T,
   class Storage,
   class CreatorClass,
   class ArrayType = CAtlArray<Storage>,
   class RowClass = CSimpleRow,
   class RowsetInterface = IRowsetImpl <T, IRowset>
>
class CRowsetImpl :
   public CComObjectRootEx<CreatorClass::_ThreadModel>,
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`CRowsetImpl`から派生したユーザーのクラス。

*Storage*<br/>
ユーザーレコードクラス。

*CreatorClass*<br/>
行セットのプロパティを含むクラスです。通常はコマンドです。

*ArrayType*<br/>
行セットのデータのストレージとして機能するクラス。 このパラメーターの既定値は `CAtlArray`ですが、必要な機能をサポートする任意のクラスを指定できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[NameFromDBID](#namefromdbid)|`DBID` から文字列を抽出し、渡された*bstr*にコピーします。|
|[SetCommandText](#setcommandtext)|2つの文字列 ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) 内の `DBID`s を検証して格納します。|

### <a name="overridable-methods"></a>オーバーライド可能なメソッド

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|特定のクライアント要求の列情報を取得します。|
|[GetCommandFromID](#getcommandfromid)|いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。存在する場合は、 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)のデータメンバーに文字列値をコピーし、 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)します。|
|[ValidateCommandID](#validatecommandid)|`DBID`のいずれかまたは両方に文字列値が含まれているかどうかを確認し、存在する場合は、そのデータメンバー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)にコピーします。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_rgRowData](#rgrowdata)|既定では、ユーザーレコードテンプレート引数を templatizes して `CRowsetImpl`する `CAtlArray` です。 別の配列型クラスは、`ArrayType` テンプレート引数を `CRowsetImpl`に変更することによって使用できます。|
|[m_strCommandText](#strcommandtext)|行セットの初期コマンドが含まれています。|
|[m_strIndexText](#strindextext)|行セットの初期インデックスが含まれています。|

## <a name="remarks"></a>解説

`CRowsetImpl` は、静的なアップキャストの形式でオーバーライドを提供します。 メソッドは、指定された行セットがコマンドテキストを検証する方法を制御します。 実装インターフェイスを複数継承することで、独自の `CRowsetImpl`スタイルクラスを作成できます。 実装を提供する必要があるメソッドは `Execute`だけです。 作成しようとしている行セットの種類によっては、creator メソッドでは `Execute`に対して異なるシグネチャが想定されます。 たとえば、`CRowsetImpl`派生クラスを使用してスキーマ行セットを実装している場合、`Execute` メソッドのシグネチャは次のようになります。

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

コマンドまたはセッションの行セットを実装するために `CRowsetImpl`派生クラスを作成する場合、`Execute` メソッドのシグネチャは次のようになります。

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

`CRowsetImpl`派生 `Execute` メソッドのいずれかを実装するには、内部データバッファー ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)) を設定する必要があります。

## <a name="crowsetimplnamefromdbid"></a><a name="namefromdbid"></a>CRowsetImpl:: NameFromDBID

`DBID` から文字列を抽出し、渡された*bstr*にコピーします。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>パラメーター

*pDBID*<br/>
から文字列の抽出元の `DBID` へのポインター。

*bstr*<br/>
から`DBID` 文字列のコピーを格納するための[CComBSTR](../../atl/reference/ccombstr-class.md)参照。

*bIndex*<br/>
からインデックス `DBID`の場合は**true**を返します。テーブル `DBID`場合は**false** 。

### <a name="return-value"></a>戻り値

標準の HRESULT です。 `DBID` がテーブルとインデックスのどちらであるか ( *Bindex*によって示されます) に応じて、メソッドは DB_E_NOINDEX または DB_E_NOTABLE を返します。

### <a name="remarks"></a>解説

このメソッドは、 [Validatecommandid](../../data/oledb/crowsetimpl-validatecommandid.md)および[Getcommandfromid](../../data/oledb/crowsetimpl-getcommandfromid.md)の `CRowsetImpl` 実装によって呼び出されます。

## <a name="crowsetimplsetcommandtext"></a><a name="setcommandtext"></a>CRowsetImpl:: SetCommandText

2つの文字列 ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) 内の `DBID`s を検証して格納します。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>パラメーター

*pTableID*<br/>
からテーブル ID を表す `DBID` へのポインター。

*pIndexID*<br/>
からインデックス ID を表す `DBID` へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

`SetCommentText` メソッドは、`IOpenRowsetImpl`の静的なテンプレート化メソッド `CreateRowset`によって呼び出されます。

このメソッドは、 [Upecommandid](../../data/oledb/crowsetimpl-validatecommandid.md)と[Getcommandfromid](../../data/oledb/crowsetimpl-getcommandfromid.md)をアップキャストポインターで呼び出して、その作業を委任します。

## <a name="crowsetimplgetcolumninfo"></a><a name="getcolumninfo"></a>CRowsetImpl:: GetColumnInfo

特定のクライアント要求の列情報を取得します。

### <a name="syntax"></a>構文

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>パラメーター

*pv*<br/>
からユーザーの `CRowsetImpl` 派生クラスへのポインター。

*pcCols*<br/>
から返される列の数へのポインター (出力)。

### <a name="return-value"></a>戻り値

静的な `ATLCOLUMNINFO` 構造体へのポインター。

### <a name="remarks"></a>解説

このメソッドは高度なオーバーライドです。

このメソッドは、特定のクライアント要求の列情報を取得するために、いくつかの基本実装クラスによって呼び出されます。 通常、このメソッドは `IColumnsInfoImpl`によって呼び出されます。 このメソッドをオーバーライドする場合は、`CRowsetImpl`派生クラスにメソッドのバージョンを配置する必要があります。 メソッドは非テンプレート化クラスに配置される可能性があるため、 *pv*を適切な `CRowsetImpl`派生クラスに変更する必要があります。

次の例は `GetColumnInfo` 使用方法を示しています。 この例では、`CMyRowset` は `CRowsetImpl`派生クラスです。 このクラスのすべてのインスタンスに対して `GetColumnInfo` をオーバーライドするには、次のメソッドを `CMyRowset` クラス定義に配置します。

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="crowsetimplgetcommandfromid"></a><a name="getcommandfromid"></a>CRowsetImpl:: GetCommandFromID

いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。存在する場合は、 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)のデータメンバーに文字列値をコピーし、 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)します。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>パラメーター

*pTableID*<br/>
からテーブル ID を表す `DBID` へのポインター。

*pIndexID*<br/>
からインデックス ID を表す `DBID` へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、`CRowsetImpl` によって静的なアップキャストを通じて呼び出され、データメンバー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)を設定します。 既定では、このメソッドは、いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。 文字列値が含まれている場合、このメソッドは文字列値をデータメンバーにコピーします。 このシグネチャを持つメソッドを `CRowsetImpl`派生クラスに配置すると、基本実装ではなく、メソッドが呼び出されます。

## <a name="crowsetimplvalidatecommandid"></a><a name="validatecommandid"></a>CRowsetImpl:: ValidateCommandID

`DBID`のいずれかまたは両方に文字列値が含まれているかどうかを確認し、存在する場合は、そのデータメンバー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)にコピーします。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>パラメーター

*pTableID*<br/>
からテーブル ID を表す `DBID` へのポインター。

*pIndexID*<br/>
からインデックス ID を表す `DBID` へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、`CRowsetImpl` によって静的なアップキャストを通じて呼び出され、そのデータメンバー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)を設定します。 既定では、このメソッドは `DBID`s に文字列値が含まれているかどうかを確認し、存在する場合はそれらをデータメンバーにコピーします。 このシグネチャを持つメソッドを `CRowsetImpl`派生クラスに配置すると、基本実装ではなく、メソッドが呼び出されます。

## <a name="crowsetimplm_rgrowdata"></a><a name="rgrowdata"></a>CRowsetImpl:: m_rgRowData

既定では、ユーザーレコードテンプレート引数を templatizes して `CRowsetImpl`する `CAtlArray` です。

### <a name="syntax"></a>構文

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>解説

*ArrayType*は、`CRowsetImpl`するテンプレートパラメーターです。

## <a name="crowsetimplm_strcommandtext"></a><a name="strcommandtext"></a>CRowsetImpl:: m_strCommandText

行セットの初期コマンドが含まれています。

### <a name="syntax"></a>構文

```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;
```

## <a name="crowsetimplm_strindextext"></a><a name="strindextext"></a>CRowsetImpl:: m_strIndexText

行セットの初期インデックスが含まれています。

### <a name="syntax"></a>構文

```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;
```
