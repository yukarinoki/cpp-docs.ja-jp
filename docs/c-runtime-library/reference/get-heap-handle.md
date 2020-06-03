---
title: _get_heap_handle
ms.date: 4/2/2020
api_name:
- _get_heap_handle
- _o__get_heap_handle
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_heap_handle
- get_heap_handle
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
ms.openlocfilehash: 895814a1a44910ef65a826cba330a3edd70b85a9
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916298"
---
# <a name="_get_heap_handle"></a>_get_heap_handle

C ランタイム システムで使用されるヒープのハンドルを返します。

## <a name="syntax"></a>構文

```C
intptr_t _get_heap_handle( void );
```

## <a name="return-value"></a>戻り値

C ランタイム システムで使用される Win32 ヒープのハンドルを返します。

## <a name="remarks"></a>解説

[HeapSetInformation](/windows/win32/api/heapapi/nf-heapapi-heapsetinformation) を呼び出し、CRT ヒープの Low Fragmentation Heap を有効にする場合は、この関数を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_heap_handle**|\<malloc.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="sample"></a>サンプル

```cpp
// crt_get_heap_handle.cpp
// compile with: /MT
#include <windows.h>
#include <malloc.h>
#include <stdio.h>

int main(void)
{
    intptr_t hCrtHeap = _get_heap_handle();
    ULONG ulEnableLFH = 2;
    if (HeapSetInformation((PVOID)hCrtHeap,
                           HeapCompatibilityInformation,
                           &ulEnableLFH, sizeof(ulEnableLFH)))
        puts("Enabling Low Fragmentation Heap succeeded");
    else
        puts("Enabling Low Fragmentation Heap failed");
    return 0;
}
```

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
