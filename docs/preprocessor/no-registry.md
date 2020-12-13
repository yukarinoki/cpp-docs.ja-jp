---
description: 詳細については、「no_registry import 属性」を参照してください。
title: no_registry インポート属性
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: fa33bf8096a92ec248b0a9d56e39fcc82f433206
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333307"
---
# <a name="no_registry-import-attribute"></a>no_registry インポート属性

**no_registry** は、でインポートされたタイプライブラリのレジストリを検索しないようコンパイラに指示 `#import` します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **no_registry**

### <a name="parameters"></a>パラメーター

*タイプライブラリ*\
タイプ ライブラリ。

## <a name="remarks"></a>解説

参照されるタイプライブラリがインクルードディレクトリに見つからない場合は、タイプライブラリがレジストリに存在する場合でも、コンパイルは失敗します。  **no_registry** は、によって暗黙的にインポートされる他のタイプライブラリに伝達さ `auto_search` れます。

コンパイラは、ファイル名で指定され、に直接渡されるタイプライブラリのレジストリを検索しません `#import` 。

を `auto_search` 指定すると、 `#import` 初期の **no_registry** 設定を使用して、追加のディレクティブが生成され `#import` ます。 最初の `#import` ディレクティブが **no_registry** された場合、が生成された `auto_search` `#import` も **no_registry** ます。

**no_registry** は、クロス参照型ライブラリをインポートする場合に便利です。 これにより、コンパイラはレジストリで古いバージョンのファイルを検索できません。 **no_registry** は、タイプライブラリが登録されていない場合にも役立ちます。

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
