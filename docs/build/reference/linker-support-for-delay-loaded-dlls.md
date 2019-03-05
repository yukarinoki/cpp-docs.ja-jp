---
title: リンカーによる DLL の遅延読み込み
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 2ff5143b8c3850386f73ff713e7986fdc3b59fd1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301390"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>リンカーによる DLL の遅延読み込み

Visual C リンカーでは、Dll の遅延読み込みできるようになりました。 Windows SDK の機能を使用する必要のあるこの**LoadLibrary**と**GetProcAddress** DLL 遅延読み込みを実装します。

使用すると、実行時に DLL を読み込む唯一の方法がなかった Visual C 6.0 では、前に**LoadLibrary**と**GetProcAddress**; オペレーティング システムは DLL を読み込むときに実行可能ファイルまたは DLL が読み込まれたを使用します。

Visual C 6.0 以降、DLL と暗黙的にリンクするときに、リンカーは、プログラムは、その DLL で関数を呼び出すまで、DLL の読み込みを遅らせるオプションを提供します。

アプリケーションが遅れる可能性が DLL を使用して読み込む、 [/DELAYLOAD (遅延読み込みインポート)](../../build/reference/delayload-delay-load-import.md)ヘルパー関数 (Visual C によって提供される既定の実装) を使用したリンカー オプション。 ヘルパー関数は、実行時に、DLL を呼び出すことによって読み込まれます**LoadLibrary**と**GetProcAddress**できます。

場合、DLL の読み込み遅延を考慮してください。

- プログラムでは、DLL で関数を呼び出すことができません。

- DLL の関数は、プログラムの実行の終盤まで呼び出さない可能性があります。

いずれかのビルド中に DLL の遅延読み込みを指定することができます、します。EXE またはします。DLL のプロジェクトです。 A。DLL プロジェクトを 1 つまたは複数の Dll の読み込みを遅延させる自体呼び出さないでください。 遅延読み込みのエントリ ポイントを Dllmain 内。

次のトピックでは、Dll の遅延読み込みについて説明します。

- [遅延読み込みする DLL の指定](../../build/reference/specifying-dlls-to-delay-load.md)

- [遅延読み込みした DLL の明示的なアンロード](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)

- [遅延読み込みされた DLL に対するすべてのインポートの読み込み](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)

- [インポートのバインド](../../build/reference/binding-imports.md)

- [エラー処理と通知](../../build/reference/error-handling-and-notification.md)

- [遅延読み込みしたインポートのダンプ](../../build/reference/dumping-delay-loaded-imports.md)

- [DLL の遅延読み込みの制約](../../build/reference/constraints-of-delay-loading-dlls.md)

- [ヘルパー関数について](understanding-the-helper-function.md)

- [独自のヘルパー関数の作成](../../build/reference/developing-your-own-helper-function.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../../build/dlls-in-visual-cpp.md)<br/>
[リンク](../../build/reference/linking.md)
