---
description: '詳細情報: CDynamicStringAccessorA クラス'
title: CDynamicStringAccessorA クラス
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: 45a4d10c8a50c4009151fa90e51172405047a21a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170725"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA クラス

では、データベーススキーマ (基になる構造) に関する知識がない場合に、データソースにアクセスできます。

## <a name="syntax"></a>構文

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>解説

両方とも、データストアからアクセスされるすべてのデータを文字列データとして取得するようにプロバイダーに要求しますが、 `CDynamicStringAccessor` ANSI 文字列データを要求します。

`CDynamicStringAccessorA``GetString`とを `SetString` 継承 `CDynamicStringAccessor` します。 オブジェクトでこれらのメソッドを使用する場合 `CDynamicStringAccessorA` 、 `BaseType` は **CHAR** です。

## <a name="requirements"></a>要件

**ヘッダー**: atldbcli. h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
