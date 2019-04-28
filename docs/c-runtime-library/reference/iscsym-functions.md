---
title: iscsym、iscsymf、__iscsym、__iswcsym、__iscsymf、__iswcsymf、_iscsym_l、_iswcsym_l、_iscsymf_l、_iswcsymf_l
ms.date: 11/04/2016
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
ms.openlocfilehash: 8ee84243b98c08504ac0bb63593e39c32230b706
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331637"
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym、iscsymf、__iscsym、__iswcsym、__iscsymf、__iswcsymf、_iscsym_l、_iswcsym_l、_iscsymf_l、_iswcsymf_l

整数が識別子に使用できる文字を表すかどうかを判別します。

## <a name="syntax"></a>構文

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。 *c*関数のナロー文字バージョンについては、0 ~ 255 の範囲内で指定する必要があります。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

両方 **_ _iscsym**と **_ _iswcsym**場合は、0 以外の値を返す*c*は文字、アンダー スコア、または数字。 両方 **_ _iscsymf**と **_ _iswcsymf**場合は、0 以外の値を返す*c*が文字またはアンダー スコア。 これらのルーチンの各場合 0 を返します*c*テスト条件を満たしていません。 これらの関数のバージョン、 **_l**を使用する点を除いて、サフィックスが同一、*ロケール*ロケールに依存する動作で、現在のロケールの代わりに渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="remarks"></a>Remarks

これらのルーチンは、プリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、マクロとして定義されます。 これらのルーチンのマクロ バージョンを使用する際には、引数を複数回評価できます。 引数リスト内で副作用がある式を使用するときにはご注意ください。

旧バージョンと互換性のため、 **iscsym**と**iscsymf**マクロとして定義されている場合にのみ[ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md)が定義されていないかが定義されています。0 としてそれ以外の場合、定義されていません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**iscsym**、 **iscsymf**、 **_ _iscsym**、 **_ _iswcsym**、 **_ _iscsymf**、 **_ _iswcsymf**、 **_iscsym_l**、 **_iswcsym_l**、 **_iscsymf_l**、 **_iswcsymf_l**|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|

**Iscsym**、 **iscsymf**、 **_ _iscsym**、 **_ _iswcsym**、 **_ _iscsymf**、 **_ _iswcsymf**、 **_iscsym_l**、 **_iswcsym_l**、 **_iscsymf_l**、および **_iswcsymf_l**ルーチンは、Microsoft 固有の仕様。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
