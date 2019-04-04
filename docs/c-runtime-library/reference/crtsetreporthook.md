---
title: _CrtSetReportHook
ms.date: 11/04/2016
apiname:
- _CrtSetReportHook
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
apitype: DLLExport
f1_keywords:
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 7dcb916ea920751618ffa6a4afbcde8df5e35cba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478339"
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

C ランタイム デバッグ レポート プロセスにフックして、クライアント定義レポート関数をインストールします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>パラメーター

*reportHook*<br/>
C ランタイム デバッグ レポート プロセスにフックする新しいクライアント定義レポート関数。

## <a name="return-value"></a>戻り値

以前のクライアント定義レポート関数を返します。

## <a name="remarks"></a>Remarks

**_CrtSetReportHook**により、C ランタイム デバッグ ライブラリのレポート プロセスに独自のレポートの関数を使用するアプリケーション。 その結果、デバッグ レポートを生成するために [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) が呼び出されるたびに、アプリケーションのレポート関数が先に呼び出されます。 この機能により、特定の割り当ての種類に注目したりを使用して、対応できない宛先にレポートを送信できるように、デバッグ レポートをフィルター処理などの操作を実行するアプリケーション **_CrtDbgReport**します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtSetReportHook**プリプロセス時に削除されます。

堅牢なバージョンの **_CrtSetReportHook**を参照してください[_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md)します。

**_CrtSetReportHook**関数クライアント定義レポート関数で指定された新しいインストール*reportHook*し、以前のクライアント定義フック関数を返します。 次の例は、クライアント定義レポート フックをどのようにプロトタイプ宣言するかを示しています。

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

場所*reportType*はデバッグ レポートの種類 (**前述**、 **_CRT_ERROR**、または **_CRT_ASSERT**)、 *メッセージ*は、レポートに含まれるよう、完全に組み立てられたデバッグ ユーザー メッセージと**returnValue**クライアント定義によって指定された値がによって返される関数を報告 **_CrtDbgReport**します。 使用できるレポートの種類の詳細については、[_CrtSetReportMode](crtsetreportmode.md) 関数を参照してください。

クライアント定義レポート関数は、それ以上のレポートの必要はありませんように完全にデバッグ メッセージを処理する場合、関数が返す**TRUE**します。 関数が返す場合**FALSE**、 **_CrtDbgReport**が呼び出され、レポートの種類、モード、およびファイルの現在の設定を使用してデバッグ レポートを生成します。 指定することでさらに、 **_CrtDbgReport**で値を返す**returnValue**アプリケーションは、デバッグ ブレークが発生したかどうかも制御できます。 デバッグ レポートを構成および生成する方法の詳細については、**_CrtSetReportMode**、 [_CrtSetReportFile](crtsetreportfile.md)、および **_CrtDbgReport**を参照してください。

フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。

> [!NOTE]
> アプリケーションをコンパイルした場合 **/clr**およびレポート関数を呼び出すと、アプリケーションの終了後にメイン、レポートの関数が CRT 関数を呼び出す場合に、CLR が例外をスローします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
