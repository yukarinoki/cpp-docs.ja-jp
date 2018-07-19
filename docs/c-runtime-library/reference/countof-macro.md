---
title: _countof マクロ | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
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
apitype: DLLExport
f1_keywords:
- _countof
- countof
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f30df64b045e2af6181d343a4eafb962d22eaa05
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394744"
---
# <a name="countof-macro"></a>_countof マクロ

静的に割り当てられた配列の要素の数を計算します。

## <a name="syntax"></a>構文

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>パラメーター

*array*<br/>
配列の名前。

## <a name="return-value"></a>戻り値

表される、配列内の要素の数、 **size_t**です。

## <a name="remarks"></a>コメント

**_countof**関数のようなプリプロセッサ マクロとして実装されます。 C++ バージョンには、ポインターが静的に宣言された配列の代わりに渡された場合は、コンパイル時に検出するために余分なテンプレートの機構です。

いることを確認*配列*が実際には、配列、ポインターではありません。 C では、 **_countof**場合は、誤った結果を生成*配列*のポインターです。 C++ では、 **_countof**場合のコンパイルに失敗した*配列*のポインターです。  関数にパラメーターとして渡される配列*ポインターに減衰*、関数内で使用できないことを意味する **_countof**配列の範囲を確認します。

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
