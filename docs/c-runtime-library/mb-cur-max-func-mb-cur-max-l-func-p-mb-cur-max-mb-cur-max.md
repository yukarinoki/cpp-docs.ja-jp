---
description: '詳細については、次を参照してください: ___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max'
title: ___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max
ms.date: 4/2/2020
api_name:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
- _o____mb_cur_max_func
api_location:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
ms.openlocfilehash: 1308dbe969f8b6638835f52ec1e7a2cdcd63bb7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321163"
---
# <a name="___mb_cur_max_func-___mb_cur_max_l_func-__p___mb_cur_max-__mb_cur_max"></a>___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max

内部 CRT 関数。 現在または指定されたロケールのマルチバイト文字の最大バイト数を取得します。

## <a name="syntax"></a>構文

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>パラメーター

locale 結果の取得元のロケール構造。 この値が null の場合は、現在のスレッド ロケールが使用されます。

## <a name="return-value"></a>戻り値

現在のスレッド ロケールまたは指定されたロケールのマルチバイト文字の最大バイト数。

## <a name="remarks"></a>解説

これは、スレッド ローカル ストレージから [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) マクロの現在の値を取得するために CRT で使用される内部関数です。 移植性を考慮して、コードでは `MB_CUR_MAX` マクロを使用することをお勧めします。

`__mb_cur_max` マクロは、`___mb_cur_max_func()` 関数を呼び出す便利な方法です。 `__p___mb_cur_max` 関数は、Visual C++ 5.0 以前のバージョンとの互換性のために定義されています。

内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。 コード内では使用しないことをお勧めします。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|

## <a name="see-also"></a>関連項目

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
