---
title: コンパイラの警告 (レベル 1) C4291 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4291
dev_langs:
- C++
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c10351be640dc142f224cb5583a980e396f086cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282380"
---
# <a name="compiler-warning-level-1-c4291"></a>コンパイラの警告 (レベル 1) C4291
'declaration': 対応する delete 演算子が見つかりませんでした。初期化は、例外をスローすると、メモリは解放されません。  
  
 仮[新しい](../../cpp/new-operator-cpp.md)は使用がない配置の[削除](../../cpp/delete-operator-cpp.md)です。  
  
 演算子を持つオブジェクトのメモリが割り当てられているときに**新しい**オブジェクトのコンス トラクターが呼び出されます。 コンス トラクターは、例外をスローする場合は、そのがオブジェクトに割り当てられたメモリの割り当てを解除する必要があります。 これは行えませんしない限り、演算子**削除**演算子に一致する関数が存在する**新しい**です。  
  
 演算子を使用する場合**新しい**、余分な引数およびコンパイル無し[/GX](../../build/reference/gx-enable-exception-handling.md)、 [/EHs](../../build/reference/eh-exception-handling-model.md)、例外処理、コンパイラを有効にする/EHa オプションにするコードが生成または演算子を呼び出す**削除**場合は、コンス トラクターが例外をスローします。  
  
 配置形式を使用する場合、**新しい**演算子 (、フォームだけでなく、サイズ引数を指定して、割り当ての) と、オブジェクトのコンス トラクターは例外をスロー、コンパイラは演算子を呼び出すコードを生成しても**削除**; が、それがだけ行わ場合演算子の仮引数付き**削除**演算子の仮引数付きの一致が存在する**新しい**メモリを割り当てられています。 例えば:  
  
```  
// C4291.cpp  
// compile with: /EHsc /W1  
#include <malloc.h>  
  
class CList  
{  
public:  
   CList(int)  
   {  
      throw "Fail!";  
   }  
};  
  
void* operator new(size_t size, char* pszFilename, int nLine)  
{  
   return malloc(size);  
}  
  
int main(void)  
{  
   try  
   {  
      // This will call ::operator new(unsigned int) to allocate heap  
      // memory. Heap memory pointed to by pList1 will automatically be  
      // deallocated by a call to ::operator delete(void*) when  
      // CList::CList(int) throws an exception.  
      CList* pList1 = new CList(10);  
   }  
   catch (...)  
   {  
   }  
  
   try  
   {  
      // This will call the overloaded ::operator new(size_t, char*, int)  
      // to allocate heap memory. When CList::CList(int) throws an  
      // exception, ::operator delete(void*, char*, int) should be called  
      // to deallocate the memory pointed to by pList2. Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291  
   }  
   catch (...)  
   {  
   }  
}  
```  
  
 上記の例では、ため C4291 の警告が生成されます演算子のない仮引数付き**削除**が定義されている演算子の配置形式に一致する**新しい**です。 問題を解決するには、上記の次のコードを挿入**メイン**です。 注意してすべてのオーバー ロードされた演算子**削除**と一致するオーバー ロードされた演算子の関数パラメーター**新しい**、最初のパラメーターを除く。  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```