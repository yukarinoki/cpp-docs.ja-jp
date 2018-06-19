---
title: コンパイラ エラー C3672 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3672
dev_langs:
- C++
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aaea09d89c192a1820c2a384144ce758fde90476
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263948"
---
# <a name="compiler-error-c3672"></a>コンパイラ エラー C3672
擬似デストラクター式は、関数呼び出しの一部としてのみ使用できます。  
  
 デストラクターが正しく呼び出されませんでした。  詳細については、次を参照してください。[デストラクター](../../cpp/destructors-cpp.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3672 を生成します。  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```