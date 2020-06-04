---
title: _findclose
ms.date: 4/2/2020
api_name:
- _findclose
- _o__findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: dffe2ff71f1eecaec78c75867ebb7e34a963ee3a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911808"
---
# <a name="_findclose"></a>_findclose

指定した検索のハンドルを終了し、関連付けられているリソースを解放します。

## <a name="syntax"></a>構文

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>パラメーター

*扱え*<br/>
**_Findfirst**の前回の呼び出しによって返された検索ハンドル。

## <a name="return-value"></a>戻り値

成功した場合、 **_findclose**は0を返します。 それ以外の場合は、-1 を返し、 **errno**を**ENOENT**に設定して、これ以上一致するファイルが見つからないことを示します。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_findclose**|\<io.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[システム コール](../../c-runtime-library/system-calls.md)<br/>
[ファイル名検索関数](../../c-runtime-library/filename-search-functions.md)<br/>
