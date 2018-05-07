---
title: コンパイラ エラー C3101 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3101
dev_langs:
- C++
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8e10d3b22e7120789b9e1b6bb48fca097fcfddb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3101"></a>コンパイラ エラー C3101
名前付き属性引数 'field' 式が正しくありません。  
  
 名前付き属性引数を初期化するときに、値は、コンパイル時定数をする必要があります。  
  
 属性の詳細については、次を参照してください。[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3101 を生成します。  
  
```  
// C3101.cpp  
// compile with: /clr /c  
ref class AAttribute : System::Attribute {  
public:  
   int Field;  
};  
  
extern int i;  
  
[assembly:A(Field = i)];   // C3101  
[assembly:A(Field = 0)];   // OK  
```