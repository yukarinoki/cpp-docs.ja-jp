---
title: raise
ms.date: 1/02/2018
apiname:
- raise
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
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: 68d1cc653b955e607648e4d30562d2b77e3520e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358060"
---
# <a name="raise"></a>raise

実行中のプログラムにシグナルを送信します。

> [!NOTE]
> テストまたはデバッグ シナリオにを除き、Microsoft Store アプリをシャット ダウンは、このメソッドを使用しないでください。 ストア アプリを終了するプログラムや UI の方法はに従って許可されていません、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)します。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)します。

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

## <a name="remarks"></a>Remarks

**raise** 関数は実行中のプログラムに *sig* を送信します。 **signal** への前回の呼び出しが *sig* の通知処理関数を組み込んでいた場合、**raise** はその関数を実行します。 ハンドラー関数がインストールされていない場合、シグナル値 *sig* に関連付けられた既定のアクションは、次のように取得されます。

|シグナル|説明|既定値|
|------------|-------------|-------------|
|**SIGABRT**|異常終了|コード 3 で呼び出し元のプログラムを終了する|
|**SIGFPE**|浮動小数点エラー|呼び出し元のプログラムを終了します。|
|**SIGILL**|無効な命令|呼び出し元のプログラムを終了します。|
|**SIGINT**|Ctrl + C 割り込み|呼び出し元のプログラムを終了します。|
|**SIGSEGV**|ストレージへの無効なアクセス|呼び出し元のプログラムを終了します。|
|**SIGTERM**|プログラムに送信される終了要求|シグナルを無視する|

上で指定したように、引数が有効なシグナルでない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 関数は、設定が処理されない場合**errno**に**EINVAL**を 0 以外の値を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**raise**|\<signal.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[signal](signal.md)<br/>
