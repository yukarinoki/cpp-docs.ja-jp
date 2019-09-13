---
title: srand
ms.date: 01/02/2018
apiname:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- srand
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.openlocfilehash: d74ae4cbec5a76df48bb2b56acab7329e6cf8aa5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927408"
---
# <a name="srand"></a>srand

**Rand**関数によって使用される擬似乱数ジェネレーターの開始シード値を設定します。

## <a name="syntax"></a>構文

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>パラメーター

*シード*<br/>
擬似乱数ジェネレーターのシード

## <a name="remarks"></a>Remarks

**Srand**関数は、現在のスレッドで一連の擬似乱数を生成するための開始点を設定します。 ジェネレーターを再初期化して同じ結果シーケンスを作成するには、 **srand**関数を呼び出し、同じ*シード*引数を再度使用します。 *シード*のその他の値は、擬似乱数シーケンスの異なる開始位置にジェネレーターを設定します。 **rand**は、生成される擬似乱数を取得します。 **Srand**の呼び出しの前に**rand**を呼び出すと、*シード*が1として渡された**srand**を呼び出す場合と同じシーケンスが生成されます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[rand](rand.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
