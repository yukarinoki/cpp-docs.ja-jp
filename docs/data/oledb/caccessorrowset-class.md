---
description: '詳細情報: CAccessorRowset クラス'
title: CAccessorRowset クラス
ms.date: 11/04/2016
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
- CAccessorRowset.Bind
- CAccessorRowset::Bind
- CAccessorRowset::CAccessorRowset
- CAccessorRowset.CAccessorRowset
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
helpviewer_keywords:
- CAccessorRowset class
- CAccessorRowset class, methods
- CAccessorRowset class, members
- Bind method
- CAccessorRowset class, constructor
- Close method
- FreeRecordMemory method
- GetColumnInfo method
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
ms.openlocfilehash: c93580fa41967004947b075e82e00bdcb745ad4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307575"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset クラス

行セットとそれに関連付けられているアクセサーを1つのクラスにカプセル化します。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset>
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサークラス。

*TRowset*<br/>
行セットクラス。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|--|--|
| [束縛](#bind) | ( `bBind` が **`false`** [CCommand:: Open](./ccommand-class.md#open)のとして指定されている場合に使用される) バインドを作成します。 |
| [CAccessorRowset](#caccessorrowset) | コンストラクターです。 |
| [閉じる](#close) | 行セットと任意のアクセサーを閉じます。 |
| [FreeRecordMemory](#freerecordmemory) | 解放する必要がある現在のレコード内のすべての列を解放します。 |
| [GetColumnInfo](#getcolumninfo) | [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\))を実装します。 |

## <a name="remarks"></a>解説

クラス `TAccessor` は、アクセサーを管理します。 クラス *trowset* は、行セットを管理します。

## <a name="caccessorrowsetbind"></a><a name="bind"></a> CAccessorRowset:: Bind

`bBind` **`false`** [CCommand:: Open](./ccommand-class.md#open)でとしてを指定した場合、バインドを作成します。

### <a name="syntax"></a>構文

```cpp
HRESULT Bind();
```

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="caccessorrowsetcaccessorrowset"></a><a name="caccessorrowset"></a> CAccessorRowset:: CAccessorRowset

`CAccessorRowset` オブジェクトを初期化します。

### <a name="syntax"></a>構文

```cpp
CAccessorRowset();
```

## <a name="caccessorrowsetclose"></a><a name="close"></a> CAccessorRowset:: Close

アクティブなアクセサーと行セットを解放します。

### <a name="syntax"></a>構文

```cpp
void Close();
```

### <a name="remarks"></a>解説

関連付けられているメモリを解放します。

## <a name="caccessorrowsetfreerecordmemory"></a><a name="freerecordmemory"></a> CAccessorRowset:: FreeRecordMemory

解放する必要がある現在のレコード内のすべての列を解放します。

### <a name="syntax"></a>構文

```cpp
void FreeRecordMemory();
```

## <a name="caccessorrowsetgetcolumninfo"></a><a name="getcolumninfo"></a> CAccessorRowset:: GetColumnInfo

開かれた行セットから列情報を取得します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns,
   DBCOLUMNINFO** ppColumnInfo,
   LPOLESTR* ppStrings) const;

HRESULT GetColumnInfo(DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

ユーザーは、返された列情報と文字列バッファーを解放する必要があります。 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)を使用し、バインドをオーバーライドする必要がある場合は、このメソッドの2番目のバージョンを使用します。

詳細については、 *OLE DB プログラマーリファレンス* の「 [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
