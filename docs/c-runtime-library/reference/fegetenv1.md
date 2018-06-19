---
title: 分かって |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fetegenv
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
- fegetenv
- fenv/fegetenv
dev_langs:
- C++
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc8b5d189838c2788bc6200f9072c9511e61d42f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396171"
---
# <a name="fegetenv"></a>fegetenv

指定したオブジェクトの現在の浮動小数点環境を格納します。

## <a name="syntax"></a>構文

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>パラメーター

*penv*<br/>
ポインター、 **fenv_t**浮動小数点環境の現在の値を格納するオブジェクト。

## <a name="return-value"></a>戻り値

浮動小数点環境が正常に格納されている場合は 0 を返します*penv*です。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>コメント

**分かって**関数によって指されるオブジェクトに現在の浮動小数点環境を格納する*penv*です。 浮動小数点環境とは、浮動小数点計算に影響する一連の状態フラグと制御モードです。 浮動小数点例外の丸め方向モードと状態フラグが含まれます。  場合*penv*が有効なを指していません**fenv_t**オブジェクト、それ以降の動作は未定義です。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
