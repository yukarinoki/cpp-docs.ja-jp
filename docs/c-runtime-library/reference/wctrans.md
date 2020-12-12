---
description: '詳細情報: wctrans'
title: wctrans
ms.date: 11/04/2016
api_name:
- wctrans
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 59efe03f5851525d38c5ebd93520367338a97a79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229653"
---
# <a name="wctrans"></a>wctrans

文字コードの 1 つのセットから別のセットへのマッピングを指定します。

## <a name="syntax"></a>構文

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>パラメーター

*property*<br/>
有効な変換のいずれかを指定する文字列。

## <a name="return-value"></a>戻り値

現在のロケールの **LC_CTYPE** カテゴリに、プロパティ文字列 *プロパティ* と一致する名前を持つマッピングが定義されていない場合、この関数は0を返します。 それ以外の場合、[towctrans](towctrans.md) への後続の呼び出しに対する 2 番目の引数として使用するのに適した 0 以外の値を返します。

## <a name="remarks"></a>解説

この関数では、文字コードの 1 つのセットから別のセットへのマッピングを指定します。

次の呼び出しのペアの動作はすべてのロケールで同じですが、"C" ロケールであっても追加のマッピングを定義できます。

|機能|同等なもの|
|--------------|-------------|
|tolower (c)|towctrans (c、wctrans ("towlower"))|
|towupper (c)|towctrans (c、wctrans ("toupper"))|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
