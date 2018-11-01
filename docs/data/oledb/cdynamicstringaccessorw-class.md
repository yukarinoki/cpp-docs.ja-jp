---
title: CDynamicStringAccessorW クラス
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 7052a912363d1256294131da9b89df97f768ecf8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551360"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW クラス

データベース スキーマ (構造体の基になる) の知識があるない場合にデータ ソースにアクセスすることができます。

## <a name="syntax"></a>構文

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>Remarks

プロバイダーが、文字列データとしてデータ ストアからすべてのデータをフェッチすることを要求するには両方が`CDynamicStringAccessor`Unicode 文字列データを要求します。

`CDynamicStringAccessorW` 継承`GetString`と`SetString`から`CDynamicStringAccessor`します。 これらのメソッドを使用すると、`CDynamicStringAccessorW`オブジェクト、`BaseType`は**WCHAR**します。

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
