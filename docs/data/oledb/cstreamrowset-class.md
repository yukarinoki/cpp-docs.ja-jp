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
ms.openlocfilehash: ad4987422fd200faef141150908d4df0722f669a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366273"
---
# <a name="cstreamrowset-class"></a>CStreamRowset クラス

宣言で使用`CCommand`します`CTable`。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>パラメーター

*Tアクセサー*<br/>
アクセサー クラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[Cストリームローセット](#cstreamrowset)|コンストラクターです。 `CStreamRowset`オブジェクトをインスタンス化して初期化します。|
|[閉じる](#close)|クラス内の[ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85))インターフェイス ポインターを解放します。|

## <a name="remarks"></a>解説

または宣言で使用`CStreamRowset``CTable``CCommand`します。

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

or

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute`に`ISequentialStream`格納されているポインターを返`m_spStream`します。 その後、この`Read`メソッドを使用して、(Unicode 文字列) データを XML 形式で取得します。 次に例を示します。

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 は XML 書式を実行し、行セットのすべての列と行を 1 つの XML 文字列として返します。

> [!NOTE]
> この機能は、SQL Server 2000 でのみ機能します。

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>Cストリームローセット::Cストリームローセット

`CStreamRowset`オブジェクトをインスタンス化して初期化します。

### <a name="syntax"></a>構文

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>Cストリームローセット::閉じる

クラス内の[ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85))インターフェイス ポインターを解放します。

### <a name="syntax"></a>構文

```cpp
void Close();
```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
