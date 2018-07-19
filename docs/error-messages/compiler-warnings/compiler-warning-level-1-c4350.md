---
title: コンパイラの警告 (レベル 1) C4350 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7e13b73eeee9c24841e97419b702b3e41be3982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286930"
---
# <a name="compiler-warning-level-1-c4350"></a>コンパイラの警告 (レベル 1) C4350
動作変更: 'member1' が 'member2' の代わりに呼び出されました。  
  
 右辺値は、非定数の参照にバインドすることはできません。 Visual Studio 2003 より前に、の Visual C のバージョンでは、直接の初期化で非定数の参照を右辺値をバインドすることでした。 このコードでは、警告できるようになりました。  
  
 旧バージョンと互換性のため、非 const 参照を右辺値をバインドすることもが可能な限り、標準変換はお勧めします。  
  
 この警告は、Visual C .NET 2002 コンパイラからの動作の変更を表します。 有効な場合、この警告を正しいコードの指定された可能性のある可能性があります。 たとえば、そのことがあるを使用する場合、 **std::auto_ptr**クラス テンプレートです。  
  
 この警告を表示する場合は、非 const 参照を右辺値をバインディングに依存しているかどうかをコードを確認します。 参照に const を追加するか、追加の定数参照のオーバー ロードを提供するには、問題を解決できます。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
 次の例では、C4350 が生成されます。  
  
```cpp  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead:  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```