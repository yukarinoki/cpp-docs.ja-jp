---
description: '詳細情報: 予期しない (CRT)'
title: unexpected (CRT)
ms.date: 11/04/2016
api_name:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 73c632c4dd5bfedbb1c3724e60786b348f77f0be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186637"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

**Set_unexpected** を使用して、指定した **終了** または関数を呼び出します。

## <a name="syntax"></a>構文

```C
void unexpected( void );
```

## <a name="remarks"></a>解説

**予期** しないルーチンは、C++ 例外処理の現在の実装では使用されません。 既定では、**予期しない** 呼び出しは **終了** します。 この既定の動作を変更するには、カスタムの終了関数を記述し、関数の名前を引数として **set_unexpected** を呼び出します。 **予期しない** 呼び出し **set_unexpected** の引数として渡された最後の関数。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**不適切**|\<eh.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[取り消し](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[解約](terminate-crt.md)<br/>
