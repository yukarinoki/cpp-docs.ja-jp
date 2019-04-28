---
title: feholdexcept
ms.date: 04/05/2018
apiname:
- feholdexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: 26097398b9f9d498ab4c56690dc9c6cbb950bafb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334386"
---
# <a name="feholdexcept"></a>feholdexcept

指定したオブジェクトに現在の浮動小数点環境を格納し、浮動小数点状態フラグをクリアし、可能であれば、浮動小数点環境を無停止モードにします。

## <a name="syntax"></a>構文

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>パラメーター

*penv*<br/>
ポインター、 **fenv_t**浮動小数点環境のコピーを格納するオブジェクト。

## <a name="return-value"></a>戻り値

関数が無停止の浮動小数点例外処理を正常に有効にできない場合にのみ 0 を返します。

## <a name="remarks"></a>Remarks

**Feholdexcept**で現在の浮動小数点環境の状態を保存する関数が使用される、 **fenv_t**指すオブジェクト*penv*とに、環境を設定するには浮動小数点例外での実行は中断されません。 これは無停止モードと呼ばれます。  このモードは、[fesetenv](fesetenv1.md) または [feupdateenv](feupdateenv.md) を使用して環境が復元されるまで継続します。

この関数は、1 つまたは複数の浮動小数点例外を呼び出し元から隠す必要があるサブルーチンの開始時に使用できます。 例外を報告する内容を消去望ましくない例外を使用して[feclearexcept](feclearexcept1.md)しを呼び出して無停止モードを終了**feupdateenv**します。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
