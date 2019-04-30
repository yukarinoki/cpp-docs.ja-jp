---
title: srand
ms.date: 1/02/2018
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
ms.openlocfilehash: 6545d4eba6c17fd55bb2b8cf23fb0319d1c96bee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354887"
---
# <a name="srand"></a>srand

使用される擬似乱数ジェネレーターのシード開始値を設定、 **rand**関数。

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

**Srand**関数は、現在のスレッドで、一連の整数の擬似乱数を生成するための開始点を設定します。 結果の同じシーケンスを作成するコード ジェネレーターを再初期化を呼び出し、 **srand**関数を使用して、同じ*シード*引数を再度します。 その他の値の*シード*ジェネレーター擬似乱数シーケンス内のさまざまな開始点を設定します。 **rand**生成される擬似乱数を取得します。 呼び出す**rand**への呼び出しの前に**srand**呼び出すことと同じシーケンスを生成**srand**で*シード*1 として渡されます。

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
