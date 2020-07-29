---
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: b6350568bdba41da90609dfd5e2e60269e7d729f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217039"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

内部 CRT 関数。 構造化例外フレームを処理するために CRT によって使用されます。

## <a name="syntax"></a>構文

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>パラメーター

*pExcept*<br/>
使用可能なステートメントに渡される例外レコード **`catch`** 。

*pRN*<br/>
例外を処理するために使用されるスタック フレームに関する動的な情報。 詳細については、「ehdata.h」を参照してください。

*pContext*<br/>
コンテキスト。 (Intel プロセッサでは使用されません)。

*pDC*<br/>
関数の開始とスタック フレームに関する追加情報。

## <a name="return-value"></a>戻り値

[try-except ステートメント](../cpp/try-except-statement.md)によって使用される*フィルター式*の値のいずれか。

## <a name="remarks"></a>解説

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h、ehdata.h|
