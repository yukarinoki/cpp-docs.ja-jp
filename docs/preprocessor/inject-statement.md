---
title: inject_statement |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 115f5b3d7012ae3e9073d81e0c1005dcb513e045
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="injectstatement"></a>inject_statement
**C 固有の仕様**  
  
 タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。  
  
## <a name="syntax"></a>構文  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `source_text`  
 タイプ ライブラリ ヘッダー ファイルに挿入するソース テキスト。  
  
## <a name="remarks"></a>コメント  
 テキストは、ヘッダー ファイルのタイプ ライブラリの内容をラップする名前空間宣言の先頭に配置されます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)