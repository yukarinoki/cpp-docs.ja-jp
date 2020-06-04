---
title: _cexit、_c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: 78675ef91c2ab68e18f6111b4908886017ae1f79
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917143"
---
# <a name="_cexit-_c_exit"></a>_cexit、_c_exit

クリーンアップ操作を実行し、プロセスを終了せずに処理を戻します。

## <a name="syntax"></a>構文

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>解説

**_Cexit**関数は、 **atexit**および **_onexit**によって登録された関数を、後入れ先出し (LIFO) の順序で呼び出します。 次に、 **_cexit**すべての i/o バッファーをフラッシュし、すべての開いているストリームを閉じてから制御を戻します。 **_c_exit**は **_exit**と同じですが、 **atexit**または **_onexit**を処理したり、ストリームバッファーをフラッシュしたりせずに呼び出し元のプロセスに戻ります。 次の表に、 **exit**、 **_exit**、 **_cexit**、および **_c_exit**の動作を示します。

|関数|動作|
|--------------|--------------|
|**exit**|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードで終了します。|
|**_exit**|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードで終了します。|
|**_cexit**|完全な C ライブラリの終了処理を実行し、呼び出し元に戻りますが、プロセスを終了しません。|
|**_c_exit**|高速な C ライブラリの終了処理を実行し、呼び出し元に戻りますが、プロセスを終了しません。|

**_Cexit**または **_c_exit**関数を呼び出すと、呼び出し時に存在する一時オブジェクトまたは自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトとは、オブジェクトが静的と宣言されていない関数内で定義されるオブジェクトです。 一時オブジェクトはコンパイラによって作成されるオブジェクトです。 **_Cexit**または **_c_exit**を呼び出す前に自動オブジェクトを破棄するには、次のようにオブジェクトのデストラクターを明示的に呼び出します。

```cpp
myObject.myClass::~myClass( );
```

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[取り消し](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
