---
title: auto キーワード |Microsoft ドキュメント
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
ms.openlocfilehash: 93b2f5e28dc0306a996b4c8bdb799122fe4646ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410000"
---
# <a name="auto-keyword"></a>auto キーワード
`auto` キーワードは宣言指定子です。 ただし、C++ 標準ではこのキーワードの元の意味と変更後の意味が定義されます。 Visual C 2010 では、前に、`auto`キーワードで宣言内の変数、*自動*ストレージ クラスです。 つまり、ローカルの有効期間を持つ変数です。 Visual C 2010、始まる、`auto`キーワードは、その宣言で初期化式から推測される型の変数を宣言します。 [/Zc:auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションの意味を制御する、`auto`キーワード。  
  
## <a name="syntax"></a>構文  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>コメント  
 `auto` キーワードの定義は、C++ プログラミング言語では変化しますが、C プログラミング言語では変化しません。  
  
 ここからのトピックでは、`auto` キーワードと、対応するコンパイラ オプションについて説明します。  
  
-   [自動](../cpp/auto-cpp.md)の新しい定義の説明、`auto`キーワード。  
  
  
-   [/Zc:auto (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)のどの定義をコンパイラに指示するコンパイラ オプションについて説明します、`auto`キーワードを使用します。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)