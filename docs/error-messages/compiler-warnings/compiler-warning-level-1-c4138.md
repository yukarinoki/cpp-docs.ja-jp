---
title: コンパイラの警告 (レベル 1) C4138 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4138
dev_langs:
- C++
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc3102f18021c16663bdf61dcde6df5e6893d46c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197089"
---
# <a name="compiler-warning-level-1-c4138"></a>コンパイラの警告 (レベル 1) C4138
始まりのデリミターがない閉じのコメントデリミター (*/) が見つかりました。  
  
 終了のコメント区切り記号の前に、開始のコメント区切り記号がありません。 コンパイラには、アスタリスクの間にスペースが前提としています (<strong>\*</strong>) とフォワード スラッシュ (/)。  
  
## <a name="example"></a>例  
  
```  
// C4138a.cpp  
// compile with: /W1  
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning  
int main()  
{  
}  
```  
  
 この警告は、コメントを入れ子にしようとすると、発生する可能性があります。  
  
 この警告は、コメントを含むコードのセクションをコメント アウトして、 **#if/#endif** ブロックでコードを囲み、制御式を 0 に設定すると、解決する場合があります。  
  
```  
// C4138b.cpp  
// compile with: /W1  
#if 0  
int my_variable;   /* Declaration currently not needed */  
#endif  
int main()  
{  
}  
```