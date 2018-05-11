---
title: embedded_idl |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0b594952e8e5be0a9be9c843877c8c4bb95eca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="embeddedidl"></a>embedded_idl
**C 固有の仕様**  
  
 属性が生成されたコードを保持して、タイプ ライブラリを .tlh ファイルに書き込むことを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
embedded_idl[("param")]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `param`  
 次の 2 つの値のいずれかを指定します。  
  
-   emitidl: typelib からインポートされた情報は、属性付きプロジェクト用に生成された IDL に存在します。  これは既定値であり、`embedded_idl` にパラメーターを指定しない場合に有効になります。  
  
-   no_emitidl: typelib からインポートされた型情報が、属性付きプロジェクト用に生成された IDL に存在しません。  
  
## <a name="example"></a>例  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>コメント  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)