---
title: CTable クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
ms.openlocfilehash: a967ef8fa2832afd56442ae4f988ba080d0b2872
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845641"
---
# <a name="ctable-class"></a>CTable クラス

単純な行セット (パラメーターなし) に直接アクセスする手段を提供します。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor,
            template <typename T> class TRowset = CRowset>
class CTable :
   public CAccessorRowset <TAccessor, TRowset>
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサークラス。

*TRowset*<br/>
行セットクラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[[ファイル]](#open)|テーブルを開きます。|

## <a name="remarks"></a>解説

行セットにアクセスするコマンドを実行する方法については、「 [CCommand](../../data/oledb/ccommand-class.md) 」を参照してください。

## <a name="ctableopen"></a><a name="open"></a> CTable:: Open

テーブルを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   LPCSTR szTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   DBID& dbid,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
からテーブルが開かれているセッション。

*wszTableName*<br/>
から開くテーブルの名前。 Unicode 文字列として渡されます。

*szTableName*<br/>
から開くテーブルの名前。 ANSI 文字列として渡されます。

*dbid*<br/>
から `DBID` 開くテーブルの。

*pPropSet*<br/>
から設定するプロパティと値を格納している [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列へのポインター。 Windows SDK の*OLE DB プログラマーリファレンス*の「[プロパティセットとプロパティグループ](/previous-versions/windows/desktop/ms713696(v=vs.85))」を参照してください。 既定値の NULL はプロパティを指定しません。

*ulPropSets*<br/>
から*PPropSet*引数で渡される[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の数。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

詳細については、 *OLE DB プログラマーリファレンス*の「 [IOpenRowset:: OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
