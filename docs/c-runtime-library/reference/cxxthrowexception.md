---
description: '詳細については、次を参照してください: _CxxThrowException'
title: _CxxThrowException
ms.date: 11/04/2016
api_name:
- _CxxThrowException
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: df4b1b30ba70ebf34bdb3cb4ae1c51a210f95a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327035"
---
# <a name="_cxxthrowexception"></a>_CxxThrowException

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

## <a name="remarks"></a>解説

このメソッドは、コンパイラで例外処理に使用されるコンパイラ専用ファイルに含まれています。 このメソッドはコードから直接呼び出さないでください。

## <a name="requirements"></a>要件

**ソース:** Throw.cpp

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
