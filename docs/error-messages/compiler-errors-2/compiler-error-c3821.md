---
title: コンパイラ エラー C3821 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3821
dev_langs:
- C++
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0d9c880cb2bc5f4b4a25d37afe80ca2a316a4f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268082"
---
# <a name="compiler-error-c3821"></a>コンパイラ エラー C3821
'function': マネージ型または関数をアンマネージ関数で使用することはできません  
  
 インライン アセンブリでの関数または[setjmp](../../c-runtime-library/reference/setjmp.md)値の型またはマネージ クラスを含めることはできません。 このエラーを解決するには、インライン アセンブリを削除し、`setjmp`または管理対象のオブジェクトを削除します。  
  
 C3821 は、vararg 関数で自動ストレージを使用しようとする場合にも発生することができます。  詳細については、次を参照してください[可変個引数リスト (...)。(C + + CLI)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)と[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3821 を生成します。  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C3821 を生成します。  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
