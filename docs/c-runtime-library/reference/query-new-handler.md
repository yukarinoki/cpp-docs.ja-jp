---
title: _query_new_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _query_new_handler
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _query_new_handler
- query_new_handler
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 340574a57bf1e6309ac9a5e1aa59b7e28632ae59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401000"
---
# <a name="querynewhandler"></a>_query_new_handler

現在の新しいハンドラー ルーチンのアドレスを返します。

## <a name="syntax"></a>構文

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>戻り値

によって設定された現在の新しいハンドラー ルーチンのアドレスが返される **_set_new_handler**です。

## <a name="remarks"></a>コメント

C++ **_query_new_handler**関数は、C++ での設定の現在の例外処理関数のアドレスを返します[_set_new_handler](set-new-handler.md)関数。 **_set_new_handler**に制御を設定する場合は、例外処理関数の指定に使用される、**新しい**演算子がメモリの割り当てに失敗します。 詳細については、C++ 言語リファレンスの「[new および delete 演算子](../../cpp/new-and-delete-operators.md)」の説明をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_query_new_handler**|\<new.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
