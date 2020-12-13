---
description: '詳細情報: _countof マクロ'
title: _countof マクロ
ms.date: 03/22/2018
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 190f47aa7bb6bcf6bbd9478cce9df90aca81b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146459"
---
# <a name="_countof-macro"></a>_countof マクロ

静的に割り当てられた配列内の要素の数を計算します。

## <a name="syntax"></a>構文

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>パラメーター

*array*<br/>
配列の名前。

## <a name="return-value"></a>戻り値

**Size_t** として表される、配列内の要素の数。

## <a name="remarks"></a>解説

**_countof** は、関数に似たプリプロセッサマクロとして実装されます。 C++ のバージョンには、静的に宣言された配列ではなくポインターが渡された場合に、コンパイル時に検出する追加のテンプレート機構があります。

*配列* が実際にはポインターではなく配列であることを確認します。 C では、*配列* がポインターの場合、 **_countof** は間違った結果を生成します。 C++ では、*配列* がポインターである場合、 **_countof** はコンパイルできません。  *ポインターに decays* する関数にパラメーターとして渡された配列。これは、関数内では、配列の範囲を判断するために **_countof** を使用できないことを意味します。

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

## <a name="example"></a>例

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>関連項目

[sizeof 演算子](../../cpp/sizeof-operator.md)<br/>
