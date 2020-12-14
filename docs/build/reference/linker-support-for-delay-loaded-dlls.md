---
description: 詳細については、Delay-Loaded Dll のリンカーサポートに関するページを参照してください。
title: リンカーによる DLL の遅延読み込み
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 6bf4527d14c7313874f162f0597114132b1a81cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190966"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>リンカーによる DLL の遅延読み込み

MSVC リンカーで、Dll の遅延読み込みがサポートされるようになりました。 これにより、Windows SDK 関数 **LoadLibrary** と **GetProcAddress** を使用して、DLL の遅延読み込みを実装する必要がなくなります。

6.0 Visual C++ する前に、実行時に DLL を読み込む唯一の方法は、 **LoadLibrary** と **GetProcAddress** を使用することでした。オペレーティングシステムは、それを使用する実行可能ファイルまたは DLL が読み込まれたときに DLL を読み込みます。

Visual C++ 6.0 以降では、dll と暗黙的にリンクする場合、リンカーは dll 内の関数を呼び出すまで DLL の遅延読み込みを行うオプションを提供します。

アプリケーションでは、ヘルパー関数 (Visual C++ によって提供される既定の実装) と共に [/DELAYLOAD (遅延読み込みインポート)](delayload-delay-load-import.md) リンカーオプションを使用して DLL の読み込みを遅延させることができます。 ヘルパー関数は、 **LoadLibrary** と **GetProcAddress** を呼び出すことによって、実行時に DLL を読み込みます。

次の場合、DLL の遅延読み込みを考慮する必要があります。

- プログラムが DLL 内の関数を呼び出すことはできません。

- DLL 内の関数は、プログラムの実行中に遅延するまで呼び出されないことがあります。

DLL の遅延読み込みは、いずれかののビルド中に指定できます。EXE または。DLL プロジェクト。 ある.1つ以上の Dll の読み込みを遅延させる DLL プロジェクト自体が、ddl の遅延読み込みエントリポイントを呼び出さないようにする必要があります。

次のトピックでは、Dll の遅延読み込みについて説明します。

- [遅延読み込みする Dll の指定](specifying-dlls-to-delay-load.md)

- [Delay-Loaded DLL の明示的なアンロード](explicitly-unloading-a-delay-loaded-dll.md)

- [Delay-Loaded DLL のすべてのインポートを読み込んでいます](loading-all-imports-for-a-delay-loaded-dll.md)

- [インポートのバインド](binding-imports.md)

- [エラー処理と通知](error-handling-and-notification.md)

- [Delay-Loaded インポートのダンプ](dumping-delay-loaded-imports.md)

- [Dll の遅延読み込みの制約](constraints-of-delay-loading-dlls.md)

- [ヘルパー関数について](understanding-the-helper-function.md)

- [独自のヘルパー関数の開発](developing-your-own-helper-function.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](../dlls-in-visual-cpp.md)<br/>
[MSVC リンカーのリファレンス](linking.md)
