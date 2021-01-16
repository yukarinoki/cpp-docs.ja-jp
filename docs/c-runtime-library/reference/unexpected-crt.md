---
description: '詳細情報: 予期しない (CRT)'
title: unexpected (CRT)
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 098d686e7c33d17020990b1db168d95c327d5112
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242905"
---
# <a name="unexpected-crt"></a>`unexpected` .CRT

**`terminate`** またはを使用して指定した関数を呼び出し **`set_unexpected`** ます。

## <a name="syntax"></a>構文

```C
void unexpected( void );
```

## <a name="remarks"></a>解説

この **`unexpected`** ルーチンは、C++ 例外処理の現在の実装では使用されません。 **`unexpected`****`terminate`** 既定では、を呼び出します。 この既定の動作は、カスタムの終了関数を記述することによって変更できます。 **`set_unexpected`** 引数として関数の名前を指定してを呼び出します。 **`unexpected`** に渡された最後の関数を呼び出し **`set_unexpected`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`unexpected`**|`<eh.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>参照

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[取り消し](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[解約](terminate-crt.md)<br/>
