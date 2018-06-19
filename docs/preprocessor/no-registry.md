---
title: no_registry |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 416663592f4362c110637fb4d4b4b418d9776cde
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849666"
---
# <a name="noregistry"></a>no_registry
`no_registry` は、`#import` でインポートされたタイプ ライブラリをレジストリで検索しないようコンパイラに指示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ファイル名*  
 タイプ ライブラリ。  
  
## <a name="remarks"></a>コメント  
 インクルード ディレクトリの参照されたタイプ ライブラリが見つからない場合は、タイプ ライブラリがレジストリにある場合、コンパイルは失敗します。  `no_registry` 暗黙的に、インポートは他のタイプ ライブラリに反映される`auto_search`です。  
  
 ファイル名で指定され、`#import` に直接渡されるタイプ ライブラリの場合、コンパイラはレジストリを検索しません。  
  
 `auto_search` を指定すると、追加の `#import` が、初期 `no_registry` の `#import` 設定で生成されます (初期 `#import` ディレクティブが `no_registry` であった場合は、`auto_search` で生成される `#import` も `no_registry`)。  
  
 `no_registry` レジストリでファイルの古いバージョンを検索するコンパイラのリスクなし間の参照されるタイプ ライブラリをインポートする場合に便利です。  `no_registry` タイプ ライブラリが登録されていない場合に便利です。  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)