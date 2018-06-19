---
title: '&lt;new&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: c52376f504e526c03d4f2c2afd39c029761f3c99
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852609"
---
# <a name="ltnewgt-functions"></a>&lt;new&gt; 関数

|||
|-|-|
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|

## <a name="nothrow"></a>  nothrow

引数として使用するオブジェクトを `nothrow` バージョンの **new** および **delete** に提供します。

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>コメント

オブジェクトは、パラメーターの型 [std::nothrow_t](../standard-library/nothrow-t-structure.md) に一致する関数の引数として使用されます。

### <a name="example"></a>例

`std::nothrow_t` を関数パラメーターとして使用する方法の例については、「[operator new](../standard-library/new-operators.md#op_new)」および「[operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)」を参照してください。

## <a name="set_new_handler"></a>  set_new_handler

`operator new` がメモリ割り当ての試行に失敗した場合に呼び出されるユーザー関数をインストールします。

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>パラメーター

`Pnew` インストールする new_handler です。

### <a name="return-value"></a>戻り値

最初の呼び出しの場合は 0、それ以降の呼び出しの場合は以前の `new_handler`。

### <a name="remarks"></a>コメント

この関数は、関数が保持する静的な [new handler](../standard-library/new-typedefs.md#new_handler) ポインターに `Pnew` を格納し、ポインターに以前に格納された値を返します。 新しいハンドラーは [operator new](../standard-library/new-operators.md#op_new)( **size_t**) によって使用されます。

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
