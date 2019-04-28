---
title: ceil、ceilf、ceill
ms.date: 04/05/2018
apiname:
- ceilf
- ceil
- ceill
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
- ntdll.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ceil
- ceilf
- ceill
helpviewer_keywords:
- calculating value ceilings
- ceill function
- ceil function
- ceilf function
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
ms.openlocfilehash: b128f20593d41fff3c4c50f6d68f8643798c5b66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335441"
---
# <a name="ceil-ceilf-ceill"></a>ceil、ceilf、ceill

値の切り上げを計算します。

## <a name="syntax"></a>構文

```C
double ceil(
   double x
);
float ceil(
   float x
);  // C++ only
long double ceil(
   long double x
);  // C++ only
float ceilf(
   float x
);
long double ceill(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**Ceil**関数に以上である最小の整数を表す浮動小数点値を返す*x*します。 エラーの戻り値はありません。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN**、 **IND**|none|**_DOMAIN**|

**ceil**ストリーミング SIMD 拡張命令 2 (SSE2) を使用して実装されています。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

## <a name="remarks"></a>Remarks

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **ceil**を受け取る**float**または**長い****二重**型。 C プログラムで**ceil**は、**二重**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**ceil**、 **ceilf**、 **ceill**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[floor](floor-floorf-floorl.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[floor、floorf、floorl](floor-floorf-floorl.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[round、roundf、roundl](round-roundf-roundl.md)<br/>
