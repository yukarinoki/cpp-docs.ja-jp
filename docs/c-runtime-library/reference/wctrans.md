---
title: wctrans
ms.date: 11/04/2016
apiname:
- wctrans
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 3c7aace7a93160d2e9a4c1523d49bcaf6ae4dc20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188456"
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

*プロパティ*<br/>
有効な変換のいずれかを指定する文字列。

## <a name="return-value"></a>戻り値

場合、 **LC_CTYPE**の現在のロケールのカテゴリが名前に一致するプロパティの文字列マッピングを定義しない*プロパティ*関数は 0 を返します。 それ以外の場合、[towctrans](towctrans.md) への後続の呼び出しに対する 2 番目の引数として使用するのに適した 0 以外の値を返します。

## <a name="remarks"></a>Remarks

この関数では、文字コードの 1 つのセットから別のセットへのマッピングを指定します。

次の呼び出しのペアの動作はすべてのロケールで同じですが、"C" ロケールであっても追加のマッピングを定義できます。

|関数|同等なもの|
|--------------|-------------|
|tolower(c)|towctrans(c, wctrans("towlower"))|
|towupper(c)|towctrans(c, wctrans("toupper"))|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
