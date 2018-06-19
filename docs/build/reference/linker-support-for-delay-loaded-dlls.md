---
title: リンカーによる Dll の遅延読み込みの |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aea4ca6d5391f71f27d59d0192fcf1f832dd6702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375585"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>リンカーによる DLL の遅延読み込み
Visual C リンカーは、Dll の遅延読み込みをサポートします。 Windows SDK の機能を使用する必要がなくなるこの**LoadLibrary**と**GetProcAddress** DLL 遅延読み込みを実装します。  
  
 Visual C 6.0 では、前に実行時に DLL を読み込む必要があるを使用して**LoadLibrary**と**GetProcAddress**; オペレーティング システムは DLL を読み込むときに実行可能ファイルまたは読み込まれた DLL を使用します。  
  
 Visual C 6.0 から始まり、DLL を静的にリンクするときに、リンカーは、プログラムは、その DLL で関数を呼び出すまで、DLL の読み込みを遅延するオプションを提供します。  
  
 アプリケーションが遅れる原因を使用して、DLL を読み込む、 [/DELAYLOAD (遅延読み込みインポート)](../../build/reference/delayload-delay-load-import.md)リンカー オプション、ヘルパー関数 (Visual C によって提供される既定の実装) を使用します。 ヘルパー関数は DLL の読み込み、実行時に呼び出すことによって**LoadLibrary**と**GetProcAddress**します。  
  
 DLL の遅延読み込み場合を考慮する必要があります。  
  
-   プログラムは、DLL の関数を呼び出さない可能性があります。  
  
-   DLL の関数が、プログラムの実行の後半まで呼び出さない可能性があります。  
  
 いずれかのビルド時に DLL の遅延読み込みを指定することができます、します。EXE またはします。DLL のプロジェクトです。 です。DLL プロジェクトを 1 つまたは複数の Dll の読み込みを遅らせる呼び出す必要はありません自体、遅延読み込みのエントリ ポイント Dllmain 内です。  
  
 次のトピックでは、Dll の遅延読み込みについて説明します。  
  
-   [遅延読み込みする DLL の指定](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [遅延読み込みした DLL の明示的なアンロード](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [遅延読み込みされた DLL に対するすべてのインポートの読み込み](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [インポートのバインド](../../build/reference/binding-imports.md)  
  
-   [エラー処理と通知](../../build/reference/error-handling-and-notification.md)  
  
-   [遅延読み込みしたインポートのダンプ](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [DLL の遅延読み込みの制約](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [ヘルパー関数について](understanding-the-helper-function.md)  
  
-   [独自のヘルパー関数の作成](../../build/reference/developing-your-own-helper-function.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C の Dll](../../build/dlls-in-visual-cpp.md)   
 [リンク](../../build/reference/linking.md)