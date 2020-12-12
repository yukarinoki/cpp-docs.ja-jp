---
description: '詳細については、次を参照してください: __getmainargs、__wgetmainargs'
title: __getmainargs、__wgetmainargs
ms.date: 11/04/2016
api_name:
- __wgetmainargs
- __getmainargs
api_location:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __wgetmainargs
- __getmainargs
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
ms.openlocfilehash: 6f06f83a72d037df6a0973b24ac92ecade6c21eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181749"
---
# <a name="__getmainargs-__wgetmainargs"></a>__getmainargs、__wgetmainargs

コマンドライン解析を呼び出し、渡されたポインターを通して引数を `main()` にコピーし直します。

## <a name="syntax"></a>構文

```cpp
int __getmainargs(
    int * _Argc,
   char *** _Argv,
   char **_ _Env,
   int _DoWildCard,
_startupinfo _ _StartInfo);

int __wgetmainargs (
   int *_Argc,
   wchar_t ***_Argv,
   wchar_t **__Env,
   int _DoWildCard,
   _startupinfo _ _StartInfo)
```

#### <a name="parameters"></a>パラメーター

`_Argc`<br/>
これに続いて `argv` で渡される引数の数を格納した整数。 `argc` パラメーターは、必ず 1 以上になります。

`_Argv`<br/>
プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例として、 `argv[0]` はプログラムが呼び出されるコマンドであり、argv [1] は最初のコマンドライン引数であり、それまでは常に **NULL** である argv [argc] まで続きます。 最初のコマンド ライン引数は、必ず `argv[1]` となり、最後のコマンド ライン引数は、`argv[argc - 1]` になります。

`_Env`<br/>
ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は **NULL** エントリによって終了します。

`_DoWildCard`<br/>
整数。1 に設定されている場合はコマンドライン引数にあるワイルドカードを展開し、0 に設定されているの場合は何もしません。

`_StartInfo`<br/>
CRT DLL に渡される他の情報です。

## <a name="return-value"></a>戻り値

成功した場合は 0、失敗した場合は負の値です。

## <a name="remarks"></a>解説

`__getmainargs` は非ワイド文字プラットフォーム、`__wgetmainargs` はワイド文字 (Unicode) プラットフォームで使用します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__getmainargs|internal.h|
|__wgetmainargs|internal.h|
