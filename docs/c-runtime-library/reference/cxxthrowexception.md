---
title: _CxxThrowException
ms.date: 11/04/2016
apiname:
- _CxxThrowException
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
apitype: DLLExport
f1_keywords:
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: 925b72a120b31029b76fa38bee73eea003511cd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550333"
---
# <a name="cxxthrowexception"></a>_CxxThrowException

例外レコードを作成し、ランタイム環境を呼び出して例画の処理を開始します。

## <a name="syntax"></a>構文

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>パラメーター

*pExceptionObject*<br/>
例外を生成したオブジェクト。

*pThrowInfo*<br/>
例外の処理に必要な情報。

## <a name="remarks"></a>Remarks

このメソッドは、コンパイラで例外処理に使用されるコンパイラ専用ファイルに含まれています。 このメソッドはコードから直接呼び出さないでください。

## <a name="requirements"></a>必要条件

**ソース:** Throw.cpp

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
