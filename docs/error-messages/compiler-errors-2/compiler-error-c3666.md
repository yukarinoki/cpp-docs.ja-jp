---
title: コンパイラ エラー C3666 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3666
dev_langs:
- C++
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4672cad0f1c0b67b58233c6394e98324a9c32aaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3666"></a>コンパイラ エラー C3666
'constructor': オーバーライド指定子 'キーワード' コンス トラクターでは使用できません  
  
 オーバーライド指定子が、コンス トラクターで使用されは許可されていません。 詳細については、次を参照してください。[オーバーライド指定子を](../../windows/override-specifiers-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3666 を生成します。  
  
```  
// C3666.cpp  
// compile with: /clr /c  
ref struct R {  
   R() new {}   // C3666  
   R(int i) {}   // OK  
};  
```