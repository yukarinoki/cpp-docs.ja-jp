---
title: no_registry |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_registry
dev_langs:
- C++
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5a3089f71deb4e75aa50b634de84516575d1d02
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807745"
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