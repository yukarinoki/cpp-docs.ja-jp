---
title: '&lt;new&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- new/std::get_new_handler
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: 6b51a5bcbb9c90370cef1391d4020862d2e2cefd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212177"
---
# <a name="ltnewgt-functions"></a>&lt;new&gt; 関数

## <a name="get_new_handler"></a><a name="get_new_handler"></a>get_new_handler

```cpp
new_handler get_new_handler() noexcept;
```

### <a name="remarks"></a>解説

現在のを返し `new_handler` ます。

## <a name="launder"></a><a name="launder"></a>launder

```cpp
template <class T>
    constexpr T* launder(T* ptr) noexcept;
```

### <a name="parameters"></a>パラメーター

*ポインター*\
*T*に似た型のオブジェクトを保持する、メモリ内のバイトのアドレス。

### <a name="return-value"></a>戻り値

X を指す*T \* *型の値。

### <a name="remarks"></a>解説

ポインターの最適化バリアとも呼ばれます。

引数の値が定数式で使用される場合に、定数式として使用されます。 別のオブジェクトによって占有されているストレージ内、つまり類似したポインターを持つオブジェクトを指すポインター値によって、ストレージのバイトに到達できます。

### <a name="example"></a>例

```cpp
struct X { const int n; };

X *p = new X{3};
const int a = p->n;
new (p) X{5}; // p does not point to new object because X::n is const
const int b = p->n; // undefined behavior
const int c = std::launder(p)->n; // OK
```

## <a name="nothrow"></a><a name="nothrow"></a>nothrow

およびのバージョンの引数として使用されるオブジェクトを提供し **`nothrow`** **`new`** **`delete`** ます。

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>解説

オブジェクトは、パラメーターの型 [std::nothrow_t](../standard-library/nothrow-t-structure.md) に一致する関数の引数として使用されます。

### <a name="example"></a>例

`std::nothrow_t` を関数パラメーターとして使用する方法の例については、[operator new](../standard-library/new-operators.md#op_new) および [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) に関する記事をご覧ください。

## <a name="set_new_handler"></a><a name="set_new_handler"></a>set_new_handler

メモリを割り当てようとしたときに**operator new**が失敗したときに呼び出されるユーザー関数をインストールします。

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>パラメーター

*Pnew*\
`new_handler`インストールする。

### <a name="return-value"></a>戻り値

最初の呼び出しの場合は 0、それ以降の呼び出しの場合は以前の `new_handler`。

### <a name="remarks"></a>解説

関数は、保持する静的[新しいハンドラー](../standard-library/new-typedefs.md#new_handler)ポインターに*pnew*を格納し、ポインターに以前に格納されていた値を返します。 新しいハンドラーは、 [operator new](../standard-library/new-operators.md#op_new)(**size_t**) によって使用されます。

### <a name="example"></a>例

```cpp
// new_set_new_handler.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;
void __cdecl newhandler( )
{
   cout << "The new_handler is called:" << endl;
   throw bad_alloc( );
   return;
}

int main( )
{
   set_new_handler (newhandler);
   try
   {
      while ( 1 )
      {
         new int[5000000];
         cout << "Allocating 5000000 ints." << endl;
      }
   }
   catch ( exception e )
   {
      cout << e.what( ) << endl;
   }
}
```

```Output
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
The new_handler is called:
bad allocation
```
