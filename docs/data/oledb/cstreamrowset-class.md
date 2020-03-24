---
title: CStreamRowset クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
ms.openlocfilehash: 300933fd6d10f5da39d9276db746ab789851a9a1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211173"
---
# <a name="cstreamrowset-class"></a>CStreamRowset クラス

`CCommand` または `CTable` の宣言で使用されます。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサークラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|コンストラクターです。 `CStreamRowset` オブジェクトをインスタンス化し、初期化します。|
|[[閉じる]](#close)|クラスの[ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85))インターフェイスポインターを解放します。|

## <a name="remarks"></a>解説

`CCommand` または `CTable` の宣言で `CStreamRowset` を使用します。次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

or

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute` は、`m_spStream`に格納されている `ISequentialStream` ポインターを返します。 次に、`Read` メソッドを使用して、XML 形式の (Unicode 文字列) データを取得します。 次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 では XML の書式設定が実行され、すべての列と行セットのすべての行が1つの XML 文字列として返されます。

> [!NOTE]
>  この機能は SQL Server 2000 でのみ機能します。

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset:: CStreamRowset

`CStreamRowset` オブジェクトをインスタンス化し、初期化します。

### <a name="syntax"></a>構文

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset:: Close

クラスの[ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85))インターフェイスポインターを解放します。

### <a name="syntax"></a>構文

```cpp
void Close();
```

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
