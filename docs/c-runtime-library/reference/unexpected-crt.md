---
title: unexpected (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- unexpected
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
- unexpected
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8dc51c41ebf938f59493cbd62fac3e0a491601
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408108"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

呼び出し**終了**または関数を使用して指定した**set_unexpected**です。

## <a name="syntax"></a>構文

```C
void unexpected( void );
```

## <a name="remarks"></a>コメント

**予期しない**ルーチンは、C++ 例外処理の現在の実装では使用されません。 **予期しない**呼び出し**終了**既定です。 この既定の動作を変更するには、カスタムの終了関数を記述して呼び出すこと**set_unexpected**関数の引数としての名前に置き換えます。 **予期しない**に渡す引数として指定されている最後の関数を呼び出す**set_unexpected**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**unexpected**|\<eh.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
