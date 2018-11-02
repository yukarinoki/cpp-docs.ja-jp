---
title: コンパイラの警告 (レベル 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: e1b787e7149afe93fb50cc1e6ceaecba2e787876
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465560"
---
# <a name="compiler-warning-level-1-c4291"></a>コンパイラの警告 (レベル 1) C4291

'declaration': 一致する演算子が見つかりました削除。初期化が例外をスローすると、メモリは解放されません。

配置[新しい](../../cpp/new-operator-cpp.md)使用がない配置の[削除](../../cpp/delete-operator-cpp.md)します。

演算子でオブジェクトがメモリに割り当てられたときに**新しい**オブジェクトのコンス トラクターが呼び出されます。 コンス トラクターは、例外をスローする場合に、オブジェクトの割り当てられたメモリ割り当てが解除する必要があります。 しない限り、これ行うことはできません、演算子**削除**演算子と一致する関数が存在する**新しい**します。

演算子を使用する場合**新しい**なしでコンパイル、余分な引数[/GX](../../build/reference/gx-enable-exception-handling.md)、 [/EHs](../../build/reference/eh-exception-handling-model.md)、/EHa コンパイラ、例外処理を有効にするオプションはコードを生成または演算子を呼び出す**削除**場合は、コンス トラクターが例外をスローします。

配置形式を使用する場合、**新しい**演算子 (割り当てのだけでなく、サイズ引数を持つフォーム) と、オブジェクトのコンス トラクターが例外をスロー、コンパイラは演算子を呼び出すコードを生成して引き続き**削除**; 演算子の場合は、のみが**削除**配置形式の演算子の一致が存在する**新しい**メモリを割り当てることです。 例えば:

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

上記の例では、ため、警告 C4291 が生成されます演算子の配置フォーム**削除**が定義されている演算子の配置形式と一致する**新しい**しません。 問題を解決するには、上記の次のコードを挿入**メイン**します。 注意してすべてのオーバー ロードされた演算子**削除**関数のパラメーターには、オーバー ロードされた演算子のものと一致**新しい**、最初のパラメーターを除く。

```
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```