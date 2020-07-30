---
title: CEnumerator クラス
ms.date: 11/04/2016
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
ms.openlocfilehash: 2a48acb8a961d76c34d2ba85ede5c827c880f400
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214920"
---
# <a name="cenumerator-class"></a>CEnumerator クラス

OLE DB 列挙子オブジェクトを使用します。このオブジェクトは、すべてのデータソースと列挙子を記述する行セットを返す[isourcesrowset を](/previous-versions/windows/desktop/ms715969(v=vs.85))インターフェイスを公開します。

## <a name="syntax"></a>構文

```cpp
class CEnumerator :
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[Find](#find)|使用可能なプロバイダー (データソース) を検索し、指定した名前のプロバイダーを探します。|
|[GetMoniker](#getmoniker)|`IMoniker`現在のレコードのインターフェイスを取得します。|
|[[ファイル]](#open)|列挙子を開きます。|

## <a name="remarks"></a>解説

`ISourcesRowset`このクラスから間接的にデータを取得できます。

## <a name="cenumeratorfind"></a><a name="find"></a>CEnumerator:: Find

使用可能なプロバイダー間で指定された名前を検索します。

### <a name="syntax"></a>構文

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>パラメーター

*szSearchName*<br/>
から検索する名前。

### <a name="return-value"></a>戻り値

**`true`** 名前が見つかった場合は。 それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この名前は、 `SOURCES_NAME` [isourcesrowset を](/previous-versions/windows/desktop/ms715969(v=vs.85))インターフェイスのメンバーにマップされます。

## <a name="cenumeratorgetmoniker"></a><a name="getmoniker"></a>CEnumerator:: GetMoniker

モニカーに変換できる文字列のコンポーネントを抽出するために、表示名を解析します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();

HRESULT GetMoniker(LPMONIKER* ppMoniker,
   LPCTSTR lpszDisplayName) const throw();
```

#### <a name="parameters"></a>パラメーター

*ppMoniker*<br/>
入出力現在の行の表示名 ([CEnumeratorAccessor:: m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) から解析されたモニカー。

*lpszDisplayName*<br/>
から解析する表示名。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cenumeratoropen"></a><a name="open"></a>CEnumerator:: Open

列挙子のモニカーが指定されている場合は、そのモニカーをバインドしてから、 [isourcesrowset を:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85))を呼び出して列挙子の行セットを取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>パラメーター

*pMoniker*<br/>
から列挙子のモニカーを指すポインターです。

*pClsid*<br/>
から`CLSID`列挙子のへのポインターです。

*子*<br/>
から列挙子への参照です。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="see-also"></a>関連項目

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
