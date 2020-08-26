---
title: cl.exe の戻り値
ms.date: 09/05/2018
helpviewer_keywords:
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
ms.openlocfilehash: 06e0993f6a96117ab73f22e73857843dfcc334a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836726"
---
# <a name="return-value-of-clexe"></a>cl.exe の戻り値

cl.exe では、動作が正常終了した場合 (エラーがない場合) は 0 を返し、それ以外の場合は 0 以外の値を返します。

スクリプト、PowerShell、.cmd、または .bat ファイルからコンパイルを行う場合は、cl.exe の戻り値が役に立ちます。 エラーまたは警告が発生した場合にそれらを解決できるように、コンパイラの出力をキャプチャすることをお勧めします。

cl.exe のエラー終了コードは多すぎて、すべてを表示することはできません。 エラーコードは、% ProgramFiles (x86)% \ Windows Kit winerror.h の Windows Software Development Kit に含まれる、Windows ソフトウェア開発キットに含まれているファイルで参照でき \\ <em>version</em>ます。 10 進数で返されるエラー コードは、16 進数に変換して検索する必要があります。 たとえば、16 進数に変換された -1073741620 エラー コードは 0xC00000CC です。 このエラーは ntstatus.h にあり、対応するメッセージは "指定した共有名がリモート サーバーで見つかりません" です。 Windows エラーコードのダウンロード可能な一覧については、「 [&#91;MS-ERREF&#93;: Windows エラーコード](/openspecs/windows_protocols/MS-ERREF)」を参照してください。

Visual Studio でエラー ルックアップ ユーティリティを使用して、コンパイラ エラー メッセージの意味を検索することもできます。 Visual Studio のコマンドシェルで、 **errlook.exe** を入力してユーティリティを起動します。または、Visual Studio IDE のメニューバーで、[ **ツール**]、[ **エラー検索**] の順に選択します。 エラー値を入力して、そのエラーに関連付けられている説明のテキストを見つけます。 詳細については、「 [ERRLOOK Reference](errlook-reference.md)」を参照してください。

## <a name="remarks"></a>解説

次に、cl.exe の戻り値を使用するサンプル .bat ファイルを示します。

```cmd
echo off
cl /W4 t.cpp
@if ERRORLEVEL == 0 (
   goto good
)

@if ERRORLEVEL != 0 (
   goto bad
)

:good
   echo "clean compile"
   echo %ERRORLEVEL%
   goto end

:bad
   echo "error or warning"
   echo %ERRORLEVEL%
   goto end

:end
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
