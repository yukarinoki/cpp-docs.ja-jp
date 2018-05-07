---
title: 致命的なエラー C1191 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1191
dev_langs:
- C++
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf700db0e415fd7886cd8ba845f06a2d8f6c3249
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1191"></a>致命的なエラー C1191
'dll' はグローバル スコープでのみインポートできます。  
  
 /Clr プログラミングを使用するプログラムに mscorlib.dll をインポートする命令は、名前空間または関数では使用できませんが、グローバル スコープで表示する必要があります。  
  
 次の例では、C1191 が生成されます。  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 考えられる解決方法:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```