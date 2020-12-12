---
description: '詳細情報: CDynamicStringAccessorW クラス'
title: CDynamicStringAccessorW クラス
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 360a9592cdce3a1046eecb360a8691b1d8480caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170673"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW クラス

では、データベーススキーマ (基になる構造) に関する知識がない場合に、データソースにアクセスできます。

## <a name="syntax"></a>構文

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>解説

どちらの場合も、データストアからアクセスされるすべてのデータを文字列データとして取得するようにプロバイダーに要求しますが、 `CDynamicStringAccessor` Unicode 文字列データを要求します。

`CDynamicStringAccessorW``GetString`とを `SetString` 継承 `CDynamicStringAccessor` します。 オブジェクトでこれらのメソッドを使用する場合 `CDynamicStringAccessorW` 、 `BaseType` は **WCHAR** です。

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
