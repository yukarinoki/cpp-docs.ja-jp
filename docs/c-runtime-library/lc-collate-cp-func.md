---
title: ___lc_collate_cp_func
ms.date: 4/2/2020
api_name:
- ___lc_collate_cp_func
- _o____lc_collate_cp_func
api_location:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___lc_collate_cp_func
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
ms.openlocfilehash: 7247827cb2bfe18c341ce60c2f3d8976f676b138
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914076"
---
# <a name="___lc_collate_cp_func"></a>___lc_collate_cp_func

内部 CRT 関数。 スレッドの現在の照合順序コード ページを取得します。

## <a name="syntax"></a>構文

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>戻り値

スレッドの現在の照合順序コード ページ。

## <a name="remarks"></a>解説

`___lc_collate_cp_func` は、CRT データのスレッド ローカル ストレージから現在の照合順序コード ページを取得するために、他の CRT 関数によって使用される内部 CRT 関数です。 この情報は、[_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 関数を使用して取得することもできます。

内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。 コード内では使用しないことをお勧めします。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|`___lc_collate_cp_func`|crt\src\setlocal.h|

## <a name="see-also"></a>関連項目

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
