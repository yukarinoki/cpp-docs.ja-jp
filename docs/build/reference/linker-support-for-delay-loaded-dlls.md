---
description: 詳細については、「リンカーによる遅延読み込み Dll のサポート」を参照してください。
title: リンカーによる DLL の遅延読み込み
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.openlocfilehash: 9ae1e2c68ed59e742493a9098d98fc35d5f2a7c7
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667278"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>リンカーによる DLL の遅延読み込み

MSVC リンカーは、Dll の遅延読み込みをサポートしています。 この機能により、Windows SDK の関数を使用したり、DLL の遅延読み込みを実装したりする必要がなく `LoadLibrary` `GetProcAddress` なります。

遅延読み込みを行わない場合、実行時に DLL を読み込む唯一の方法は、およびを使用することです。 `LoadLibrary` `GetProcAddress` オペレーティングシステムは、それを使用する実行可能ファイルまたは dll が読み込まれたときに dll を読み込みます。

遅延読み込みを使用すると、DLL を暗黙的にリンクするときに、プログラムがその DLL 内の関数を呼び出すまで DLL の読み込みを遅らせるオプションが提供されます。

アプリケーションでは、ヘルパー関数と共に[ `/DELAYLOAD` (遅延読み込みインポート)](delayload-delay-load-import.md)リンカーオプションを使用して DLL の読み込みを遅延させることができます。 (既定のヘルパー関数の実装は、Microsoft によって提供されます)。ヘルパー関数は、およびを呼び出すことによって、実行時に必要に応じて DLL を読み込み `LoadLibrary` `GetProcAddress` ます。

次の場合は、DLL の遅延読み込みを検討してください。

- プログラムが DLL 内の関数を呼び出さない可能性があります。

- DLL 内の関数は、プログラムの実行中に遅延するまで呼び出されないことがあります。

DLL の遅延読み込みは、EXE プロジェクトまたは DLL プロジェクトのビルド時に指定できます。 1つ以上の Dll 自体の読み込みを遅らせている DLL プロジェクトは、で遅延読み込みされたエントリポイントを呼び出すことは `DllMain` できません。

次の記事では、Dll の遅延読み込みについて説明します。

- [遅延読み込みする Dll の指定](specifying-dlls-to-delay-load.md)

- [遅延読み込みされた DLL の明示的なアンロード](explicitly-unloading-a-delay-loaded-dll.md)

- [遅延読み込みされた DLL のすべてのインポートを読み込みます](loading-all-imports-for-a-delay-loaded-dll.md)

- [遅延読み込みされたインポートのバインド](binding-imports.md)

- [エラー処理と通知](error-handling-and-notification.md)

- [遅延読み込みされたインポートのダンプ](dumping-delay-loaded-imports.md)

- [DLL の遅延読み込みの制約](constraints-of-delay-loading-dlls.md)

- [ヘルパー関数について](understanding-the-helper-function.md)

- [独自のヘルパー関数を開発する](developing-your-own-helper-function.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](../dlls-in-visual-cpp.md)<br/>
[MSVC リンカーのリファレンス](linking.md)
