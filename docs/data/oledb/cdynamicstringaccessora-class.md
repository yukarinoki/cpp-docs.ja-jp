---
title: CDynamicStringAccessorA クラス
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: bfe4cf2d6aa107c21ed0d8b226616ebaa8488102
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537437"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA クラス

データベース スキーマ (構造体の基になる) の知識があるない場合にデータ ソースにアクセスすることができます。

## <a name="syntax"></a>構文

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>Remarks

プロバイダーが、文字列データとしてデータ ストアからすべてのデータをフェッチすることを要求するには両方が`CDynamicStringAccessor`要求 ANSI 文字列データ。

`CDynamicStringAccessorA` 継承`GetString`と`SetString`から`CDynamicStringAccessor`します。 これらのメソッドを使用すると、`CDynamicStringAccessorA`オブジェクト、`BaseType`は**CHAR**します。

## <a name="requirements"></a>必要条件

**ヘッダー**: atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
