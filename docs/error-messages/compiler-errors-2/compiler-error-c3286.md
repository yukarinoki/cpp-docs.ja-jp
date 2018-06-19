---
title: コンパイラ エラー C3286 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc47c103e93fe1e4f20f5007c6688b5b6648bf32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248184"
---
# <a name="compiler-error-c3286"></a>コンパイラ エラー C3286  
  
> '*指定子*': 繰り返し変数は、ストレージ クラス指定子を持つことはできません  
  
ストレージ クラスは、反復変数では指定できません。 詳細については、次を参照してください。[ストレージ クラス (C++)](../../cpp/storage-classes-cpp.md)と[ごとに、で](../../dotnet/for-each-in.md)です。  
  
## <a name="example"></a>例  
  
次の例では、C3286 を生成し、正しい使用法も示しています。  
  
```cpp  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```