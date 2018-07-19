---
title: _CrtSetReportHook | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ef76fe0b7befb99b5bf0e8bb69fa1a1229782de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398790"
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

## <a name="remarks"></a>コメント

**_CrtSetReportHook**により、C ランタイム デバッグ ライブラリのレポート プロセスに独自のレポート関数を使用するアプリケーション。 その結果、デバッグ レポートを生成するために [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) が呼び出されるたびに、アプリケーションのレポート関数が先に呼び出されます。 この機能により、特定の割り当ての種類に注目したりできない宛先を使用してレポートを送信できるように、デバッグ レポートをフィルター処理などの操作を実行するアプリケーション **_CrtDbgReport**です。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtSetReportHook**プリプロセス時に削除されます。

堅牢なバージョンの **_CrtSetReportHook**を参照してください[_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md)です。

**_CrtSetReportHook**関数、新しいクライアント定義レポート関数で指定されたをインストール*reportHook*し、以前のクライアント定義フック関数を返します。 次の例は、クライアント定義レポート フックをどのようにプロトタイプ宣言するかを示しています。

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

ここで*reportType*デバッグ レポートの種類は、(**前述**、 **_CRT_ERROR**、または **_CRT_ASSERT**)、*メッセージ*は、完全に組み立てられたデバッグ ユーザー メッセージ、レポートに含まれていると**returnValue**レポートで返される必要がある関数をクライアント定義で指定された値は **_CrtDbgReport**です。 使用できるレポートの種類の詳細については、[_CrtSetReportMode](crtsetreportmode.md) 関数を参照してください。

クライアント定義レポート関数は、それ以上のレポートは必要ありませんされるように完全にデバッグ メッセージを処理する場合、関数が返す**TRUE**です。 関数が返されるときに**FALSE**、 **_CrtDbgReport**が呼び出され、レポートの種類、モード、およびファイルの現在の設定を使用してデバッグ レポートを生成します。 指定することによってさらに、 **_CrtDbgReport**内の値を返す**returnValue**アプリケーションは、デバッグ ブレークが発生したかどうかも制御できます。 デバッグ レポートを構成および生成する方法の詳細については、次を参照してください。 **_CrtSetReportMode**、 [_CrtSetReportFile](crtsetreportfile.md)、および **_CrtDbgReport**です。

フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。

> [!NOTE]
> アプリケーションがコンパイルされた場合 **/clr**され、レポート関数が呼び出されたアプリケーションの終了後にメイン、CLR レポート機能は、CRT 関数を呼び出す場合、例外がスローされます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
