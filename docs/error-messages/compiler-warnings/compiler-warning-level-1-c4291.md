---
description: '詳細情報: コンパイラの警告 (レベル 1) C4291'
title: コンパイラの警告 (レベル 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: 190fbb1ed91c5524dcd83a0a02a0b0280e264891
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340113"
---
# <a name="compiler-warning-level-1-c4291"></a>コンパイラの警告 (レベル 1) C4291

' 宣言 ': 一致する演算子の削除が見つかりませんでした。初期化が例外をスローした場合、メモリは解放されません

配置の[削除](../../cpp/delete-operator-cpp.md)がない場合は、配置の[新しい](../../cpp/new-operator-cpp.md)が使用されます。

演算子を使用してオブジェクトにメモリが割り当てられると **`new`** 、オブジェクトのコンストラクターが呼び出されます。 コンストラクターが例外をスローした場合、そのオブジェクトに割り当てられたメモリの割り当てを解除する必要があります。 **`delete`** 演算子に一致する演算子関数が存在しない限り、この操作は実行できません **`new`** 。

引数を追加せずに演算子を使用 **`new`** し、 [/Gx](../../build/reference/gx-enable-exception-handling.md)、 [/Ehs](../../build/reference/eh-exception-handling-model.md)、または/eha オプションを使用して例外処理を有効にすると、コンパイラは、 **`delete`** コンストラクターが例外をスローした場合に operator を呼び出すためのコードを生成します。

演算子の配置形式 **`new`** (割り当てのサイズに加えて引数を含む) を使用し、オブジェクトのコンストラクターが例外をスローした場合、コンパイラは operator を呼び出すためのコードを生成しますが、これは、 **`delete`** **`delete`** メモリを割り当てた演算子の配置形式と一致する配置形式の演算子が存在する場合にのみ実行され **`new`** ます。 次に例を示します。

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

上の例では、 **`delete`** 演算子の配置形式に一致する演算子の配置形式が定義されていないため、警告 C4291 が生成され **`new`** ます。 この問題を解決するには、 **main** の上に次のコードを挿入します。 オーバーロードされた演算子のすべてのパラメーターが、 **`delete`** **`new`** 最初のパラメーターを除き、オーバーロードされた演算子のパラメーターと一致することに注意してください。

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
