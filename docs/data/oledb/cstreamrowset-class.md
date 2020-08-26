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
ms.openlocfilehash: 304dfe0e026a9fbba899c1ef17c06cf1baf1529b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841052"
---
# <a name="cstreamrowset-class"></a>CStreamRowset クラス

`CCommand`宣言または宣言で使用 `CTable` します。

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

| 名前 | 説明 |
|-|-|
|[CStreamRowset](#cstreamrowset)|コンストラクターです。 オブジェクトをインスタンス化し、初期化し `CStreamRowset` ます。|
|[閉じる](#close)|クラスの [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) インターフェイスポインターを解放します。|

## <a name="remarks"></a>解説

`CStreamRowset`または宣言でを使用し `CCommand` `CTable` ます。次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

または

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute``ISequentialStream`に格納されているポインターを返し `m_spStream` ます。 次に、メソッドを使用し `Read` て、XML 形式の (Unicode 文字列) データを取得します。 次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 では XML の書式設定が実行され、すべての列と行セットのすべての行が1つの XML 文字列として返されます。

> [!NOTE]
> この機能は SQL Server 2000 でのみ機能します。

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a> CStreamRowset:: CStreamRowset

オブジェクトをインスタンス化し、初期化し `CStreamRowset` ます。

### <a name="syntax"></a>構文

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a> CStreamRowset:: Close

クラスの [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) インターフェイスポインターを解放します。

### <a name="syntax"></a>構文

```cpp
void Close();
```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
