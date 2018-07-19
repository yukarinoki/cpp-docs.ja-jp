---
title: _cexit、_c_exit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _c_exit
- _cexit
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
dev_langs:
- C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0840ccec85d46a13984b65ebe99e53b968bedeb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395823"
---
# <a name="cexit-cexit"></a>_cexit、_c_exit

クリーンアップ操作を実行し、プロセスを終了せずに処理を戻します。

## <a name="syntax"></a>構文

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>コメント

**_Cexit**関数後入れ先出し (LIFO) の順序、によって登録された関数の呼び出し**atexit**と **_onexit**です。 **_Cexit**すべての I/O バッファーをフラッシュし、返す前にすべての開いているストリームを閉じます。 **_c_exit**と同じ **_exit**が、処理されず、呼び出し元プロセスを返す**atexit**または **_onexit**ストリーム バッファーのフラッシュまたはします。 動作**終了**、 **_exit**、 **_cexit**、および **_c_exit**は次の表に示すようにします。

|関数|動作|
|--------------|--------------|
|**exit**|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードで終了します。|
|**_exit**|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードで終了します。|
|**_cexit**|完全な C ライブラリの終了処理を実行し、呼び出し元に戻りますが、プロセスを終了しません。|
|**_c_exit**|高速な C ライブラリの終了処理を実行し、呼び出し元に戻りますが、プロセスを終了しません。|

呼び出すと、 **_cexit**または **_c_exit**関数の呼び出し時に存在する一時または自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトとは、オブジェクトが静的と宣言されていない関数内で定義されるオブジェクトです。 一時オブジェクトはコンパイラによって作成されるオブジェクトです。 呼び出す前に自動オブジェクトを破棄する **_cexit**または **_c_exit**、明示的に次のように、オブジェクトのデストラクターを呼び出します。

```cpp
myObject.myClass::~myClass( );
```

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
