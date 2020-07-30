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
ms.openlocfilehash: 35a80503597b7e59ec10618b9c8e18e0e69f018e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221511"
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
から派生したユーザーのクラス `CRowsetImpl` 。

*Storage*<br/>
ユーザーレコードクラス。

*CreatorClass*<br/>
行セットのプロパティを含むクラスです。通常はコマンドです。

*ArrayType*<br/>
行セットのデータのストレージとして機能するクラス。 このパラメーターの既定値はです `CAtlArray` が、必要な機能をサポートする任意のクラスを指定できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[NameFromDBID](#namefromdbid)|から文字列を抽出 `DBID` し、渡された*bstr*にコピーします。|
|[SetCommandText](#setcommandtext)|を検証し、 `DBID` 2 つの文字列 ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)および[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) に格納します。|

### <a name="overridable-methods"></a>オーバーライド可能なメソッド

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|特定のクライアント要求の列情報を取得します。|
|[GetCommandFromID](#getcommandfromid)|いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。存在する場合は、 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)のデータメンバーに文字列値をコピーし、 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)します。|
|[ValidateCommandID](#validatecommandid)|とのどちらか一方または両方に文字列値が含まれているかどうかを確認 `DBID` します。存在する場合は、データメンバー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)および[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)にコピーします。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_rgRowData](#rgrowdata)|既定では、 `CAtlArray` ユーザーレコードテンプレート引数を templatizes するがに設定さ `CRowsetImpl` れています。 別の配列型クラスは、テンプレート引数をに変更することによって使用でき `ArrayType` `CRowsetImpl` ます。|
|[m_strCommandText](#strcommandtext)|行セットの初期コマンドが含まれています。|
|[m_strIndexText](#strindextext)|行セットの初期インデックスが含まれています。|

## <a name="remarks"></a>解説

`CRowsetImpl`静的アップキャストの形式でオーバーライドを提供します。 メソッドは、指定された行セットがコマンドテキストを検証する方法を制御します。 `CRowsetImpl`実装インターフェイスを複数継承することで、独自のスタイルのクラスを作成できます。 実装を提供する必要があるメソッドは、だけです `Execute` 。 作成しようとしている行セットの種類によっては、の作成者メソッドでの異なるシグネチャが想定され `Execute` ます。 たとえば、派生クラスを使用して `CRowsetImpl` スキーマ行セットを実装している場合、 `Execute` メソッドは次のシグネチャを持ちます。

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

の派生クラスを作成して `CRowsetImpl` コマンドまたはセッションの行セットを実装する場合、 `Execute` メソッドのシグネチャは次のようになります。

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

の派生メソッドを実装するには、 `CRowsetImpl` `Execute` 内部データバッファー ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)) を設定する必要があります。

## <a name="crowsetimplnamefromdbid"></a><a name="namefromdbid"></a>CRowsetImpl:: NameFromDBID

から文字列を抽出 `DBID` し、渡された*bstr*にコピーします。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>パラメーター

*pDBID*<br/>
から文字列の抽出元のへのポインター `DBID` 。

*bstr*<br/>
から文字列のコピーを格納するための[CComBSTR](../../atl/reference/ccombstr-class.md)参照 `DBID` 。

*bIndex*<br/>
[入力] **`true`** インデックスの場合は、 `DBID` **`false`** テーブルの場合は `DBID` です。

### <a name="return-value"></a>戻り値

標準の HRESULT です。 `DBID`がテーブルとインデックスのどちらであるか ( *bindex*によって示されます) に応じて、メソッドは DB_E_NOINDEX または DB_E_NOTABLE を返します。

### <a name="remarks"></a>解説

このメソッドは、 `CRowsetImpl` [Validatecommandid](../../data/oledb/crowsetimpl-validatecommandid.md)と[getcommandfromid](../../data/oledb/crowsetimpl-getcommandfromid.md)の実装によって呼び出されます。

## <a name="crowsetimplsetcommandtext"></a><a name="setcommandtext"></a>CRowsetImpl:: SetCommandText

を検証し、 `DBID` 2 つの文字列 ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)および[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) に格納します。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>パラメーター

*pTableID*<br/>
からテーブル ID を表すへのポインター `DBID` 。

*pIndexID*<br/>
からインデックス ID を表すへのポインター `DBID` 。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

`SetCommentText`メソッドは `CreateRowset` 、の静的なテンプレート化メソッドで呼び出され `IOpenRowsetImpl` ます。

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
からユーザーの派生クラスへのポインター `CRowsetImpl` 。

*pcCols*<br/>
から返される列の数へのポインター (出力)。

### <a name="return-value"></a>戻り値

静的構造体へのポインター `ATLCOLUMNINFO` 。

### <a name="remarks"></a>解説

このメソッドは高度なオーバーライドです。

このメソッドは、特定のクライアント要求の列情報を取得するために、いくつかの基本実装クラスによって呼び出されます。 通常、このメソッドはによって呼び出され `IColumnsInfoImpl` ます。 このメソッドをオーバーライドする場合は、派生クラスにメソッドのバージョンを配置する必要があり `CRowsetImpl` ます。 メソッドは非テンプレート化クラスに配置される可能性があるため、 *pv*を適切な派生クラスに変更する必要があり `CRowsetImpl` ます。

使用法の例を次に示し `GetColumnInfo` ます。 この例で `CMyRowset` は、は `CRowsetImpl` から派生したクラスです。 `GetColumnInfo`このクラスのすべてのインスタンスに対してをオーバーライドするには、クラス定義に次のメソッドを配置し `CMyRowset` ます。

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
からテーブル ID を表すへのポインター `DBID` 。

*pIndexID*<br/>
からインデックス ID を表すへのポインター `DBID` 。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、によって静的なアップキャストを通じて呼び出され、 `CRowsetImpl` [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)データメンバーと[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)を設定します。 既定では、このメソッドは、いずれかまたは両方のパラメーターに文字列値が含まれているかどうかを確認します。 文字列値が含まれている場合、このメソッドは文字列値をデータメンバーにコピーします。 このシグネチャを持つメソッドをの派生クラスに配置すると `CRowsetImpl` 、基本実装ではなく、メソッドが呼び出されます。

## <a name="crowsetimplvalidatecommandid"></a><a name="validatecommandid"></a>CRowsetImpl:: ValidateCommandID

とのどちらか一方または両方に文字列値が含まれているかどうかを確認 `DBID` します。存在する場合は、データメンバー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)および[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)にコピーします。

### <a name="syntax"></a>構文

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>パラメーター

*pTableID*<br/>
からテーブル ID を表すへのポインター `DBID` 。

*pIndexID*<br/>
からインデックス ID を表すへのポインター `DBID` 。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

このメソッドは、 `CRowsetImpl` [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)のデータメンバーを設定するために、によって静的アップキャストによって呼び出されます。 既定では、このメソッドは、いずれかまたは両方のに文字列値が含まれているかどうかを確認 `DBID` し、存在する場合はそれらをデータメンバーにコピーします。 このシグネチャを持つメソッドをの派生クラスに配置すると `CRowsetImpl` 、基本実装ではなく、メソッドが呼び出されます。

## <a name="crowsetimplm_rgrowdata"></a><a name="rgrowdata"></a>CRowsetImpl:: m_rgRowData

既定では、 `CAtlArray` ユーザーレコードテンプレート引数を templatizes するがに設定さ `CRowsetImpl` れています。

### <a name="syntax"></a>構文

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>解説

*ArrayType*は、に対するテンプレートパラメーター `CRowsetImpl` です。

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
