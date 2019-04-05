---
title: no_registry
ms.date: 10/18/2018
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: 2a0fd9a761f765aa9562ab18c095f683b80c7987
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023426"
---
# <a name="noregistry"></a>no_registry

**no_registry**レジストリにインポートされたタイプ ライブラリを検索しないようにコンパイラに指示`#import`します。

## <a name="syntax"></a>構文

```
#import filename no_registry
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
タイプ ライブラリ。

## <a name="remarks"></a>Remarks

参照されるタイプ ライブラリがインクルード ディレクトリで見つからない場合、タイプ ライブラリがレジストリである場合でも、コンパイルは失敗します。  **no_registry**で暗黙的にインポートされた他のタイプ ライブラリに伝達`auto_search`します。

ファイル名で指定され、`#import` に直接渡されるタイプ ライブラリの場合、コンパイラはレジストリを検索しません。

ときに`auto_search`が指定されている追加`#import`に s が生成されます、 **no_registry**の初期設定`#import`(場合初期`#import`ディレクティブが**no_registry**、 `auto_search`-生成された`#import`も**no_registry**)。

**no_registry**クロス コンパイラをレジストリ内のファイルの古いバージョンの検索のリスクを負うことがなく、参照されるタイプ ライブラリをインポートする場合に便利です。 **no_registry**もタイプ ライブラリが登録されていない場合に便利です。

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)