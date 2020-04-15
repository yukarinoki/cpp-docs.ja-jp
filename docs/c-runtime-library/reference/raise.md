---
title: raise
ms.date: 4/2/2020
api_name:
- raise
- _o_raise
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: b38a3430274b2324e345be30ce9e38f0c2749fa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338260"
---
# <a name="raise"></a>raise

実行中のプログラムにシグナルを送信します。

> [!NOTE]
> テストまたはデバッグのシナリオを除き、Microsoft Store アプリをシャットダウンする場合は、このメソッドを使用しないでください。 ストア アプリを閉じるプログラムまたは UI の方法は、 [Microsoft Store のポリシー](/legal/windows/agreements/store-policies)に従って許可されていません。 詳しくは[、UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)に関する情報をご覧ください。

## <a name="syntax"></a>構文

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>パラメーター

*sig*<br/>
発生するシグナル。

## <a name="return-value"></a>戻り値

正常に終了した場合、**raise** は 0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>解説

**raise** 関数は実行中のプログラムに *sig* を送信します。 **signal** への前回の呼び出しが *sig* の通知処理関数を組み込んでいた場合、**raise** はその関数を実行します。 ハンドラー関数がインストールされていない場合、シグナル値 *sig* に関連付けられた既定のアクションは、次のように取得されます。

|シグナル|意味|Default|
|------------|-------------|-------------|
|**SIGABRT**|異常終了|コード 3 で呼び出し元のプログラムを終了する|
|**SIGFPE**|浮動小数点エラー|呼び出し元のプログラムを終了します。|
|**SIGILL**|無効な命令|呼び出し元のプログラムを終了します。|
|**SIGINT**|Ctrl + C 割り込み|呼び出し元のプログラムを終了します。|
|**SIGSEGV**|ストレージへの無効なアクセス|呼び出し元のプログラムを終了します。|
|**SIGTERM**|プログラムに送信される終了要求|シグナルを無視する|

上で指定したように、引数が有効なシグナルでない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 処理されない場合、関数は**errno**を**EINVAL**に設定し、ゼロ以外の値を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**raise**|\<signal.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[中止](abort.md)<br/>
[信号](signal.md)<br/>
