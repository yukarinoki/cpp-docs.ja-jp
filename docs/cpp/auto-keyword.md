---
title: auto キーワード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a02ed2a19f44f19396038f8e41cb1c7f5a069407
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405887"
---
# <a name="auto-keyword"></a>auto キーワード
**自動**キーワードは宣言指定子。 ただし、C++ 標準ではこのキーワードの元の意味と変更後の意味が定義されます。 Visual C 2010 では、前に、**自動**キーワードで変数の宣言、*自動*ストレージ クラス、つまり、ローカルな有効期間を持つ変数です。 Visual C 2010 では、以降、**自動**キーワードは、その宣言の初期化式から推測される型の変数を宣言します。 [/Zc:auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションの意味を制御する、**自動**キーワード。  
  
## <a name="syntax"></a>構文  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>Remarks  
 定義、**自動**C プログラミング言語ではなく、C++ のプログラミング言語でキーワードを変更します。  
  
 次のトピックについて説明します、**自動**キーワードと、対応するコンパイラ オプション。  
  
-   [自動](../cpp/auto-cpp.md)の新しい定義を説明します、**自動**キーワード。  
  
-   [/Zc:auto (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)のどの定義をコンパイラに指示するコンパイラ オプションについて説明します、**自動**キーワードを使用します。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)