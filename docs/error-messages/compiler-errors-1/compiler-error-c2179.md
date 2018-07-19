---
title: コンパイラ エラー C2179 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2179
dev_langs:
- C++
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c12d7235cc146f080d74ffb09361dd691f7e1ba9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170334"
---
# <a name="compiler-error-c2179"></a>コンパイラ エラー C2179
'type': 属性引数は、型パラメーターを使用できません  
  
 ジェネリック型パラメーターは、実行時に解決します。 ただし、属性パラメーターは、コンパイル時に解決する必要があります。 そのため、属性の引数としてジェネリック型パラメーターを使うことはできません。  
  
## <a name="example"></a>例  
 次の例では、C2179 を生成します。  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```