---
title: CRestrictions クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
ms.openlocfilehash: 4a4c86987ceff0f04986d32011ba941e0d2319fe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211303"
---
# <a name="crestrictions-class"></a>CRestrictions クラス

スキーマ行セットの制限を指定できるようにするジェネリッククラス。

## <a name="syntax"></a>構文

```cpp
template <class T, short nRestrictions, const GUID* pguid>
class CRestrictions :
   public CSchemaRowset <T, nRestrictions>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
アクセサーに使用されるクラス。

*nRestrictions*<br/>
スキーマ行セットの制限列の数。

*pguid*<br/>
スキーマの GUID へのポインター。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbsch

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[[ファイル]](#open)|ユーザーが指定した制限に従って結果セットを返します。|

## <a name="crestrictionsopen"></a><a name="open"></a>CRestrictions:: Open

ユーザーが指定した制限に従って結果セットを返します。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(const CSession& session,
   LPCTSTR lpszParam 1 = NULL,
   LPCTSTR lpszParam 2 = NULL,
   LPCTSTR lpszParam 3 = NULL,
   LPCTSTR lpszParam 4 = NULL,
   LPCTSTR lpszParam 5 = NULL,
   LPCTSTR lpszParam 6 = NULL,
   LPCTSTR lpszParam 7 = NULL,
   bool bBind = true);
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
からデータソースへの接続に使用する既存のセッションオブジェクトを指定します。

*lpszParam*<br/>
からスキーマ行セットの制限を指定します。

*bBind*<br/>
から列マップを自動的にバインドするかどうかを指定します。 既定値は**true**です。これにより、列マップが自動的にバインドされます。 *Bbind*を**false**に設定すると、手動でバインドできるように、列マップが自動的にバインドされなくなります。 (手動バインドは OLAP ユーザーにとって特に重要です)。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

スキーマ行セットに対して最大7つの制限を指定できます。

各スキーマ行セットに定義されている制限については、「 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)
