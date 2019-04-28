---
title: '&lt;new&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: b5803b5fdf44392b6096f9c9a5ebdde7f94eae59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223733"
---
# <a name="ltnewgt-functions"></a>&lt;new&gt; 関数

|||
|-|-|
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|

## <a name="nothrow"></a>  nothrow

引数として使用するオブジェクトを提供します、 **nothrow**のバージョンの**新しい**と**削除**します。

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>Remarks

オブジェクトは、パラメーターの型 [std::nothrow_t](../standard-library/nothrow-t-structure.md) に一致する関数の引数として使用されます。

### <a name="example"></a>例

`std::nothrow_t` を関数パラメーターとして使用する方法の例については、「[operator new](../standard-library/new-operators.md#op_new)」および「[operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)」を参照してください。

## <a name="set_new_handler"></a>  set_new_handler

インストールするときに呼び出されるユーザー関数**new 演算子**メモリの割り当ての試行に失敗します。

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>パラメーター

*Pnew*<br/>
`new_handler`をインストールします。

### <a name="return-value"></a>戻り値

最初の呼び出しの場合は 0、それ以降の呼び出しの場合は以前の `new_handler`。

### <a name="remarks"></a>Remarks

関数は*Pnew*静的な[新しいハンドラー](../standard-library/new-typedefs.md#new_handler)ポインターが保持するポインターに以前に格納されている値が返されます。 新しいハンドラーを使って[演算子 new](../standard-library/new-operators.md#op_new)(**size_t**)。

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

## <a name="see-also"></a>関連項目

[\<new>](../standard-library/new.md)<br/>
