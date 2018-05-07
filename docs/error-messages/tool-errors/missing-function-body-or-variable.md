---
title: 関数本体または変数がありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54e2b8c5831eb6d487cf530df1b733b73580cbb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="missing-function-body-or-variable"></a>関数本体または変数の未定義
だけ関数のプロトタイプでは、コンパイラがエラーを発生させず続行できますが、関数のコードまたは予約された変数の領域がないために、リンカーが、アドレスへの呼び出しを解決することはできません。 リンカーが解決する必要がある関数への呼び出しを作成するまで、このエラーを表示はされません。  
  
## <a name="example"></a>例  
 Main 関数呼び出しは、プロトタイプにより、関数の存在を考えるため lnk2019 エラーが発生します。  リンカーは、しないことを検出します。  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>例  
 C++ では、クラス定義に、クラスであり、プロトタイプだけでなく、特定の機能の実装を含めることを確認します。 ヘッダー ファイルの外部でクラスを定義する場合は必ず関数の前にクラス名を含める (`Classname::memberfunction`)。  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [リンカー ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)