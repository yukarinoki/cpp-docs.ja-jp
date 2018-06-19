---
title: コンパイラ エラー C3622 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8c7ab18bfba899c2df41becb457ed2e7725f81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33260093"
---
# <a name="compiler-error-c3622"></a>コンパイラ エラー C3622
'class': 宣言されたクラスを 'keyword' をインスタンス化することはできません  
  
としてマークされたクラスのインスタンスを作成しようとしました[抽象](../../windows/abstract-cpp-component-extensions.md)です。 としてマークされているクラス`abstract`基底クラスを指定できますが、インスタンス化することはできません。  
  
## <a name="example"></a>例  
次の例では、C3622 を生成します。  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
