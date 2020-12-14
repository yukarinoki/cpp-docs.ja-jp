---
description: '詳細については、次を参照してください: _ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l'
title: _ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l
ms.date: 4/2/2020
api_name:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
- _o__ismbclower
- _o__ismbclower_l
- _o__ismbcupper
- _o__ismbcupper_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbcupper
- _ismbclower
helpviewer_keywords:
- _ismbcupper function
- ismbclower function
- _ismbclower_l function
- ismbcupper_l function
- _ismbclower function
- ismbcupper function
- ismbclower_l function
- _ismbcupper_l function
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
ms.openlocfilehash: c4afed88aff750be44602270b0bc7c2e3fa77073
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279664"
---
# <a name="_ismbclower-_ismbclower_l-_ismbcupper-_ismbcupper_l"></a>_ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l

マルチバイト文字が小文字または大文字であるかどうかをチェックします。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _ismbclower(
   unsigned int c
);
int _ismbclower_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcupper(
   unsigned int c
);
int _ismbcupper_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 *C*<= 255 で、対応する **_ismbb** ルーチン (たとえば、 **_ismbcalnum** が **_ismbbalnum** に対応する) がある場合、結果は対応する **_ismbb** ルーチンの戻り値になります。

## <a name="remarks"></a>解説

これらの各関数は特定の条件で特定のマルチバイト文字をテストします。

**_L** サフィックスを持つこれらの関数のバージョンは同じですが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用する点が異なります。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

|ルーチンによって返される値|テスト条件|コード ページ 932 の例|
|-------------|--------------------|---------------------------|
|**_ismbclower**|小文字の英字|*C* が ASCII 小文字の英字 (0x61<=*c*<= 0x7a) の1バイト表現である場合にのみ、0以外の値を返します。|
|**_ismbclower_l**|小文字の英字|*C* が ASCII 小文字の英字 (0x61<=*c*<= 0x7a) の1バイト表現である場合にのみ、0以外の値を返します。|
|**_ismbcupper**|大文字の英字|*C* が ASCII 大文字の英文字 (0x41<=*c*<= 0x5a) の1バイト表現である場合に限り、0以外の値を返します。|
|**_ismbcupper_l**|大文字の英字|*C* が ASCII 大文字の英文字 (0x41<=*c*<= 0x5a) の1バイト表現である場合に限り、0以外の値を返します。|

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_ismbclower**|\<mbstring.h>|
|**_ismbclower_l**|\<mbstring.h>|
|**_ismbcupper**|\<mbstring.h>|
|**_ismbcupper_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc ルーチン](../../c-runtime-library/ismbc-routines.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
