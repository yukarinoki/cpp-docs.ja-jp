---
title: コンパイラ エラー C2461 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47aee3122dad3e875cf58d5a41bcadda297e1463
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2461"></a>コンパイラ エラー C2461
  
> '*クラス*': コンス トラクター構文の正式なパラメーターがありません  
  
 クラスのコンス トラクターは、仮パラメーターを指定しません。 コンス トラクターの宣言には、仮パラメーター リストを指定する必要があります。 一覧を空にすることができます。  
  
この問題を解決するには、宣言の後のかっこのペアを追加*クラス*:: **クラス*です。  
  
## <a name="example"></a>例  
  
次の例では、c2461 エラーを修正する方法を示します。  
  
```cpp  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;     // C2461  
   C::C();   // OK  
};  
```