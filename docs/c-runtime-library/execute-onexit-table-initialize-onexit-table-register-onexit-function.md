---
title: _execute_onexit_table、_initialize_onexit_table、_register_onexit_function | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
dev_langs:
- C++
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9a6ea61883e6ce94bc41f16e7139156c68c8059
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082093"
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table、_initialize_onexit_table、_register_onexit_function

終了時に呼び出されるルーチンを管理します。

## <a name="syntax"></a>構文

```
int _initialize_onexit_table(
    _onexit_table_t* table
    );

int _register_onexit_function(
    _onexit_table_t* table,
    _onexit_t        function
    );

int _execute_onexit_table(
    _onexit_table_t* table
    );
```

#### <a name="parameters"></a>パラメーター

*table*<br/>
[in, out] onexit 関数テーブルを指すポインター。

*function*<br/>
[in] onexit 関数テーブルに追加する関数を指すポインター。

## <a name="return-value"></a>戻り値

正常に終了した場合は、0 を返します。 それ以外の場合は、負の値を返します。

## <a name="remarks"></a>コメント

これらの関数は、C ランタイムをサポートするために使用されるインフラストラクチャ実装の詳細であり、ご使用のコードから直接呼び出してはなりません。 C ランタイムでは、*onexit 関数テーブル*を使用して、`atexit`、`at_quick_exit`、および `_onexit` の呼び出しによって登録される関数のシーケンスを表現します。 onexit 関数テーブルのデータ構造は、C ランタイムの不透明な実装の詳細であり、データ メンバーの順番と意味は変わる場合があります。 それらを外部コードによって確認してはなりません。

`_initialize_onexit_table` 関数は、onexit 関数テーブルをその初期値に初期化します。  この関数は、onexit 関数テーブルを `_register_onexit_function` または `_execute_onexit_table` に渡す前に呼び出す必要があります。

`_register_onexit_function` 関数は、onexit 関数テーブルの末尾に関数を追加します。

`_execute_onexit_table` 関数は、onexit 関数テーブル内のすべての関数を実行し、テーブルをクリアして、制御を返します。 `_execute_onexit_table` の呼び出しの後、このテーブルは無効な状態になります。再度使用するには `_initialize_onexit_table` を呼び出して事前に再初期化しておく必要があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`_initialize_onexit_table function`、`_register_onexit_function`、`_execute_onexit_table`|C、C++: \<process.h>|

`_initialize_onexit_table`、`_register_onexit_function`、`_execute_onexit_table` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>参照

[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit、_Exit、_exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit、_onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)