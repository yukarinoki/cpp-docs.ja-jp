---
title: コンパイラ エラー C2847 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd18d685649c5ad8f03e3fdbb8b375717227f4c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2847"></a>コンパイラ エラー C2847
マネージ型または WinRT 型の 'class' に対して sizeof を使用できません  
  
 [Sizeof](../../cpp/sizeof-operator.md)演算子は、コンパイル時にオブジェクトの値を取得します。 マネージまたは WinRT のクラス、インターフェイス、または値型のサイズは、動的であるため、コンパイル時に確定できません。  
  
 たとえば、次の例では C2847 が生成されます。  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  
