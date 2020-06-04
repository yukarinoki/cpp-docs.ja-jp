---
title: コンパイラの警告 (レベル 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: c1972236e30be4e6ca738b606b00398f5c7860e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754857"
---
# <a name="compiler-warning-level-1-c4291"></a>コンパイラの警告 (レベル 1) C4291

'宣言' : 一致する演算子の削除が見つかりません。初期化が例外をスローした場合、メモリは解放されません

配置削除がない[配置新規](../../cpp/new-operator-cpp.md)が使用[されます。](../../cpp/delete-operator-cpp.md)

演算子**new**を使用してオブジェクトにメモリが割り当てられると、オブジェクトのコンストラクタが呼び出されます。 コンストラクターが例外をスローする場合は、オブジェクトに割り当てられたすべてのメモリを割り当て解除する必要があります。 これは、演算子**new**に一致する演算子**削除**関数が存在しない限り、実行できません。

余分な**引数を指定**せずに new 演算子を使用し[、/GX、/EHs、/EHa](../../build/reference/gx-enable-exception-handling.md)オプションを指定してコンパイルして例外処理を有効にすると、コンパイラはコンストラクターが例外をスローした場合に演算子**削除**を呼び出すコードを生成します。 [/EHs](../../build/reference/eh-exception-handling-model.md)

**new**演算子の配置形式 (割り当てのサイズに加えて引数を持つフォーム) を使用し、オブジェクトのコンストラクタが例外をスローした場合、コンパイラは引き続き演算子**delete**を呼び出すコードを生成します。しかし、この操作は、メモリを割り当てた新**しい**演算子の配置フォームに一致する演算子**delete**の配置フォームが存在する場合にのみ行われます。 次に例を示します。

```cpp
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

上の例では、オペレータ**delete**の配置フォームが定義されておらず、オペレータ**new**の配置形式に一致するものが定義されていないため、警告 C4291 が生成されます。 この問題を解決するには **、main**の上に次のコードを挿入します。 オーバーロードされた演算子**の delete**関数パラメータはすべて、最初のパラメータを除いてオーバーロードされた演算子**new**のパラメータと一致します。

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
