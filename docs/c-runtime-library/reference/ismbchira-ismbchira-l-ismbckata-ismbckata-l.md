---
title: _ismbchira、_ismbchira_l、_ismbckata、_ismbckata_l
ms.date: 4/2/2020
api_name:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
- _o__ismbchira
- _o__ismbchira_l
- _o__ismbckata
- _o__ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
ms.openlocfilehash: 89c6aacbb6726165703d38e3ea519806b1f970d2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910705"
---
# <a name="_ismbchira-_ismbchira_l-_ismbckata-_ismbckata_l"></a>_ismbchira、_ismbchira_l、_ismbckata、_ismbckata_l

**コード ページ 932 固有の関数**

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _ismbchira(
   unsigned int c
);
int _ismbchira_l(
   unsigned int c,
   _locale_t locale
);
int _ismbckata(
   unsigned int c
);
int _ismbckata_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*40u-c*<br/>
テストする文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 *C* <= 255 で、対応する **_ismbb**ルーチン (たとえば、 **_ismbcalnum**が **_ismbbalnum**に対応する) がある場合、結果は対応する **_ismbb**ルーチンの戻り値になります。

## <a name="remarks"></a>解説

これらの各関数は特定の条件で特定のマルチバイト文字をテストします。

**_L**サフィックスを持つこれらの関数のバージョンは同じですが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用する点が異なります。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

|ルーチン|テスト条件 (コード ページ 932 のみ)|
|-------------|-------------------------------------------|
|**_ismbchira**|2バイトのひらがな: 0x829F<=*c*<= 0X829f。|
|**_ismbchira_l**|2バイトのひらがな: 0x829F<=*c*<= 0X829f。|
|**_ismbckata**|2バイトカタカナ: 0x8340<=*c*<= 0x8340。|
|**_ismbckata_l**|2バイトカタカナ: 0x8340<=*c*<= 0x8340。|

**終了コードページ932固有**

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbchira**|\<mbstring.h>|
|**_ismbchira_l**|\<mbstring.h>|
|**_ismbckata**|\<mbstring.h>|
|**_ismbckata_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
